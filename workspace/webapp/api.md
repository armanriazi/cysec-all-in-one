# Introduction of API

## DOM

**The Broken Access Like DOM** (Domain) in security systems refers to **a vulnerability that allows attackers to bypass authentication** mechanisms or gain unauthorized access to sensitive resources within an organization's network. This type of vulnerability often occurs when there are weaknesses in how user accounts, permissions, or access controls are managed across different domains or systems.

### How it works

1. Multiple domains or systems exist within an organization's network.
2. Each domain has its own set of users and access controls.
3. There are inconsistencies or gaps in how these access controls are implemented or enforced across domains.
4. An attacker exploits these inconsistencies to gain access to a domain they shouldn't have access to.

### Examples of vulnerabilities

- Weak password **policies** across domains
- **Inadequate multi-factor** authentication implementation
- Incorrectly configured firewall **rules**[S1]
- **Unpatched**[S1] vulnerabilities in applications used across domains
- **Misconfigured**[S1] identity federation services

### Impact on security

The Broken Access Like DOM vulnerability can lead to significant **security risks**:

- **Unauthorized access** to sensitive data
- Potential **lateral movement** within the network
- Increased risk of **data breaches**
- **Difficulty in tracking** and managing user activities across domains
- **Compliance issues** due to inadequate access control measures

### Mitigation strategies

To address this vulnerability, organizations should implement:

- Centralized **identity management** solutions
- Consistent **access control policies** across all domains
- **Regular audits** and **penetration testing**
- Implementation of least **privilege principle**
- **Continuous monitoring** of user activities and access patterns

### Best practices

- **Implement a zero-trust model** for network access

- Use **role-based access control** consistently across all domains
- Conduct regular **security assessments** and **compliance checks**
- **Educate employees** about the importance of secure practices across all systems
- Keep all software and systems **up-to-date** with the latest security patches

By understanding and addressing the Broken Access Like DOM vulnerability, organizations can significantly strengthen their overall security posture and protect against various types of cyber threats.

## XSS

The named XSS (Cross-Site Scripting) attack in security systems is known as **"Stored Cross-Site Scripting" or "Persistent Cross-Site Scripting."** This type of attack involves storing malicious scripts **on a website** that will be executed by other users when they visit the page.

### Characteristics of Stored XSS

- The attacker injects malicious **JavaScript code into a database or file system** that is accessed by the web application.
- The injected script remains stored on the server until it is retrieved and executed by a user's browser.
- It can affect all users who access the compromised content, regardless of whether they have an account or not.

### Examples of Stored XSS Attacks

- Comment sections where users can **post comments**[S2] without moderation

- **File upload**[S1] systems where files are stored on the server and displayed to others

- **Search functionality that displays results from a database**[S1]

### Prevention Strategies

- Implement proper **input validation and sanitization at every point where user data is processed**
- Use **Content Security Policy (CSP)**[S1] to restrict which sources of content are allowed to be executed
- Regularly **update and patch** web applications to fix vulnerabilities

- **Educate users** about the risks of clicking on suspicious links or downloading attachments from unknown sources

### Impact of Stored XSS

- Can lead to **unauthorized access** to sensitive data
- Allows attackers to **steal user sessions or cookies**[S1]
- Enables malicious **redirections to phishing sites or malware downloads**
- Can **compromise the integrity** of the entire web application

Stored XSS attacks are particularly dangerous because they can affect users who didn't interact with the attacker directly, making them a significant threat to overall system security.

## SSRF

### What is SSRF?

SSRF stands for **Server-Side Request Forgery**[S3]. It is a type of web application vulnerability where an attacker can induce the web application to send a request to any arbitrary internal or external server, potentially exposing internal network services or data.

### How SSRF works

1. An attacker sends a specially **crafted HTTP request**[S1] to the vulnerable web application.
2. The web application processes the request and makes another request to a server specified by the attacker.
3. The attacker can **manipulate the request** to target internal servers, databases, or other sensitive resources.

### Types of SSRF attacks

1. Internal SSRF: Targets internal servers within the organization's network.
2. External SSRF: Targets external servers outside the organization's network.
3. **Blind SSRF: Occurs when the application doesn't return the response content to the attacker.**

### Examples of SSRF attacks

1. Attacker **targets internal DNS servers**[S1] to obtain sensitive information.
2. Attacker **exploits internal web servers** to steal data or inject malware.
3. Attacker **manipulates the application** to connect to unintended external services.

### Prevention strategies

1. **Validate and sanitize** all user inputs.
2. Implement strict **access controls** on internal services.
3. Use **Content Security Policy (CSP)** to restrict where resources can be loaded from.
4. Implement **rate limiting and IP blocking**.
5. Regularly **update and patch** web applications.

### Key considerations

- SSRF can lead to significant security risks if **left unchecked**.
- It often requires careful **analysis of application behavior** to detect.
- Proper input validation and output **encoding are crucial defenses against SSRF**.

## Property Authority

The named property authority attack is a type of vulnerability that can occur in various security systems, particularly those relying on access control mechanisms. This attack **exploits weaknesses in how permissions or authorities are assigned and managed within a system.**

### How it works

In a typical scenario:

1. **An attacker gains unauthorized access** to a system or network.
2. They discover a way to manipulate or **alter the named properties (permissions)** associated with user accounts or resources.
3. By modifying these properties, **the attacker can elevate their privileges** or gain access to restricted areas without being detected.

### Examples of affected systems

This type of attack can affect various types of security systems, including:

- Access Control Systems (**ACS**)
- Identity and Access Management (**IAM**) solutions
- Network Security Groups (**NSGs**)
- **Cloud**-based security platforms

### Mitigation strategies

To prevent or mitigate named property authority attacks:

- Implement strict access controls and **least privilege principles**
- **Regularly audit** and **review user permissions**
- Use role-based access control (**RBAC**) instead of static permissions
- Implement multi-factor authentication (**MFA**) for all users
- Conduct regular **penetration testing** and **vulnerability assessments**

### Real-world implications

Named property authority attacks have significant real-world implications:

- **Data breaches**: Attackers may gain unauthorized access to sensitive data.
- **System compromise**: Malicious actors could potentially take control of critical systems.
- **Compliance issues**: Organizations may face regulatory penalties for failing to protect user data and system integrity.

## APIs

### Named API Vulnerabilities

1. Insecure Direct Object Reference (**IDOR**):
   - Occurs when an application provides **direct access to objects based on user-supplied input** [3].
   - Attackers can bypass authorization and access resources in the system directly, such as database records or files [3].

2. Broken Object Level Authorization (**BOLA**):
   - Similar to IDOR, BOLA is defined as "IDOR in APIs" [3].
   - **APIs often expose endpoints handling object identifiers, creating a wide attack surface**[S1] [3].

3. Missing Function Level Access Control (**MFLAC**):
   - **Refers to broken access control on functions rather than objects** [3].
   - Web applications should **verify function-level access rights** for all requested actions by any user [3].

4. Broken Access Control (**BAC**):
   - Represents a security **flaw within applications** that allows individuals to gain access to data and functions they are not authorized for [1].
   - Can occur due to weak or **improperly implemented access control measures** [1].

### Key Considerations

- These vulnerabilities often result from **misconfigurations, insufficient testing, or inadequate enforcement of access control mechanisms** [1].
- They can lead to unauthorized data exposure, full system compromise, and other security issues [2].
- Common weaknesses **associated with broken access control** include insecure direct object references, insufficient authentication, and misconfigured access control mechanisms [1].

### Prevention Strategies

1. Implement secure **authentication and authorization** mechanisms from the outset [1].
2. **Validate user inputs** and declare authorized access at the code level [1].
3. Include access control unit and integration **tests** in testing routines [1].
4. Enforce role-based access control (**RBAC**) and attribute-based access control (**ABAC**) mechanisms [1].
5. Ensure effective access control is enforced on the **trusted server-side** or **server-less API** [1].

## CSRF

### What is CSRF?

**CSRF stands for Cross-Site Request Forgery**. It is a type of web application security vulnerability that allows an attacker to trick a web application into performing unintended actions. Specifically, it occurs when an attacker **tricks a user into submitting a form or clicking a link that performs an unintended action** on behalf of the user.

### How CSRF works

1. An attacker creates a malicious website or **email that contains a hidden form or button**[S1].
2. The form or button submits a request to the victim's trusted site.
3. The request is executed without the user's knowledge or consent.

### Key points about CSRF

- **It relies on the user** already being authenticated on the targeted site.
- **It doesn't involve stealing credentials, but rather manipulating the user's existing session.**
- It's often **combined with other attacks** to increase its impact.

### Examples of CSRF attacks

1. Changing account **settings**
2. Transferring **funds**
3. **Deleting** content
4. **Modifying** personal information

### Prevention techniques

1. **Implementing the Same-Origin Policy**
2. **Using tokens or cookies that are unique per session**
3. **Validating referrer headers**
4. **Using double-submit cookies**
5. **Implementing Content Security Policy (CSP)**

### Best practices

- Always **validate incoming requests**, especially those involving sensitive operations.
- **Use tokens or cookies that are unique per session.**
- **Educate users** about the risks of clicking suspicious links or opening attachments from unknown sources.
- Regularly **update and patch** your web application to fix known vulnerabilities.

---

# Understanding API Vulnerabilities: BOLA, IDOR, BAC, and MFLAC

In the realm of web application security, several vulnerabilities can arise from improper authorization checks. Understanding these vulnerabilities is crucial to safeguard sensitive data from unauthorized access. Among these, **Broken Object Level Authorization (BOLA)**, **Insecure Direct Object References (IDOR)**, **Broken Access Control (BAC)**, and **Missing Function Level Access Control (MFLAC)** are critical issues that can lead to severe consequences if not addressed. This comprehensive guide will delve deeper into each of these vulnerabilities, accompanied by real-world scenarios, detailed explanations, and practical testing methods using tools like **Metasploit** and **Burp Suite**.

Sure! Here is the updated table with the addition of **BFLA** (Business Logic Abuse):

## Mitigation Strategies for Vulnerabilities

| Vulnerability                         | MITRE ATT&CK TTPs                         | Detailed Descriptions of Mitigations                                                                 | Reflected on Pattern                               |
|---------------------------------------|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------|
| **BOLA** | **T1070** - Indicator Removal on Host   | Ensure that access checks are enforced for each request, verifying that the requesting user is authorized to access the specified resource. Use unique and unpredictable identifiers for resources to prevent enumeration attacks. | ├─ T1070: Event Logged<br>│   ├─ Sub-Technique: Implement Controls<br>│   │   └─ Procedure: Verify Log Entries             |
| **IDOR** | **T1069** - Permission Groups Discovery  | Use non-predictable IDs and check permissions rigorously before granting access to any user document or resource. Implement input filtering/validation to ensure correct format for identifiers. | ├─ T1069: User Permission Justification<br>│   ├─ Sub-Technique: Validate Identifiers<br>│   │   └─ Procedure: Check Role Permissions        |
| **BAC**  | **T1075** - Pass the Hash   | Implement a middleware that verifies user roles before allowing access to sensitive APIs. Ensure consistent role checks at all entry points for critical operations. | ├─ T1075: Security Token Verification<br>│   ├─ Sub-Technique: Middleware Integration<br>│   │   └─ Procedure: Role Check at Entry Point     |
| **MFLAC** | **T1068** - Exploit Public-Facing Application | Apply access control checks at the start of sensitive functions to verify user permissions. Utilize express middleware for consistent access validation across different routes. | ├─ T1068: Function Permission Requirement<br>│   ├─ Sub-Technique: Validate User Actions<br>│   │   └─ Procedure: Apply Access Controls on Functions |
| **BFLA** | **T1071** - Application Layer Protocol | Implement strict input validation to ensure that business logic is not being manipulated. Use rate limiting to control the number of requests and establish anomaly detection algorithms to identify suspicious patterns. | ├─ T1071: Validate Business Logic<br>│   ├─ Sub-Technique: Input Validation<br>│   │   └─ Procedure: Anomaly Detection and Rate Limiting  |

### BOLA Mitigation Strategies

**BOLA:**  <br>1. Implement strict authorization checks to ensure users can only access their resources.<br>2. Use unique identifiers for user-specific endpoints that require authorization checks.<br>3. Leverage role-based access control (RBAC) or attribute-based access control (ABAC).

**IDOR:** <br>1. Replace predictable identifiers with non-sequential, random identifiers.<br>2. Enforce strict access controls based on user roles.<br>3. Conduct input validation to ensure that users cannot manipulate identifiers.

**BAC:** <br>1. Implement role-based access controls to restrict sensitive operations.<br>2. Validate user roles on every sensitive operation.<br>3. Utilize secure coding practices to prevent bypassing checks (e.g., validating with sessions and tokens).

**MFLAC:**  <br>1. Enforce function-level access controls by validating user permissions before executing sensitive actions.<br>2. Utilize middleware for consistent access checks across all routes.<br>3. Regularly audit roles and permissions to ensure they align with business processes.

**BFLA** is a security vulnerability that occurs when an application fails to properly enforce access controls for different functions or features based on user roles. This flaw allows unauthorized users to access functionalities they should not be allowed to use, leading to potential security breaches.

To prevent BFLA, enforce authorization checks on the server side to ensure that each user has the appropriate permissions before executing sensitive functions. Regular security testing should also be conducted to identify and fix any access control issues.

# All types of vulnerabilities of APIs

## Broken Function Level Authorization (BFLA)

Consider a web application with user roles such as "Admin" and "User." The application has a function to delete user accounts, which should only be accessible to Admins.

- **Normal Behavior**:
  - Admin User: Can access the delete functionality at `DELETE /users/{id}`.
  - Regular User: Should be restricted from accessing this function.

- **Exploit**:
  An attacker who has logged in as a regular user discovers the delete endpoint and sends a request like:

  ```
  DELETE /users/123
  ```

  Since the application lacks proper authorization checks, the regular user is able to delete the account of user ID 123, which they should not have permission to do.

## Insecure Direct Object References (IDOR)

IDOR is a common security vulnerability that occurs when an application exposes direct access to objects such as files or database records without proper authorization checks. Attackers can exploit this vulnerability by manipulating the references to access unauthorized data.
Basics of what IDOR is, how it works, its risks, and methods for detection and prevention.

### Sample Response

**What is IDOR?**

Insecure Direct Object Reference (IDOR) is a type of security vulnerability found in web applications that occurs when an application exposes a reference to an internal object, such as a database record or a file, without proper authorization checks. This allows an attacker to manipulate the reference to access or perform actions on objects they are not authorized to interact with.

**How IDOR Works:**

IDOR typically involves a situation where an application uses user-supplied input to directly reference internal objects. For example, consider a URL that allows users to access their profile:

```
http://example.com/user/profile?id=123
```

In this example, `id=123` might refer to a unique user record in the database. If the application does not verify whether the authenticated user has permission to access that specific user profile, an attacker could change the ID in the URL to access another user's profile:

```
http://example.com/user/profile?id=124
```

If the application lacks proper authorization controls, the attacker could view, modify, or delete data belonging to another user. This can lead to unauthorized data access, data exfiltration, or other harmful consequences.

**Risks Associated with IDOR:**

- **Data Exposure:** Sensitive data from other users can be accessed without authorization.
- **Data Manipulation:** Attackers may modify or delete records they shouldn't be able to.
- **Reputation Damage:** Organizations may suffer reputational harm if users' data is compromised.
- **Regulatory Compliance Issues:** Applications that fail to protect user data may face legal and regulatory repercussions.

**Detection and Prevention:**

To detect IDOR vulnerabilities, one can perform manual testing by manipulating parameters in HTTP requests and observing the application's response. Automated tools like Burp Suite or OWASP ZAP can also help in scanning for such vulnerabilities.

**Preventive Measures:**

- **Access Control Checks:** Always validate that the user has permission to access the requested objects, regardless of the input provided.
- **Indirection:** Use indirect references or tokens instead of exposing direct object references. For instance, instead of using `user_id`, you could use a token that maps to the user in the backend.
- **Logging and Monitoring:** Implement logging for access requests to detect any unauthorized access attempts.

### How to Detect IDOR Vulnerabilities

Here are some steps and methods to detect IDOR vulnerabilities systematically:

#### 1. **Understanding IDOR**

- Get familiar with how the application exposes resources. This often happens in URLs or API parameters where object IDs are passed, such as:
  - `/user/profile?id=123`
  - `/invoice/details?invoice_id=456`
- The vulnerability arises when an attacker can change the ID (e.g., from `123` to `124`) to access data belonging to another user.

#### 2. **Manual Testing**

- **Identify Parameters**: Make note of any parameters in the application that reference internal objects.
- **Manipulate Requests**:
  - Use a browser's developer tools to inspect and intercept requests.
  - Modify object IDs to attempt to access other users' data.
- **Check for Response**: If you receive a response containing information that does not belong to your user, it's likely an IDOR vulnerability.

#### 3. **Automated Scanning Tools**

- Use security testing tools that can detect IDOR vulnerabilities. Some popular tools include:
  - **Burp Suite**: Can be configured to automatically scan for IDOR by testing parameter values.
  - **OWASP ZAP (Zed Attack Proxy)**: Can also be used for testing web applications and includes features for detecting IDOR.
  - **Acunetix, Nessus**: Other scanners that can include IDOR checking as part of their scanning capabilities.

#### 4. **Burp Suite Example**

- **Intercept HTTP Requests**: Configure Burp to intercept requests sent from your browser.
- **Send to Repeater**: Send requests to the Repeater tool where you can modify parameters easily.
- **Modify Parameter**: Change the parameter value (e.g., the user ID or invoice ID) to see if you can access unauthorized data.
- **Analyze Responses**: Check the responses to see if sensitive information from other users is returned.

#### 5. **Code Review (For Developers)**

- Perform security code reviews, focusing on how the application handles user input for object references.
- Ensure proper access controls are implemented for object access, verifying users' permissions before serving data.

### Example of Testing for IDOR

IDOR vulnerabilities can pose severe risks, especially in applications handling sensitive information. Regular testing and securing object references with proper authorization checks and roles can significantly reduce the risk of IDOR vulnerabilities. Security training for developers on secure coding practices is also essential to prevent such vulnerabilities from being introduced during development.
Suppose you have a URL like this:

```plaintext
http://example.com/user/profile?id=10
```

1. **Initial Request**: You send the above request and receive the profile details for user ID `10`.
2. **Manipulate the ID**: Change the `id` parameter to `11`, `12`, etc.:
   - `http://example.com/user/profile?id=11`
   - `http://example.com/user/profile?id=12`
3. **Analyze Responses**: If you receive the details of other user profiles (`id=11` or `id=12`), you have found an IDOR vulnerability.

Yes, Metasploit can be used for testing web applications, particularly in the context of penetration testing and identifying vulnerabilities. While Metasploit is primarily known for its exploit database and capabilities against operating systems and network services, it also has various auxiliary and exploit modules specifically designed for web applications.

### IDOR with Metexploit

### Metexploit

Metasploit doesn't have a built-in module for testing IDOR vulnerabilities specifically. However, you can use Metasploit in combination with other tools or techniques to identify and exploit IDOR vulnerabilities. Here's a general approach:

### Using Metasploit for Web Application Testing

Here are some ways you can use Metasploit for web application testing:

#### 1. **Web Scanning Modules**

Metasploit includes multiple auxiliary modules that can perform various types of scans against web applications. Examples include:

- **SQL Injection Detection**:

  ```bash
  use auxiliary/scanner/http/sql_injection
  set RHOSTS <target>
  set TARGETURI /login.php?username=admin&password=admin
  run
  ```

- **Directory and File Enumeration**:

  ```bash
  use auxiliary/scanner/http/dir_scanner
  set RHOSTS <target>
  set RPATH /path/to/directory
  run
  ```

- **XSS Testing**:
  Metasploit has modules that can help identify potential Cross-Site Scripting (XSS) vulnerabilities.

#### 2. **Exploit Modules for Web Frameworks**

Some modules are designed specifically to exploit vulnerabilities in web applications and frameworks, such as:

- **WordPress Exploits**: Exploits for known vulnerabilities in WordPress plugins or themes.
- **CMS Exploits**: Modules for exploiting vulnerabilities in various Content Management Systems (CMS).

#### 3. **Metasploit’s Web Application Testing Utilities**

In addition to exploiting vulnerabilities, Metasploit provides several utilities for web application testing, including:

- **Metasploit Pro**: If you're using the Pro version of Metasploit, it includes additional web application security testing features and capabilities to integrate with tools like Burp Suite.

- **Web Application Attack Framework**: Metasploit includes a set of tools (Metasploit Community edition) for web application attack simulations.

#### 4. **Integration with Other Tools**

You can also combine Metasploit with other tools for a more robust web application testing experience:

- **Burp Suite**: You can use Burp to intercept requests and then send them to Metasploit for exploitation.
- **OWASP ZAP**: Similar to Burp, ZAP can be used for initial scanning and interception of requests that can then be exploited using Metasploit.

### Example of Testing a Web Application

1. **Initialize Metasploit**:

   ```bash
   msfconsole
   ```

2. **Search for Web Modules**:

   ```bash
   search type:auxiliary http
   ```

3. **Select a Module**:

   ```bash
   use auxiliary/scanner/http/sql_injection
   ```

4. **Set Target and Run**:

   ```bash
   set RHOSTS <target>
   set TARGETURI /example.php?id=1
   run
   ```

5. **Check Results**: Analyze the output to determine if the web application is vulnerable and plan further actions accordingly.

## Broken Access Control (BAC)

Broken Access Control (BAC) refers to a security vulnerability where an application fails to properly enforce restrictions on what authenticated users can do. This allows attackers to access unauthorized functionality or data.

### Understanding BAC

BAC occurs when access control checks are missing or improperly implemented. Common examples include:

- Bypassing access control checks by modifying the URL or HTML page
- Allowing privilege escalation by changing user role parameters
- Accessing API endpoints without proper authorization
- Metadata manipulation like tampering with JWT tokens

### Key Risks

- **Unauthorized Access:** Users can access restricted functionality or data
- **Privilege Escalation:** Users can elevate their privileges to admin/higher roles
- **Information Disclosure:** Sensitive data exposed to unauthorized users
- **Data Manipulation:** Unauthorized modification of data

### Detection Methods

1. **Manual Testing:**
   - Attempt to access restricted URLs/endpoints
   - Modify user roles and permissions in requests
   - Test vertical and horizontal privilege escalation

2. **Automated Scanning:**
   - Use web vulnerability scanners
   - Implement automated security testing
   - Deploy continuous security monitoring

### Prevention Strategies

- **Implement Strong Access Controls:**
  - Use role-based access control (RBAC)
  - Enforce principle of least privilege
  - Validate permissions on server-side
  
- **Security Best Practices:**
  - Deny access by default
  - Log access control failures
  - Use secure session management
  - Implement rate limiting

### Example Testing Scenario

```http
# Original admin request
GET /admin/users HTTP/1.1
Authorization: Bearer <admin_token>

# Attempting unauthorized access
GET /admin/users HTTP/1.1
Authorization: Bearer <regular_user_token>
```

Regular security testing and proper implementation of access controls are essential to prevent BAC vulnerabilities and protect sensitive resources.
By implementing robust authorization checks and regularly testing for vulnerabilities, applications can mitigate the risks associated with BOLA and protect sensitive user data.

## Broken Object Level Authorization (BOLA)

BOLA is a critical security vulnerability that arises when an application does not properly enforce authorization checks for object-level access. This flaw allows attackers to manipulate requests to access or modify objects they are not authorized to interact with.

### Understanding BOLA

BOLA occurs when an application fails to verify whether the user has the necessary permissions to perform actions on a specific object. For example, consider an API endpoint that retrieves user details:

```
GET /api/user/details?user_id=123
```

If the application does not enforce proper authorization checks, an attacker could change the `user_id` parameter to access another user's details:

```
GET /api/user/details?user_id=124
```

### Risks Associated with BOLA

- **Unauthorized Access:** Attackers can access sensitive information of other users.
- **Data Manipulation:** Unauthorized modification or deletion of data.
- **Compliance Violations:** Breaches of data protection regulations.
- **Reputation Damage:** Loss of trust from users due to data breaches.

### Detecting and Preventing BOLA

#### Detection

1. **Manual Testing:**
   - Identify endpoints that expose object references.
   - Manipulate object identifiers in requests to test access control.
   - Verify if unauthorized data is accessible.

2. **Automated Tools:**
   - Use tools like Burp Suite or OWASP ZAP to scan for BOLA vulnerabilities.
   - Configure tools to test object-level authorization by altering request parameters.

#### Prevention

- **Implement Access Controls:** Ensure that every request is checked against the user's permissions for the specific object.
- **Use Indirect References:** Employ indirect references or tokens instead of direct object identifiers.
- **Regular Audits:** Conduct regular security audits and code reviews to identify and fix authorization issues.
- **Security Training:** Educate developers on secure coding practices to prevent BOLA vulnerabilities.

### Example of Testing for BOLA

Consider an API endpoint:

```plaintext
GET /api/order/details?order_id=1001
```

1. **Initial Request:** Access the endpoint with a valid `order_id` to retrieve order details.
2. **Manipulate the ID:** Change the `order_id` to test unauthorized access:
   - `GET /api/order/details?order_id=1002`
3. **Analyze Responses:** If details of another order are returned, a BOLA vulnerability is present.

By implementing robust authorization checks and regularly testing for vulnerabilities, applications can mitigate the risks associated with BOLA and protect sensitive user data.

## Missing Function Level Access Control (MFLAC)

Missing Function Level Access Control (MFLAC) is a security vulnerability that occurs when an application does not properly enforce access controls at the function level. This allows unauthorized users to invoke functions or execute operations that they should not have access to.

### Understanding MFLAC

MFLAC arises when the application fails to verify whether the user has the necessary permissions to execute a specific function. For example, consider an API endpoint that allows users to delete accounts:

```
DELETE /api/user/delete
```

If the application does not enforce proper authorization checks before executing the delete operation, an attacker could invoke this function to delete accounts they are not authorized to delete.

### Risks Associated with MFLAC

- **Unauthorized Operations:** Attackers can perform actions they are not permitted to, such as deleting or modifying data.
- **Data Integrity Issues:** Critical data can be altered or destroyed without proper authorization.
- **Compliance Violations:** Breaches of data protection regulations.
- **Reputation Damage:** Loss of trust from users due to security incidents.

### Detecting and Preventing MFLAC

#### Detection

1. **Manual Testing:**
   - Identify endpoints that perform sensitive operations.
   - Attempt to invoke these functions without proper authorization.
   - Verify if unauthorized operations are possible.

2. **Automated Tools:**
   - Use tools like Burp Suite or OWASP ZAP to scan for MFLAC vulnerabilities.
   - Configure tools to test function-level authorization by attempting unauthorized operations.

#### Prevention

- **Implement Access Controls:** Ensure that every function call is checked against the user's permissions.
- **Use Role-Based Access Control (RBAC):** Define roles and permissions clearly and enforce them at the function level.
- **Principle of Least Privilege:** Grant users only the minimum level of access necessary to perform their tasks.
- **Regular Audits:** Conduct regular security audits and code reviews to identify and fix authorization issues.
- **Security Training:** Educate developers on secure coding practices to prevent MFLAC vulnerabilities.

### Example of Testing for MFLAC

Consider an API endpoint:

```plaintext
DELETE /api/user/delete
```

1. **Initial Request:** Attempt to delete a user account without proper authorization.
2. **Analyze Response:** If the account is deleted successfully, a MFLAC vulnerability is present.

By implementing robust authorization checks and regularly testing for vulnerabilities, applications can mitigate the risks associated with MFLAC and protect sensitive user data.
