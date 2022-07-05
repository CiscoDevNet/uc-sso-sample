# SSO Pop-Up Sample

Description: This sample demonstrates opening a popup window for the user to interact with the Cisco UC SSO login sequence, and extracting the SSO access token information via JavaScript in the child page.

## Files:
  - `ssopu.html`: Parent page, launches the SSO window and provides a callback function for the child window to send SSO token data back
  - `ssocb.html`: Child page, loaded at the end of the SSO sequence, calls the parent callback function to report the SSO token data (location.hash URL fragment)

## Requirements: 
  - Working SAML SSO environment for UCM/CUC
  - Basic web server to host the files, the files should be served via HTTPS
  - The SSO redirect URL pointing to `ssocb.html` must be configured in UC Manager or Unity Connection via **Enterprise Parameters**->**Redirect URIs for Third Party SSO Client**
  - User account credentials as configured in the SSO Identity Provider
  - The UC service host, SSO Identity Provider host, and application server host should be resolveable via DNS (manual entries in the 'hosts' file can help during testing)
  - Pop-up blockers may interfere with the popup window launch

## Getting Started:
  - Edit `ssopu.html` to provide the appropriate values for `ucHost` (e.g. UC Manager) and redirectUrl (e.g. https://myappserver/ssocb.html)
  - Upload both files to the web server, open `ssopu.html` in a browser
  - You may need to accept multiple certificates from the app server, UC host, and Identity Provider during the SSO sequence (or import them into the browser/system permanently)
  - Provide the user account credentials
  - The popup window should close and the access token be displayed in the parent page
  
