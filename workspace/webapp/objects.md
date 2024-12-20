
## HTTP Security Headers

[T1]

- [Check Online Security Headers](https://securityheaders.com/)

| HTTP Header                              | Description                                                                                            | Example Vulnerability                        | Example Use-Case                                           |
|------------------------------------------|--------------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------------------------------|
| **Strict-Transport-Security (HSTS)**     | Instructs browsers to only communicate via HTTPS, preventing Man-in-the-Middle (MitM) attacks.      | Downgrade attacks (HTTP to HTTPS)          | Forcing secure connections on a web application.          |
| **Content-Security-Policy (CSP)**       | Defines trusted sources for content, mitigating XSS and data injection attacks.                       | Cross-Site Scripting (XSS)                 | Preventing inline scripts and unauthorized resource loading.|
| **Cross-Origin Resource Sharing (CORS)**| Controls access to resources from different origins, reducing the risk of CSRF and data leaks.        | Cross-Site Request Forgery (CSRF)          | Allowing specific domains to access APIs.                 |
| **X-Frame-Options**                     | Prevents clickjacking by controlling whether a page can be displayed in a frame or iframe.            | Clickjacking attacks                        | Protecting sensitive actions from being deceived through framing.|
| **X-XSS-Protection**                    | Enables the browser's built-in XSS protection to block identified attacks.                            | Cross-Site Scripting (XSS)                 | Allows browsers to detect and block reflected XSS.        |
| **X-Content-Type-Options**              | Prevents browsers from MIME sniffing content types, reducing the risk of certain attacks.            | MIME type confusion                         | Ensuring proper handling of file types served by an application.|
| **Referrer-Policy**                     | Controls the amount of information shared when navigating from one page to another, enhancing privacy.| Referrer leakage                            | Limiting sensitive URL information while navigating.       |
| **Permissions-Policy**                  | Enables or disables the use of certain features (like geolocation, camera) on your site.              | Malicious feature access                    | Controlling access to features in iframes.               |
| **Public-Key-Pins (HPKP)**              | Allows a site to specify which public key (or keys) are valid for it, aimed to prevent MITM attacks   | Man-in-the-Middle attacks                   | Enforcing public key usage for client verification.       |
| **Expect-CT**                           | Allows web hosts to determine if they can enforce Certificate Transparency for their HTTPS certificates.| Misissued or fraudulent certificates        | Ensuring compliance with certificate transparency protocols.|
| **Content-Disposition**                  | Indicates if content should be treated as an attachment or inline, helping protect against unwanted file types.| Unintended file downloads                 | Customize how files are handled and presented to users.   |

Certainly! Below is a structured table representing the HTTP security headers, including ASCII art examples of how you might format these in a tool like Postman.

### HTTP Security Headers Examples in Postman

| HTTP Header                               | Example Request                                     |
|-------------------------------------------|----------------------------------------------------|
| **Strict-Transport-Security (HSTS)**      | POST /example HTTP/1.1                             |
|                                           | Host: example.com                                   |
|                                           | Strict-Transport-Security: max-age=31536000; includeSubDomains |
| **Content-Security-Policy (CSP)**        | POST /example HTTP/1.1                             |
|                                           | Host: example.com                                   |
|                                           | Content-Security-Policy: default-src 'self'; script-src 'none'; |
| **Cross-Origin Resource Sharing (CORS)** | POST /example HTTP/1.1                             |
|                                           | Host: example.com                                   |
|                                           | Access-Control-Allow-Origin: <https://trusted.com>    |
| **X-Frame-Options**                      | POST /example HTTP/1.1                             |
|                                           | Host: example.com                                   |
|                                           | X-Frame-Options: DENY                              |
| **X-XSS-Protection**                     | POST /example HTTP/1.1                             |
|                                           | Host: example.com                                   |
|                                           | X-XSS-Protection: 1; mode=block                    |
| **X-Content-Type-Options**               | POST /example HTTP/1.1                             |
|                                           | Host: example.com                                   |
|                                           | X-Content-Type-Options: nosniff                    |
| **Referrer-Policy**                      | POST /example HTTP/1.1                             |
|                                           | Host: example.com                                   |
|                                           | Referrer-Policy: no-referrer                        |
| **Permissions-Policy**                   | POST /example HTTP/1.1                             |
|                                           | Host: example.com                                   |
|                                           | Permissions-Policy: geolocation=(self)             |
| **Public-Key-Pins (HPKP)**               | POST /example HTTP/1.1                             |
|                                           | Host: example.com                                   |
|                                           | Public-Key-Pins: pin-sha256="base64-encoded-public-key"; max-age=5184000; includeSubDomains |
| **Expect-CT**                            | POST /example HTTP/1.1                             |
|                                           | Host: example.com                                   |
|                                           | Expect-CT: max-age=86400; enforce                  |
| **Content-Disposition**                   | POST /example HTTP/1.1                             |
|                                           | Host: example.com                                   |
|                                           | Content-Disposition: attachment; filename="example.png" |

Certainly! Below are the tables for HTTP security headers configuration for Apache and Nginx, now including a description for each header.

### HTTP Security Headers Configuration for Apache

| **Header**                     | **Configuration**                                     | **Description**                                                                                   |
|--------------------------------|------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **X-Frame-Options**            | Header always set "X-Frame-Options: DENY"           | Prevents the page from being displayed in a frame or iframe, mitigating clickjacking attacks.    |
|                                | Header always set "X-Frame-Options: SAMEORIGIN"     | Allows the page to be displayed in a frame on the same origin only, protecting against framing.   |
| **X-XSS-Protection**           | Header always set "X-XSS-Protection: 1; mode=block" | Enables the browser's cross-site scripting (XSS) filter to block detected attacks.                |
| **X-Content-Type-Options**     | Header always set "X-Content-Type-Options: nosniff" | Prevents the browser from MIME-sniffing the content type, helping to prevent attacks based on content type mismatches. |
| **Content-Security-Policy**    | Header set "Content-Security-Policy: default-src 'self'" | Specifies allowed sources for content to prevent XSS and data injection attacks.                  |
| **Referrer-Policy**            | Header always set "Referrer-Policy: no-referrer"    | Controls the amount of referrer information sent when navigating from your site, enhancing privacy. |

### HTTP Security Headers Configuration for Nginx

| **Header**                     | **Configuration**                                     | **Description**                                                                                   |
|--------------------------------|------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **X-Frame-Options**            | add_header X-Frame-Options "DENY";                   | Prevents the page from being displayed in a frame or iframe, mitigating clickjacking attacks.    |
|                                | add_header X-Frame-Options "SAMEORIGIN";            | Allows the page to be displayed in a frame on the same origin only, protecting against framing.   |
| **X-XSS-Protection**           | add_header X-XSS-Protection "1; mode=block";       | Enables the browser's cross-site scripting (XSS) filter to block detected attacks.                |
| **X-Content-Type-Options**     | add_header X-Content-Type-Options "nosniff";       | Prevents the browser from MIME-sniffing the content type, helping to prevent attacks based on content type mismatches. |
| **Content-Security-Policy**    | add_header Content-Security-Policy "default-src 'self';"; | Specifies allowed sources for content to prevent XSS and data injection attacks.                  |
| **Referrer-Policy**            | add_header Referrer-Policy "no-referrer";          | Controls the amount of referrer information sent when navigating from your site, enhancing privacy. |
| **Permissions-Policy**         | add_header Permissions-Policy "geolocation=(self)"; | Specifies features that can be accessed by the web page, including geolocation, enhancing privacy. |
| **Expect-CT**                  | add_header Expect-CT "max-age=86400; enforce";      | Instructs browsers to enforce Certificate Transparency, helping to detect misissued certificates.  |
| **Public-Key-Pins (HPKP)**     | add_header Public-Key-Pins "pin-sha256=\"base64-encoded-public-key\"; max-age=5184000; includeSubDomains"; | Provides a mechanism to prevent certain types of MITM attacks by specifying expected public key hashes. |

### Cookie Flags

| Cookie Flag            | Description                                                                                  | Example Vulnerability                           | Example Use-Case                                         |
|------------------------|----------------------------------------------------------------------------------------------|------------------------------------------------|---------------------------------------------------------|
| **Secure**             | Ensures the cookie is only sent over HTTPS connections to prevent transmission over unsecured channels. | Man-in-the-Middle (MitM) attacks              | Protecting session cookies during transit in secure applications.   |
| **HttpOnly**           | Prevents JavaScript access to cookies, reducing the risk of XSS attacks that could steal cookies. | Cross-Site Scripting (XSS)                    | Safeguarding authentication tokens from client-side scripts.     |
| **SameSite**           | Controls whether a cookie is sent with cross-site requests, mitigating CSRF attacks.        | Cross-Site Request Forgery (CSRF)             | Restricting cookies to first-party contexts to enhance security.  |
| **Domain**             | Specifies which domains can access the cookie.                                            | Subdomain hijacking                             | Limiting cookie access to specific subdomains to contain exposure. |
| **Path**               | Defines the URL path that must exist in the requested URL for the browser to send the cookie. | Cookie leakage through unintended paths        | Scoping cookies to specific pages or directories of web applications. |
| **Expires / Max-Age** | Defines the duration for which the cookie will be valid, after which it's automatically deleted. | Session fixation attacks                       | Expiring session cookies after a reasonable time period.         |
| **Samesite=Strict**   | Cookies are only sent in a first-party context; not sent along with cross-origin requests. | Cross-Site Request Forgery (CSRF)             | Preventing cookies from being sent in cross-origin requests regardless of user interactions. |
| **Samesite=Lax**      | Cookies are sent in a first-party context but are sent along with top-level navigation.   | Cross-Site Request Forgery (CSRF)             | Allowing cookies in navigational requests while blocking others.  |

## Common Endpoints[S1]

| Endpoint                     | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `/admin`                     | Common admin panel access.                                |
| `/login`                     | Login page for user authentication.                       |
| `/logout`                    | Logout functionality.                                     |
| `/api`                       | Base URL for API calls.                                   |
| `/api/v1/`                  | Versioned API endpoint.                                   |
| `/api/v1/auth/login`        | API endpoint for user login.                              |
| `/api/v1/auth/logout`       | API endpoint for user logout.                             |
| `/settings`                  | Settings page for user configurations.                    |
| `/config`                    | Configuration settings, often sensitive.                  |
| `/status`                    | Server status page (could reveal uptime).                |
| `/docs`                      | Documentation endpoint for APIs.                          |
| `/user/profile`              | User profile access.                                      |
| `/users`                     | User management or user listings.                         |
| `/api/v1/users/{id}`        | Fetch user details by ID.                                 |
| `/api/v1/products`          | List of products, could be sensitive.                    |
| `/api/v1/orders`            | Orders management, may return sensitive data.             |
| `/account/view?id=123`      | Viewing account details, can test ID changes.            |
| `/search`                    | Search functionality, can manipulate queries.             |
| `/register`                  | User registration page.                                   |
| `/password/reset`            | Password reset flows.                                     |
| `/uploads`                   | File upload endpoint, often critical for security.        |
| `/files`                     | Access to user-uploaded files or documents.               |
| `/reports`                   | Reporting tools access, might reveal internal metrics.    |
| `/notifications`             | User notifications endpoint.                              |
| `/help`                      | Help or support page.                                     |
| `/terms`                     | Terms of service and agreements.                          |
| `/privacy`                   | Privacy policy information.                               |
| `/api/healthcheck`          | Healthcheck endpoint for service availability.            |
| `/debug`                     | Debug page might expose application info.                |
| `/?debug=true`               | Testing for debug mode that reveals more data.           |
| `/?goto=...`               |  with different values to check for potential unlinked pages.           |

## JWT

### Cheet Sheet

Here's an expanded JWT (JSON Web Token) cheat sheet table that includes examples for each aspect. This will help clarify how to implement and utilize JWTs in web applications.

| **Aspect**               | **Details**                                                                                                                                                           | **Examples**                                                                                                                                                               |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **What is JWT?**        | JWT is a compact, URL-safe means of representing claims to be transferred between two parties.                                                                       | - An authorization token for a user after login.                                                                                                                         |
| **Structure of JWT**     | JWT consists of three parts: `<Header>.<Payload>.<Signature>`.                                                                                                     | Example JWT: `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c`                              |
| **Header**               | Contains metadata about the token, such as the signing algorithm (e.g., HS256) and token type (JWT).                                                                 | `{ "alg": "HS256", "typ": "JWT" }`                                                                                                                                       |
| **Payload**              | Contains the claims. Claims are statements about an entity (typically, the user) and additional data.                                                                 | `{ "sub": "1234567890", "name": "John Doe", "iat": 1516239022 }`                                                                                                      |
| **Signature**            | Used to verify the sender of the JWT and to ensure that the message wasn't changed. It is created using the header, payload, and a secret key.                       | `HMACSHA256(base64UrlEncode(header) + "." + base64UrlEncode(payload), secret)`                                                                                       |
| **Common Header Algorithms** | - **HS256**: HMAC using SHA-256.<br>- **RS256**: RSA Signature using SHA-256.<br>- **ES256**: ECDSA using P-256 and SHA-256.                                       | - **HS256**: `{"alg": "HS256", "typ": "JWT"}`<br>- **RS256**: Use with a public/private key pair for signing and verification.                                       |
| **Common Claims**        | - **iss**: Issuer.<br>- **sub**: Subject (the user the token represents).<br>- **aud**: Audience (intended recipients of the token).<br>- **exp**: Expiration time. <br>- **nbf**: Not before. <br>- **iat**: Issued at time. <br>- **jti**: JWT ID. | Example Claims: <br>`{ "iss": "example.com", "sub": "user123", "aud": "example_app", "exp": 1633072800 }`                                                             |
| **Best Practices**       | - Always use HTTPS to protect JWT in transit.<br>- Set short expiration times using the `exp` claim.<br>- Use secure storage for JWTs (e.g., HttpOnly cookies).<br>- Regularly rotate signing keys.<br>- Validate all claims when processing JWTs.<br>- Use audience and issuer validation to prevent token misuse.<br>- Implement token revocation strategies (e.g., blacklisting). | - Use `exp` to set a token's expiration: `{ "exp": Math.floor(Date.now() / 1000) + (60 * 60) }` (expires in 1 hour).                                                   |
| **Common Pitfalls**      | - Using weak signing algorithms (e.g., none is the default) can lead to security issues.<br>- Storing sensitive data in the payload (it's easily decodable).<br>- Failing to validate the token properly, leading to unauthorized access.<br>- Ignoring proper error handling on token validation errors.     | - Failure to validate: `if (!token) { throw new Error('Token not provided'); }` should be implemented.                                                               |
| **Revocation Strategies**| - Store blacklisted tokens.<br>- Use short-lived tokens with refresh tokens.<br>- Maintain a mutable token store for invalidation.                                      | - When a user logs out, add the token to a blacklist or mark it as revoked for a specific user session.                                                                  |
| **Token Storage**        | - **Local Storage**: Can be accessed by JavaScript but is vulnerable to XSS attacks.<br>- **Session Storage**: Similar risks as local storage.<br>- **HttpOnly Cookies**: Not accessible via JavaScript, reducing XSS risks.                       | - Store token in `HttpOnly` cookie: `Set-Cookie: jwt=your_jwt_token; HttpOnly; Secure; SameSite=Strict`                                                                |

### Additional Considerations

- **Token Size:** Limit payload size to improve performance, especially for mobile applications.
- **Libraries:** Use established libraries for JWT handling (e.g., `jsonwebtoken` in Node.js, `jwt` in Python).
- **Audit Logs:** Maintain logs of token usage for security and monitoring.

### Token Structure

Sure! Below is an ASCII representation of the structure of a JSON Web Token (JWT) along with related components such as headers and claims. A JWT typically consists of three parts: **Header**, **Payload**, and **Signature**. In this representation, I'll include the components of the JWT and some key flags that may be relevant.

```
+-------------------------------------------------------+
|                       JSON Web Token                  |
+-------------------------------------------------------+
|                       Header                           |
| -----------------------------------------------------  |
| {"alg": "HS256", "typ": "JWT"}                        |
| - alg: Algorithm used for signing (e.g., HS256)      |
| - typ: Type of the token (JWT)                         |
+-------------------------------------------------------+
|                       Payload                          |
| -----------------------------------------------------  |
| {"sub": "1234567890",                                 |
|  "name": "John Doe",                                   |
|  "iat": 1516239022,                                   |
|  "exp": 1516242622}                                   |
| - sub: Subject (e.g., user ID)                        |
| - name: User's name                                    |
| - iat: Issued at (timestamp for when token was issued)|
| - exp: Expiration time (timestamp)                    |
| - other custom claims can be added here as needed     |
+-------------------------------------------------------+
|                       Signature                        |
| -----------------------------------------------------  |
| HMACSHA256(                                          |
|   base64UrlEncode(header) + "." +                    |
|   base64UrlEncode(payload),                           |
|   your-256-bit-secret)                                |
| - Used to verify that the sender of the JWT is who it  |
|   claims to be and to ensure that the message wasn't   |
|   changed along the way.                               |
+-------------------------------------------------------+
```

### Example JWT

Here’s an example JWT string that encapsulates the above components:

```plaintext
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.\
eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.\
SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

### Explanation of the Example JWT

1. **Header**:
   - **alg**: Indicates the algorithm used (HMAC SHA-256).
   - **typ**: Indicates the type of the token (JWT).
  
2. **Payload**:
   - **sub**: Identifier for the subject of the token (user ID).
   - **name**: A claim that represents the user's name.
   - **iat**: Indicates when the token was issued (in UNIX timestamp format).

3. **Signature**:
   - Combines the base64Url encoded header and payload along with a secret key to produce a signature.

### Related Flags/Headers (for JWT usage)

- **Authorization**: Bearer tokens are typically sent in the Authorization header when making requests to protect resources.
- **exp**: Expiration time of the token, limiting how long the token is valid.
- **nbf**: Indicates that the token is not valid before a certain time.
- **iat**: Issued at-time for the token.
- **jti**: Unique identifier for the token.

Using JWTs allows for secure transmission of information between parties and can be verified and trusted since they are digitally signed.

Certainly! Below is the organized table with headers clearly delineating the **Problem** and **Solution** columns, along with a brief introduction for clarity.

### JWT Security Issues and Solutions

| **Problem**                            | **Example**                                                                                    | **Solution**                                                                                                     |
|----------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| **Signature Algorithm None Attack**    | An attacker modifies the JWT header to use `alg: "none"` and removes the signature, allowing the token to be accepted without verification. | Always validate the `alg` field; do not accept unsigned tokens. Implement an allowlist of expected algorithms.   |
| **Token Expiration Mismanagement**     | A token is still accepted for an extended period, even after a user has logged out, potentially allowing unauthorized access. | Implement a short expiration time (`exp`) and refresh tokens using proper token management strategies.           |
| **Replay Attacks**                    | An attacker captures a valid token and reuses it to gain unauthorized access.                  | Use nonce values or implement token binding to associate tokens with specific sessions or devices.               |
| **Token Storage Vulnerabilities**      | Tokens stored in insecure places (e.g., localStorage) can be accessed by malicious scripts.   | Store tokens securely using HttpOnly and Secure cookies to prevent XSS and CSRF attacks.                        |
| **Lack of Revocation Mechanism**      | If a token is compromised, there is no way to revoke it before expiration.                    | Maintain a blacklist or a revocation list of tokens, or alternatively, use short-lived tokens with refresh tokens. |
| **Excessive Token Size**              | Including too many claims can lead to large token sizes, affecting performance and network efficiency. | Limit claims to only what's necessary for the application and avoid excess claims and metadata.                 |
| **Weak Secret Key**                   | Using a weak or easily guessable secret key makes it easier for attackers to forge tokens.    | Use a strong, complex secret key. Employ key rotation policies and consider using asymmetric keys for added security. |
| **Misconfigured Audience Claims**      | Accepting a token issued for a different audience (aud) could lead to unauthorized access.    | Validate the `aud` claim properly and enforce that tokens are only accepted for the expected audience.           |
| **Insecure Transport**                 | Sending JWTs over non-secure channels (i.e., HTTP instead of HTTPS) can lead to interception. | Always use HTTPS for all communication involving JWTs to protect against man-in-the-middle attacks.              |
| **Lack of Claims Validation**          | Failing to validate required claims (e.g., `iss`, `exp`) results in accepting invalid tokens. | Always validate claims upon token usage and ensure necessary claims are present and correct before processing.  |

Here's a sorted comparison table of RSA (Rivest-Shamir-Adleman) and HMAC (Hash-based Message Authentication Code), along with other related cryptographic methods. The table highlights their characteristics, use cases, strengths, weaknesses, and a comparative analysis regarding their vulnerability to attacks.

| **Cryptographic Method** | **Type**                | **Key Length**                | **Strengths**                                    | **Weaknesses**                                     | **Use Cases**                               | **Better for Attacking** |
|--------------------------|-------------------------|-------------------------------|--------------------------------------------------|---------------------------------------------------|--------------------------------------------|--------------------------|
| **RSA**                  | Asymmetric encryption    | Typically 2048-4096 bits     | High security with large key sizes, widely used for secure key exchange | Slower than symmetric; vulnerability to certain attacks if key size is small | Secure email, digital signatures, key exchange | Moderate (depends on implementation)  |
| **HMAC**                 | Symmetric authentication  | Based on hash function (e.g., SHA-256) | Fast, provides strong integrity and authenticity with a secret key | Shared secret key must be protected; not suitable for non-repudiation | API authentication, data integrity verification | Low (strong against attacks with proper key protection) |
| **AES**                  | Symmetric encryption      | 128, 192, or 256 bits       | Fast, secure, widely adopted, efficient with big data | Requires secure key management; vulnerable if key is weak or not stored properly | Data encryption, VPNs, secure storage      | Low (if implemented correctly) |
| **ECDSA**                | Asymmetric digital signature | Typically 256, 384 bits    | Efficient with shorter keys compared to RSA; strong security | Complex implementation; issues with certain curves have led to vulnerabilities | Digital signatures, software distribution | Moderate (depends on key management) |

In terms of **which is better for attacking**, both are designed to prevent unauthorized access and attacks. However, poorly implemented systems using RSA without proper key management practices could be more susceptible to attacks compared to a well-implemented HMAC system under proper conditions.
