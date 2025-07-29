


# ADFS SSO Summary
1. Create Domain 
  * DC1: Primary Domain Controller (on-prem AD)
     * Install core roles (AD, DNS, DHCP): Install-WindowsFeature AD-Domain-Services, DNS, DHCP -IncludeManagementTools
     * Promote to DC (creates forest): Install-ADDSForest -DomainName "bobsbuilders.local" -InstallDNS -NoRebootOnCompletion
  * DC2 (Replica DC + AD CS)
     * Install core roles + AD CS (PKI): Install-WindowsFeature AD-Domain-Services, DNS, AD-Certificate -IncludeManagementTools
     * Promote as replica DC: Install-ADDSDomainController -DomainName "bobsbuilders.local" -InstallDNS -NoRebootOnCompletion
     * Configure AD CS (after reboot): Install-AdcsCertificationAuthority -CAType EnterpriseRootCA -ValidityPeriod Years 5 -CryptoProviderName "RSA#Microsoft Software Key Storage Provider" -KeyLength 2048
2. Setup Certs
  * Issue SSL Cert for Internal Apps: Open certsrv.msc on DC2 → Right-click Certificate Templates → Duplicate Web Server template. Name: InternalWebSSL → Enable Client Authentication + Server Authentication. Right-click Certificates → Request New Certificate → Choose InternalWebSSL. Subject Name: MyArchitectureProgram.bobsbuilders.local.
  * Trust the CA on All Devices: Export root cert from certsrv.msc (Right-click CA → Properties → View Certificate → Export as .cer). Use Group Policy to Install cert in Trusted Root Certification Authorities on all company PCs.
3. ADFS Server:
  * Separate Windows Server with ADFS + IIS roles and hosting the login page (https://sts.bobsbuilders.com/adfs/ls).
  * Public SSL cert (e.g., DigiCert, Let’s Encrypt).
  * DNS A record: sts.bobsbuilders.com → ADFS server’s IP.
4. (optional For internal apps) (e.g., MyArchitectureProgram on IIS WEBSERVER01) Bob logs into his domain-joined PC → Gets Kerberos TGT from AD.
ADFS uses this ticket for SSO to other on-prem apps (no password prompts).
6. (optional for online apps) - Facebook Business SSO Config:
  * Uploaded your ADFS metadata XML or manually entered:
  * SAML Endpoint: https://sts.bobsbuilders.com/adfs/ls
  * Public Cert: From ADFS.
7. User Flow:
  * Bob enters bob@bobsbuilders.com on Facebook → Redirected to ADFS.
  * ADFS validates against on-prem AD → Issues SAML token.
8. Auth Success: Facebook receives token → Logs Bob in.


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