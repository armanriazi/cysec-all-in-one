## OWASP

The **Open Web Application Security Project (OWASP)** maintains a list of the top security risks for web applications, known as the **OWASP Top Ten**. This list is widely recognized in the industry and serves as a guide for organizations to enhance their web application security practices.

### OWASP Top Ten security risks

| **OWASP Top Ten Risks**                   | **Description**                                                                                                           | **Mitigation Strategies**                                     |
|-------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
| **1. Broken Access Control**              | Improperly configured access controls that allow unauthorized users to access restricted resources.                       | Use secure access control measures; implement role-based access control (RBAC/ABAC).  |
| **2. Cryptographic Failures**             | Inadequate protection of sensitive data due to poor encryption practices or use of obsolete algorithms.                    | Use strong encryption protocols; manage cryptographic keys securely.            |
| **3. Injection**                          | Flaws that allow attackers to send untrusted data (e.g., SQL, NoSQL, command injections) to interpreters.                 | Use parameterized queries; validate and sanitize user inputs.                  |
| **4. Insecure Design**                   | Lack of security design principles leading to vulnerabilities.                                                             | Apply security by design principles; threat modeling during development.      |
| **5. Security Misconfiguration**         | Misconfigured security settings or unnecessary default options in applications/web servers.                                | Regularly review configurations; automate security configuration checks.      |
| **6. Vulnerable and Outdated Components** | Use of components (libraries, frameworks) that are outdated or known to have vulnerabilities.                              | Regularly update and patch components; use automated tools for dependency checking. |
| **7. Identification and Authentication(IAM) Failures** | Issues with the identification and authentication processes, leading to unauthorized access.                               | Implement strong password policies; use multi-factor authentication (MFA).   |
| **8. Software and Data Integrity Failures** | Inadequate measures to protect the integrity of software and data from unauthorized modification or corruption.            | Use code signing; implement integrity checks for data.                          |
| **9. Security Logging and Monitoring Failures** | Lack of proper logging and monitoring that allows attackers to cover their tracks or misuse a system.                      | Implement comprehensive logging and alerting mechanisms; regularly review logs.  |
| **10. Server-Side Request Forgery (SSRF)** | Vulnerability that allows an attacker to send unauthorized requests from the server to internal resources.                  | Validate and sanitize all server-side requests; implement strict whitelisting.  |

The OWASP Top Ten serves as an essential resource for understanding the most critical security risks to web applications, helping organizations prioritize their security efforts and implement effective mitigation strategies.
