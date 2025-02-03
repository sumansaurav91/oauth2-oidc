# OAuth2.0 Fundamentals

## Core Concepts and Terminology

### Access Token 

* **Definition**: An access token is a tiny piece of code that contains a large amount of data. Information about the user, permissions, groups, and timeframes is embedded within one token that passes from a server to a user's device.
* Represents authorization to access resources
* Usually short-lived (typically 1 hour)
* Sent with each API request
* What’s Included in an Access Token?
   - Three key elements are included in most access tokens.
      - **Header**: Data about the token's type and the algorithm used to make it are included here. 
      - **Payload**: Information about the user, including permissions and expirations, is included here. 
      - **Signature**: Verification data, so the recipient can ensure the authenticity of the token, is included here. This signature is typically hashed, so it's difficult to hack and replicate.

#### Sample Access Token
```JWT
eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IlEwWkdPRFpHUWpORVFqSTBOVEkxTWpVM05ERXlSVEUzTUVJNE9FVkRPRVF6TVRaR1JEWkZNUSJ9.eyJodHRwczovL3FsLmN1c3RvbS5vcGVuaWQuY29tL2NsaWVudF9uYW1lIjoic3NhdXJhdi10ZXN0LWNsaWVudCIsImlzcyI6Imh0dHBzOi8vc3NvLnRlc3QuYXV0aHJvY2suY29tLyIsInN1YiI6Im9jbWlacG1oa0dpN01VakpGNkF0R01IejhyTnhlSldCQGNsaWVudHMiLCJhdWQiOiJ1cm46cWwtYXBpOnJvY2tldGFjY291bnQtYXBpLTIwMTc3NzpUZXN0IiwiaWF0IjoxNzM4NTY1Mzc1LCJleHAiOjE3Mzg1Njg5NzUsInNjb3BlIjoiYWNjb3VudDpyZWFkIGFjY291bnQ6d3JpdGUgYWNjb3VudDphZG1pbiBhZG1pbmFjY291bnQ6cmVhZCBhZG1pbmFjY291bnQ6d3JpdGUgYWRtaW5tZmE6cmVhZCBhZG1pbm1mYTp3cml0ZSBleHRlcm5hbGFkbWluOnJlYWQgZXh0ZXJuYWxhZG1pbjp3cml0ZSBhY2NvdW50bGlua2luZzpyZWFkIGFjY291bnRsaW5raW5nOndyaXRlIGN1cnJlbnRhY2NvdW50OnJlYWQgY3VycmVudGFjY291bnQ6d3JpdGUgY3VycmVudG1mYTpyZWFkIGN1cnJlbnRtZmE6d3JpdGUgYWRtaW5wYW5lbDpyZWFkIG1lcmdlOndyaXRlIHByaXZhY3k6d3JpdGUgaGVhbHRoOnJlYWQiLCJndHkiOiJjbGllbnQtY3JlZGVudGlhbHMiLCJhenAiOiJvY21pWnBtaGtHaTdNVWpKRjZBdEdNSHo4ck54ZUpXQiIsInBlcm1pc3Npb25zIjpbImFjY291bnQ6cmVhZCIsImFjY291bnQ6d3JpdGUiLCJhY2NvdW50OmFkbWluIiwiYWRtaW5hY2NvdW50OnJlYWQiLCJhZG1pbmFjY291bnQ6d3JpdGUiLCJhZG1pbm1mYTpyZWFkIiwiYWRtaW5tZmE6d3JpdGUiLCJleHRlcm5hbGFkbWluOnJlYWQiLCJleHRlcm5hbGFkbWluOndyaXRlIiwiYWNjb3VudGxpbmtpbmc6cmVhZCIsImFjY291bnRsaW5raW5nOndyaXRlIiwiY3VycmVudGFjY291bnQ6cmVhZCIsImN1cnJlbnRhY2NvdW50OndyaXRlIiwiY3VycmVudG1mYTpyZWFkIiwiY3VycmVudG1mYTp3cml0ZSIsImFkbWlucGFuZWw6cmVhZCIsIm1lcmdlOndyaXRlIiwicHJpdmFjeTp3cml0ZSIsImhlYWx0aDpyZWFkIl19.mGWFAhovB7y2tikMoCFLIM3D7iDBkLMhQPe1SOsyh6mQZwnmIsA_VmXOGKmTw1wRZpHDZuEfcDvi7W1pfUhGMEPqGhWmUtsHEZUoNk0fvx07hf7YMBeEA9cjW1o3goJ6vFKcF8crnZuqMNUNweGnTjs4ESrlHhyZL4BqmTUUB3VRGrlFjhIN7sr-Y-ywAfh6i3zJfxzPQBbJAfEaEoG118XUA_kVhh9Nb6VZqJ2yNqpwJM9-uiQ-IpDRanQQrzIjHCzLybSF4MMCudHeoScphAr-GBdDsk0D0x5l2EzBtlV3VlqwK-SRlQavloLhEYSzP8OmnuVgEkag_ztoJPSt8gggg
```
#### Decode Sample Access Token

<img width="800" alt="image" src="https://github.com/user-attachments/assets/13cc9a12-2b63-4cb0-96a9-426d8b97bfbd" />

<img width="800" alt="image" src="https://github.com/user-attachments/assets/6eebf38a-6e69-455e-b1a9-149fa7db5236" />

<img width="800" alt="image" src="https://github.com/user-attachments/assets/44ed2e18-d518-4186-8f5a-de54e8c70d78" />

### Refresh Token:
* **Definition**: A refresh token is a token that allows a client to get a new access token when the current access token expires.
  - Longer-lived token (days/months)
  - Used to obtain new access tokens
  - More securely stored than access tokens
* Benefits
  - Refresh tokens improve user experience by allowing users to remain logged in across sessions 
  - Refresh tokens provide greater security by allowing the authorization server to revoke them if necessary
* When it's invalidated 
  - A refresh token can be invalidated if:
  - The authorization server revokes it
  - The user revokes their consent
  - The refresh token expires
  - The authentication policy for the resource changes

### Scope:
* **Definition**:  scope in an access token is a permission that limits what an application can do with a user's data. Scopes are used in OAuth 2.0 to control access to a user's account. 
  - Defines permission boundaries
  - Granular access control
  - Requested by client, approved by user
  - Example: ```scope=read_profile write_posts read_photos```


## Main Roles

### Resource Owner:
* **Definition**:
   - "Resource Owner" refers to the individual or entity that owns the data or resource being accessed, and is typically the end-user who has the authority to grant or deny access to that resource, usually by providing their credentials to an application requesting access;
   - essentially, the person who is being authenticated to access a protected resource.
     
### Client (Application):
* Request Access to resource
* Types:
  ```
  // Confidential Client (can keep secrets) - Typically Server side application running on a secure server where client secret can be safely stored
   client_id: abc123
   client_secret: xyz789
   
   // Public Client (cannot keep secrets) - Application running on User's device like mobile app or SPA
   client_id: def456
  ```

  ### Authorization Server:
  * **Definition**: An authorization server is a server that verifies a user's permissions and issues tokens to client applications. It acts as a central hub for managing access control to protected resources.
  * Key Endpoints:
    
    ```
      * /authorize    - User consent
      * /token       - Token issuance
      * /revoke      - Token revocation
      * /userinfo    - User information (OIDC)
      * /.well-known/jwks.json: Provides public keys for token verification
      * /.well-known/openid-configuration - Discovery endpoint
    ```
  * Diagram Explaining Authorization Server Architecture

 ![image](https://github.com/user-attachments/assets/785dbab0-e7e3-418d-aa5a-c8b078d3abd0)

 * Flow Description
```js
1. Client -> Auth Server: Request authorization
   GET /authorize?
     response_type=code&
     client_id=abc123&
     scope=read_profile&
     redirect_uri=https://app.com/callback

2. User -> Auth Server: Grants consent

3. Auth Server -> Client: Returns auth code
   302 Redirect to: https://app.com/callback?code=xyz789

4. Client -> Auth Server: Exchanges code for tokens
   POST /token
   {
     grant_type: "authorization_code",
     code: "xyz789",
     client_id: "abc123",
     client_secret: "def456"
   }

5. Client -> Resource Server: Uses access token
   GET /api/resource
   Authorization: Bearer eyJhbGciOiJIUzI11111
```
### Resource Server
* **Definition**: A resource server is a server that hosts protected resources and provides access to them through an API. Resource servers are often used in OAuth 2.0, where they receive and validate access tokens to ensure that the request is authorized.
* Example:
  ```js
     GET /api/user/profile
     Authorization: Bearer eyJhbGciOiJIUzI11111
  ```

### Authentication
   * Focuses on "Who are you?"
   * Verifies user identity
   * Typically handled by OIDC
