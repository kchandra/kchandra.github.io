# Setting up okta

## Authorization Code Flow

```sequence-diagram
User -> Web App : Access app
Web App -> Okta : Authorization Code Request /authorize
Okta --> User : Redirect to login page
User -> Okta : Authenticate
Okta --> Web App : Authorizaton Code
Web App -> Okta : Authorization Code + Client ID + Client Secret to /oauth/token
Note over Okta : Validate Authorization Code + Client ID + Client Secret
Okta --> Web App : ID Token and Access Token
Web App -> Your Api : Make api call with Access Token
Your Api --> Web App : Response
```

## Authorization Code Flow with PKCE

```sequence-diagram
User -> Web App : Access app
Note over Web App : Generate Code Verifier and Code Challenge
Web App -> Okta : Authorization Code Request + Code Challenge to  /authorize
Okta --> User : Redirect to login page
User -> Okta : Authenticate
Okta --> Web App : Authorizaton Code
Web App -> Okta : Authorization Code + Code Verifer to /oauth/token
Note over Okta : Validate Code Verifier and Challenge
Okta --> Web App : ID Token and Access Token
Web App -> Your Api : Make api call with Access Token
Your Api --> Web App : Response
```

