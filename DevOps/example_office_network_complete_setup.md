

This document is a guide on a complete setup of a windows domain office network with users
and apps and how they are all setup.

# ADFS SSO Summary
1. Create Domain 
  * DC1: Primary Domain Controller (on-prem AD)
     * Install core roles (AD, DNS, DHCP): Install-WindowsFeature AD-Domain-Services, DNS, DHCP -IncludeManagementTools
     * Promote to DC (creates forest): Install-ADDSForest -DomainName "bobsbuilders.local" -InstallDNS -NoRebootOnCompletion
        * Open ports for Core AD/DNS/DHCP Ports
          * Port	Protocol	Purpose	Direction
          * 53	TCP/UDP	DNS Resolution	Inbound/Outbound
          * 88	TCP/UDP	Kerberos Authentication	Inbound/Outbound
          * 135	TCP	RPC (Remote Procedure Call)	Inbound/Outbound
          * 389	TCP/UDP	LDAP (Active Directory queries)	Inbound/Outbound
          * 445	TCP	SMB (File/Printer sharing, GPOs)	Inbound/Outbound
          * 636	TCP	LDAPS (Secure LDAP)	Inbound/Outbound
          * 3268	TCP	Global Catalog (LDAP)	Inbound/Outbound
          * 3269	TCP	Global Catalog (LDAPS)	Inbound/Outbound
     * Create AD users, add roles e.g, Remote desktop users, administrators
  * DC2 (Replica DC + AD CS)
     * Install core roles + AD CS (PKI): Install-WindowsFeature AD-Domain-Services, DNS, AD-Certificate -IncludeManagementTools
     * Promote as replica DC: Install-ADDSDomainController -DomainName "bobsbuilders.local" -InstallDNS -NoRebootOnCompletion
     * Configure AD CS (after reboot): Install-AdcsCertificationAuthority -CAType EnterpriseRootCA -ValidityPeriod Years 5 -CryptoProviderName "RSA#Microsoft Software Key Storage Provider" -KeyLength 2048
     * Open extra ports for AD CS
          * Port	Protocol	Purpose	Direction
          * 443	TCP	HTTP Enrollment (PKI web services)	Inbound (if web enrollment enabled)
          * 5985	TCP	WinRM (HTTP, for remote PS management & RMM)	Inbound/Outbound
          * 5986	TCP	WinRM (HTTPS, secure remote PS & RMM)	Inbound/Outbound
2. Setup Certs
  * Issue SSL Cert for Internal Apps: Open certsrv.msc on DC2 → Right-click Certificate Templates → Duplicate Web Server template. Name: InternalWebSSL → Enable Client Authentication + Server Authentication. Right-click Certificates → Request New Certificate → Choose InternalWebSSL. Subject Name: MyArchitectureProgram.bobsbuilders.local.
  * Trust the CA on All Devices: Export root cert from certsrv.msc (Right-click CA → Properties → View Certificate → Export as .cer). Use Group Policy to Install cert in Trusted Root Certification Authorities on all company PCs.
3. ADFS Server:
  * Separate Windows Server with ADFS + IIS roles and hosting the login page (https://sts.bobsbuilders.com/adfs/ls).
  * Public SSL cert (e.g., DigiCert, Let’s Encrypt).
  * DNS A record: sts.bobsbuilders.com → ADFS server’s IP.
   * open ports for ADFS
          * Port	Protocol	Purpose	Direction
          * 80	TCP	HTTP (Redirects to HTTPS)	Inbound (Public)
          * 443	TCP	HTTPS (SAML/WS-Federation endpoints)	Inbound (Public)
          * 49443	TCP	ADFS Admin Service (optional)	Inbound (Internal)
4. (optional For internal apps) 
 * Create IIS server e.g. WEBSERVER01 - add IIS ROLE
 * Create app and deploy it e.g, MyArchitectureProgram (point IIS to Router Static Public IP, then configure in Domain        register A record to point to it)
 * Open ports
    * Port	Protocol	Purpose	Direction
    * 80	TCP	HTTP (if used)	Inbound (Internal)
    * 443	TCP	HTTPS (SSL for internal app)	Inbound (Internal)
    * Example situation if Bob an AD user logs into his domain-joined PC he Gets Kerberos ticket from AD.
      ADFS uses this Kerberos ticket for SSO so Bob can log into MyArchitectureProgram.
5. Open all ports in the SD-WAN Router (as well as previously on each servers local firewall)
  * (optional if using DHCP/DNS server, disable DHCP/DNS in router)
   * Create port forwarding rules in router
    * Rule Type	Source	Destination	Port	Protocol	Action	Notes
    * Port Forward	WAN	ADFS Server (LAN IP)	443	TCP	Allow	Public ADFS endpoint (sts.bobsbuilders.com)
    * Port Forward	WAN	IIS Server (LAN IP)	443	TCP	Allow	Public app access (app.bobsbuilders.com)
    * LAN Inbound	DC1	DC2	389, 636	TCP	Allow	AD replication/LDAP(S)
    * LAN Inbound	ADFS Server	DC1/DC2	88, 389, 445	TCP	Allow	Kerberos/LDAP/SMB for auth
    * LAN Outbound	Any Server	Internet	443, 80	TCP	Allow	Let’s Encrypt renewals, updates
  * Block public access to WinRM (5985/5986), RDP (3389), and 49443 from WAN
  * Enable logging (if not done already)
  * Enable geoblocking e.g. North Korea
6. Create File Shares and backups
 * Enable VHDX Volume-Level (Full volume backup of d:\ data drives in Fileservers e..g FS01)
 * Enable WSB File/Folder-Level (Targeted backup).
 * Enable Shadow Copies ("Previous Versions") (Short-term snapshots, uses VSS).
 * Use a free software e.g, Veeam to create ISO backups of all servers
 * Setup a NAS or Backup server and put all the backups there.
 * Enable group policy for NTFS permission access to lock down files/folders
 * To check open shares - Computer management - Shares - all the shared drives will be listed
to add as network drives/browse as UNC paths etc.,
7. (optional for online apps) - Facebook Business SSO Config:
  * Uploaded your ADFS metadata XML or manually entered:
  * SAML Endpoint: https://sts.bobsbuilders.com/adfs/ls
  * Public Cert: From ADFS.
8. User Flow:
  * Bob enters bob@bobsbuilders.com on Facebook → Redirected to ADFS.
  * ADFS validates against on-prem AD → Issues SAML token.
9. Auth Success: Facebook receives token → Logs Bob in.


# ENTRA SSO Example

1. Sync on-prem AD to Azure AD Connect (DC1/DC2 → Azure AD) OR Create users in Entra
2. Enterprise App Registration - Identity - Enterprise Apps - Add Facebook/Salesforce as a SAML/WS-Fed app.
  * Upload their metadata XML or enter:
  * Sign-on URL: https://facebook.com
  * Entity ID: https://www.facebook.com/company_bobsbuilders
3. Map Azure AD attributes (e.g., userPrincipalName → SAML NameID) Add optional claims (e.g., department for role-based access).
4. Facebook/Salesforce Config:
 * Provide Azure AD’s:
 * Login URL: https://login.microsoftonline.com/<tenant-id>/saml2
 * Logout URL: https://login.microsoftonline.com/common/wsfederation?wa=wsignout1.0
 * Public Certificate (from Azure AD’s SAML settings).
5. User Flow - Bob visits facebook.com → Clicks "Sign in with Microsoft" (auto-redirect to Entra).
 * Azure AD checks:
 * (optional) If synced from on-prem AD → Auths via Kerberos (if Seamless SSO enabled).
 * Else → Shows Azure AD login page.
 * Issues SAML token → Bob lands in Facebook.