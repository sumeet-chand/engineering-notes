


# ADFS SSO Summary
1. DC1: Primary Domain Controller (on-prem AD).
2. DC2: Replica DC for redundancy.
3. ADFS Server:
  * Separate Windows Server with IIS hosting the login page (https://sts.bobsbuilders.com/adfs/ls).
  * Public SSL cert (e.g., DigiCert, Let’s Encrypt).
  * DNS A record: sts.bobsbuilders.com → ADFS server’s IP.
4. Facebook Business SSO Config:
  * Uploaded your ADFS metadata XML or manually entered:
  * SAML Endpoint: https://sts.bobsbuilders.com/adfs/ls
  * Public Cert: From ADFS.
5. User Flow:
  * Bob enters bob@bobsbuilders.com on Facebook → Redirected to ADFS.
  * ADFS validates against on-prem AD → Issues SAML token.
6. Auth Success: Facebook receives token → Logs Bob in.


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