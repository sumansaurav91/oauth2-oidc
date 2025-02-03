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

#### Refresh Token:
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
* Scope
  - Defines permission boundaries
  - Granular access control
  - Requested by client, approved by user
  - Example: ```scope=read_profile write_posts read_photos```




















