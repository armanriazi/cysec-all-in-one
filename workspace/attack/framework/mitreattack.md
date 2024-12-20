## MITRE ATT&CK

The abbreviation for [MITRE ATT&CK](https://attack.mitre.org/) stands for "MITRE Adversarial Tactics, Techniques, and Common Knowledge."
The MITRE ATT&CK framework includes over 424 techniques, which represent the various ways in which attackers can accomplish their objectives across different phases of the attack lifecycle. These techniques are classified under specific tactics, such as initial access, execution, persistence, privilege escalation, defense evasion, credential access, discovery, lateral movement, collection, exfiltration, and impact.

### MITRE ATT&CK Steps

When applying a Red Teaming methodology based on MITRE ATT&CK techniques, the process typically includes the following steps:

1. **Planning**: Define the scope and objectives of the Red Team engagement, including the systems to be tested and the rules of engagement.

2. **Mapping Tactics and Techniques**: Use the ATT&CK framework to identify relevant tactics (the goals of an attack, such as initial access, execution, persistence, etc.) and techniques (specific methods to achieve those goals, like phishing, remote code execution, etc.).

3. **Execution**: Conduct simulated attacks by employing the tactics and techniques outlined in the ATT&CK framework. This may involve red teaming activities such as social engineering, network exploitation, or lateral movement within the organization.

4. **Assessment**: Assess the effectiveness of existing security controls against the simulated attacks and measure the organization's ability to detect and respond to them.

5. **Reporting and Remediation**: Provide detailed reports on the findings, including vulnerabilities discovered, specific techniques used, and recommendations for improving security posture. Work with the organization to develop a remediation plan.

6. **Follow-Up**: After remediation, conduct follow-up tests to verify that vulnerabilities have been addressed and that security measures are effective.

By leveraging MITRE ATT&CK in Red Teaming, organizations can gain a better understanding of their security weaknesses and improve their defenses against potential real-world attacks.

### Comparison Frameworks

| Framework               | Purpose                                        | Key Focus Areas                            | Open Source | Use in Red Teaming    |
|------------------------|------------------------------------------------|-------------------------------------------|-------------|-----------------------|
| **MITRE ATT&CK**       | Knowledge base for understanding adversaries   | Tactics, techniques, procedures (TTPs)   | Yes         | Yes                   |
| **NIST Cybersecurity Framework** | Framework for managing cybersecurity risk | Identify, Protect, Detect, Respond, Recover | Yes       | No                    |
| **Lockheed Martin Cyber Kill Chain** | Structure of phases in a cyber attack | Reconnaissance, Weaponization, Delivery, Exploitation, Installation, Command & Control, Actions on Objectives | No | Limited               |
| **OWASP Testing Guide** | Guidelines for web application security testing | Testing techniques for web vulnerabilities | Yes      | No                    |
| **CIS Controls**       | Best practices for cybersecurity defense      | Specific controls and safeguards           | Yes         | Yes                   |
| **ISO/IEC 27001**     | International standard for information security management | Risk management and security controls      | No          | Limited               |
| **Pyramid of Pain**    | Visual representation of threat intelligence and countermeasures | Emphasizes the cost of defenses vs. attacker costs | Yes  | No                    |

---

### Tools

| Tool Name                     | Description                                                    | Key Functionality                               | Open Source | Relevance to MITRE ATT&CK   | Rate of Usage/Popularity | Beneficial for Job Acquisition |
|-------------------------------|---------------------------------------------------------------|-------------------------------------------------|-------------|------------------------------|--------------------------|---------------------------------|
| **MITRE ATT&CK Navigator**    | A web-based tool for visualizing and utilizing the ATT&CK matrix. | Allows users to view, filter, and annotate ATT&CK techniques. | Yes         | Core tool for mapping TTPs   | High                     | Yes                             |
| **Caldera**                   | An automated adversary emulation system.                      | Simulates attacks based on ATT&CK techniques.  | Yes         | Supports red teaming efforts   | Medium                   | Yes                             |
| **Atomic Red Team**           | A collection of small, testable scripts demonstrating the use of ATT&CK techniques. | Enables testing of specific techniques in a controlled environment. | Yes         | Directly based on ATT&CK      | High                     | Yes                             |
| **Mitre ATT&CK Framework for Cloud** | A specialized version of ATT&CK focused on cloud environments.        | Maps tactics and techniques specific to cloud security scenarios. | Yes         | Extends ATT&CK for cloud security | Medium                   | Yes                             |
| **Red Canary**                | A threat detection tool utilizing ATT&CK techniques for incident response. | Aids in threat detection and response aligned with ATT&CK. | No          | Uses ATT&CK for detection     | Medium                   | Yes                             |
| **Sigma**                     | A generic signature format for SIEM systems that enables threat detection. | Allows the creation of detection rules based on ATT&CK techniques. | Yes         | Compatible with ATT&CK        | High                     | Yes                             |
| **ThreatHunter Playbook**     | A platform for threat hunting that incorporates MITRE ATT&CK mapping. | Provides playbooks tailored to ATT&CK for threat hunting activities. | Yes         | Supports hunter operations against ATT&CK TTPs | Medium                   | Yes                             |
| **MISP** (Malware Information Sharing Platform) | A threat intelligence platform that allows sharing of indicators and TTPs. | Facilitates threat analysis and sharing, incorporating ATT&CK mappings.  | Yes | Integrates ATT&CK TTPs for threat analysis | Medium                   | Yes                             |
| **Pupy**                      | A cross-platform remote administration and post-exploitation tool. | Remote access, command execution, and file transfer across different OS. | Yes         | Supports various ATT&CK tactics, especially lateral movement and command control | Medium                   | Yes                             |
| **Empire**                    | A PowerShell and Python post-exploitation framework.         | Provides a variety of post-exploitation techniques and command execution capabilities. | Yes         | Utilizes numerous ATT&CK techniques for persistence, credential access, etc. | High                     | Yes                             |
| **Impacket**                  | A collection of Python classes for working with network protocols. | Facilitates network protocol manipulation, allowing for authentication and exploitation. | Yes         | Supports a range of ATT&CK techniques like lateral movement and credential access. | High                     | Yes                             |
| **PowerSploit**              | A PowerShell exploitation framework for post-exploitation tasks. | Offers various modules for information gathering, persistence, and defense evasion. | Yes         | Directly relevant to many ATT&CK techniques regarding PowerShell usage. | High                     | Yes                             |
| **Cuckoo Sandbox**              | An automated malware analysis system for observing malware behavior. | Isolates and analyzes suspicious files to identify malware tactics and techniques. | Yes         | Useful for understanding malware behaviors in the context of ATT&CK techniques | High                     | Yes                             |

Certainly! Below is a table summarizing the Tactics from the TTP framework, along with succinct examples for each.

### TTP Tactics with Examples

| **Lockheed Martin Cyber Kill Chain**                 | **Tactic**                     | **Description**                                                  | **Example**                                                      |
|------------------------------------------------------|--------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|
| **Reconnaissance**                                   | **7. Discovery**               | Gathering information about the network or systems.            | Using network scanning tools like Nmap to find open ports.      |
|                                                      | **14. Reconnaissance**         | Gathering intel about the target before attacks.               | Conducting social engineering to learn about company structure.  |
| **Weaponization**                                    | **3. Persistence**             | Maintaining access over time.                                   | Installing a backdoor service that restarts on boot.            |
| **Delivery**                                         | **1. Initial Access**          | Gaining entry into a target system.                             | Phishing email that tricks a user into providing credentials.    |
| **Exploitation**                                     | **2. Execution**               | Running malicious code on a system.                             | PowerShell script downloading and executing malware.             |
|                                                      | **4. Privilege Escalation**   | Gaining elevated access.                                        | Exploiting a vulnerability to gain admin rights on a server.     |
| **Command & Control (C2)**                           | **12. Command and Control (C2)**| Establishing communication with compromised assets.           | Using a remote access tool (RAT) to control infected systems.    |
| **Actions on Objectives**                            | **9. Collection**              | Gathering data of interest.                                     | Collecting sensitive files from a compromised server.           |
|                                                      | **10. Exfiltration**           | Transferring data outside the network.                          | Using FTP to send stolen data to an external server.            |
|                                                      | **11. Impact**                 | Causing damage to systems or data.                              | Encrypting files and demanding ransom (ransomware attack).      |
| **X**                                                | **5. Defense Evasion**        | Avoiding detection by security tools.                           | Obfuscating malware code to evade antivirus signatures.          |
|                                                      | **6. Credential Access**       | Stealing user credentials.                                      | Keylogging to capture usernames and passwords during login.      |
|                                                      | **8. Lateral Movement**        | Moving between systems in a network.                            | Using stolen credentials to access other devices on the network. |
|                                                      | **13. Resource Development**   | Building infrastructure for attacks.                            | Setting up a fake domain to host phishing websites.              |
|                                                      | **15. Measurement**            | Evaluating and adapting tactics based on observed outcomes.     | Analyzing previous attack success rates to refine future tactics. |

### Conclusion

This table highlights key tactics within the TTP framework alongside practical examples, making it easier to understand how each tactic is applied in real-world scenarios. Recognizing these tactics can help organizations strengthen their defenses and improve their incident response capabilities.

Certainly! Below is a pivot table that organizes TTP (Tactics, Techniques, and Procedures) into tactics with corresponding techniques for each category. This format provides a clear view of how each tactic can be implemented through specific techniques.

### TTP Tactics with Techniques

| **Tactic**                     | **Techniques**                                                                                                      |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------|
| **1. Initial Access**          | - Phishing Email                                                                                                   |
|                                | - Exploit Public-Facing Application                                                                                 |
|                                | - Supply Chain Compromise                                                                                           |
| **2. Execution**               | - Command-Line Interface (CLI)                                                                |
|                                | - Scripting (PowerShell, Python)                                                                                   |
|                                | - Exploiting Application Layer Protocols                                                                              |
| **3. Persistence**             | - Registry Run Keys/Startup Folder                                                                                  |
|                                | - Scheduled Tasks                                                                                                   |
|                                | - Services and Drivers                                                                                              |
| **4. Privilege Escalation**   | - Exploitation for Client Execution                                                                                 |
|                                | - Valid Accounts                                                                                                    |
|                                | - Kernel Exploitation                                                                                               |
| **5. Defense Evasion**        | - Timestomping                                                                                                     |
|                                | - Obfuscated Files or Information                                                                                   |
|                                | - Indicator Removal on Host                                                                                         |
| **6. Credential Access**       | - Credential Dumping                                                                                                 |
|                                | - Keylogging                                                                                                        |
|                                | - Brute Force                                                                                                       |
| **7. Discovery**               | - Network Service Scanning                                                                                          |
|                                | - File and Directory Discovery                                                                                      |
|                                | - Account Discovery                                                                                                 |
| **8. Lateral Movement**        | - Remote Desktop Protocol (RDP)                                                                                   |
|                                | - Windows Admin Shares                                                                                              |
|                                | - Pass-the-Hash                                                                                                     |
| **9. Collection**              | - Data from Information Repositories                                                                                          |
|                                | - Data from Local System                                                                                             |
|                                | - Screen Capture                                                                                                    |
| **10. Exfiltration**           | - Exfiltration Over Command and Control Channel                                                                 |
|                                | - Exfiltration Over Web Service                                                                                     |
|                                | - Data Staged                                                                                                       |
| **11. Impact**                 | - Data Encrypted for Impact                                                                                         |
|                                | - Service Stop                                                                                                      |
|                                | - Resource Hijacking                                                                                                 |
| **12. Command and Control (C2)**| - Application Layer Protocol                                                                                       |
|                                | - Custom Command and Control Protocol                                                                               |
|                                | - Web Service                                      |
| **13. Resource Development**   | - Malicious Infrastructure                                                                                          |
|                                | - Tool Development                                                                                                  |
|                                | - Phishing Kits                                                |
| **14. Reconnaissance**         | - Active Scanning                                                                                                    |
|                                | - Passive Scanning                                                                                                   |
|                                | - Open Source Intelligence (OSINT)                                                                                 |
| **15. Measurement**            | - Performance Measurement                                                                                           |
|                                | - Evaluation Metrics                                                                                                |
|                                | - Adversary Tracking                                                                                                 |

This pivot table directly links each TTP tactic to specific techniques, providing a structured approach to understanding how attackers operationalize their methods. By familiarizing organizations with these tactics and techniques, they can enhance their defenses and better prepare for potential threats.

### Some exist open layer for navigator

- [Center-for-threat-informed-defense-veris](https://raw.githubusercontent.com/center-for-threat-informed-defense/attack_to_veris)
- [Center-for-threat-informed-defense-cve](https://github.com/center-for-threat-informed-defense/attack_to_cve)

### MITRE@TACK Workbench

One of the issues that ATT&CK Workbench aims to address is in dealing with **Information overload**.
Complete the sentence: ATT&CK Workbench is a tool designed to containerize the ATT&CK knowledge base, making ATT&CK easier to use and extend throughout the community. This application is **your own Customized instance of the knowledgebase** where you can explore, extend, and annotate ATT&CK data.

[The ATT&CK Workbench](https://github.com/center-for-threat-informed-defense/attack-workbench-frontend) enables a number of important use cases within the ATT&CK community:

Cyber Threat Intelligence: Take notes on techniques, groups, and other objects to collaborate within a threat intelligence team. Update your knowledge base with new mappings as soon as new threat reports are released.
Defensive Planning: Stay up to date with the evolving threat landscape by downloading new releases of ATT&CK automatically. Fill in gaps in open-source reporting by creating new groups and software and seamlessly integrate them into the existing ATT&CK knowledge base.
Red Teaming: Track and manage coverage of Red Team engagements the same way you track your ATT&CK coverage.
Collaboration with ATT&CK and the community: Share your custom datasets with the ATT&CK[community and download datasets created by others.

- [Collection index for subscribtion](https://github.com/mitre-attack/attack-stix-data/blob/master/index.json)

#### Workbench Integration

Integrating with the ATT&CK Navigator allows you to add layers based on customized extensions.

After added your techniques in workbench with references the next step is integrate to platform intelligence and navigator:

- [Integrations](https://github.com/center-for-threat-informed-defense/attack-workbench-frontend/blob/master/docs/integrations.md)

#### PROBLEM

Defenders struggle to integrate their organization’s local knowledge of adversaries and their TTPs with the public ATT&CK knowledge base.

#### SOLUTION

Build an easy-to-use open-source software tool that allows organizations to manage and extend their own local version of ATT&CK and keep it in sync with MITRE’s knowledge base.

#### IMPACT

Drastically reduces the barriers for defenders to ensure that their threat intelligence is aligned with the public ATT&CK knowledge base.

## Subteqniques and Procedures

<details>
<summary> Initial Access Tactics</summary>

```plaintext
├── Tactic 1: Initial Access
│   ├── Technique T1071: Application Layer Protocol
│   │   ├── Sub-Technique T1071.001: Web Protocols
│   │   ├── Sub-Technique T1071.002: File Transfer Protocols
│   │   ├── Mitigation: Implement email filtering.
│   │   ├── Procedure: Conduct phishing simulations.
│   │   ├── STIX Example:
│   │   │   {
│   │   │       "type": "indicator",
│   │   │       "id": "indicator--8e6f5022-5b20-4fdd-9a3b-c5cd37026e33",
│   │   │       "indicator_type": "malicious-activity",
│   │   │       "pattern": "[ipv4-addr:value = '192.0.2.1']",
│   │   │       "valid_time": {
│   │   │           "start_time": "2023-10-01T00:00:00.000Z",
│   │   │           "end_time": "2023-12-01T00:00:00.000Z"
│   │   │       },
│   │   │       "labels": ["malicious"],
│   │   │       "description": "Malicious IP address suspected in phishing attacks."
│   │   │   }
│   │   └── Sub-Procedures:
│   │       ├── Train employees on recognizing phishing.
│   │       └── Set up reporting mechanisms for suspected emails.
│   ├── Technique T1566: Phishing (APT28, APT29)
│   │   ├── Sub-Technique T1566.001: Spear Phishing Link
│   │   ├── Sub-Technique T1566.002: Spear Phishing Attachment
│   │   ├── Mitigation: Regular patching of applications.
│   │   ├── Procedure: Perform regular penetration testing.
│   │   ├── STIX Example:
│   │   │   {
│   │   │       "type": "attack-pattern",
│   │   │       "id": "attack-pattern--c9fe9c34-6b56-4ed8-89b2-cd4bcab0f22f",
│   │   │       "name": "Phishing",
│   │   │       "description": "Attackers use phishing emails to gain access to systems."
│   │   │   }
│   │   └── Sub-Procedures:
│   │       ├── Use automated vulnerability scanners.
│   │       └── Review application logs for anomalies.
│   ├── Technique T1195: Supply Chain Compromise
│   │   ├── Sub-Technique T1195.001: Compromise Software Dependencies
│   │   └── Sub-Technique T1195.002: Compromise Hardware
│   │       ��── Mitigation: Vet third-party vendors rigorously.
│   │       ├── Procedure: Monitor supply chain for unusual activities.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "intrusion-set",
│   │       │       "id": "intrusion-set--a6933dba-d9f4-4b76-b2f2-1f0dc71dd0b4",
│   │       │       "name": "Fancy Bear",
│   │       │       "description": "Fancy Bear is a Russian cyber espionage group known for targeting political entities.",
│   │       │       "first_seen": "2014-01-01T00:00:00.000Z",
│   │       │       "last_seen": "2023-10-01T00:00:00.000Z"
│   │       │   }
│   │       └── Sub-Procedures:
│   │           ├── Implement vendor risk assessments.
│   │           └── Establish incident response protocols.
```

</details>

<details>
<summary> Execution Tactics</summary>

```plaintext
├── Tactic 2: Execution
│   ├── Technique T1059: Scripting
│   │   ├── Sub-Technique T1059.001: PowerShell
│   │   ├── Sub-Technique T1059.002: JavaScript
│   │   └── Sub-Technique T1059.003: Visual Basic
│   │       ├── Mitigation: Monitor CLI usage.
│   │       ├── Procedure: Audit command logs regularly.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "attack-pattern",
│   │       │       "id": "attack-pattern--f2939dcb-bfa7-4d47-8d5f-2e4d235fb2c0",
│   │       │       "name": "Scripting",
│   │       │       "description": "Scripting languages are utilized to execute commands or programs."
│   │       │   }
│   │       └── Sub-Procedures:
│   │           ├── Utilize tools to restrict CLI access for non-admins.
│   │           └── Create alerts for suspicious command executions.
│   ├── Technique T1203: Exploitation for Client Execution
│   │   ├── Sub-Technique T1203.001: Browser
│   │   ├── Sub-Technique T1203.002: Microsoft Office
│   │       ├── Mitigation: Limit script execution policies.
│   │       ├── Procedure: Review script logs for anomalies.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "indicator",
│   │       │       "id": "indicator--dca4f8a5-6343-4ec5-90c1-0f77c0fa263c",
│   │       │       "indicator_type": "malicious-activity",
│   │       │       "pattern": "[file:path = 'C:\\malware.exe']",
│   │       │       "description": "Malicious executable commonly used in client exploitation."
│   │       │   }
│   │       └── Sub-Procedures:
│   │           ├── Disable scripts from untrusted sources.
│   │           └── Implement code-signing for internal scripts.
│   └── Technique T1060: Registry Run Keys / Startup Folder
│       ├── Sub-Technique T1060.001: Run Key
│       └── Sub-Technique T1060.002: Startup Folder
│           ├── Mitigation: Regularly review startup items.
│           ├── Procedure: Automate checks for unauthorized entries.
│           ├── STIX Example:
│           │   {
│           │       "type": "attack-pattern",
│           │       "id": "attack-pattern--98d6b10a-2e9c-4663-a57e-472518b119c5",
│           │       "name": "Registry Run Keys / Startup Folder",
│           │       "description": "Malicious programs use registry runs to persist through reboots."
│           │   }
│           └── Sub-Procedures:
│               ├── Implement alerts for changes to registry keys.
│               └── Restore defaults for known legitimate software.
```

</details>

<details>
<summary> Persistence Tactics</summary>

```plaintext
├── Tactic 3: Persistence
│   ├── Technique T1547: Boot or Logon Autostart Execution
│   │   ├── Sub-Technique T1547.001: Registry Run Keys
│   │   ├── Sub-Technique T1547.002: Scheduled Tasks
│   │       ├── Mitigation: Regularly review startup items.
│   │       ├── Procedure: Automate checks for unauthorized entries.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "attack-pattern",
│   │       │       "id": "attack-pattern--7bcb3683-e673-41d5-a619-6200f66e46c6",
│   │       │       "name": "Boot or Logon Autostart Execution",
│   │       │       "description": "Techniques that enable persistence by automatically launching a program at startup."
│   │       │   }
│   │       └── Sub-Procedures:
│   │           ├── Implement alerts for changes to registry keys.
│   │           └── Restore defaults for known legitimate software.
│   ├── Technique T1136: Create Account
│   │   └── Sub-Technique T1136.001: Local Account
│   │       ├── Mitigation: Limit permissions on task creation.
│   │       ├── Procedure: Audit scheduled tasks routinely.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "indicator",
│   │       │       "id": "indicator--c9514c24-c9b1-4c1d-a625-0b6f58765f75",
│   │       │       "indicator_type": "malicious-activity",
│   │       │       "pattern": "[user-account:name = 'newadmin']",
│   │       │       "description": "Suspicious account creation likely indicating persistence."
│   │       │   }
│   │       └── Sub-Procedures:
│   │           ├── Ensure tasks run under restricted permissions.
│   │           └── Monitor task execution and outcomes.
│   └── Technique T1069: Indicator Removal on Host
│       └── Sub-Technique T1069.001: Clear Windows Event Logs
│           ├── Mitigation: Monitor for memory access attacks.
│           ├── Procedure: Employ credential storage protections.
│           ├── STIX Example:
│           │   {
│           │       "type": "attack-pattern",
│           │       "id": "attack-pattern--6391c126-4d58-474d-bc4f-7b9faa947c37",
│           │       "name": "Indicator Removal on Host",
│           │       "description": "Techniques that allow adversaries to cover their tracks."
│           │   }
│           └── Sub-Procedures:
│               ├── Implement credential vaults.
│               └── Use monitoring for suspicious process behavior.
```

</details>

<details>
<summary> Privilege Escalation Tactics</summary>

```plaintext
├── Tactic 4: Privilege Escalation
│   ├── Technique T1068: Execution via Application Layer
│   │   └── Sub-Technique T1068.001: Web Server
│   │       ├── Mitigation: Keep client software updated.
│   │       ├── Procedure: Conduct vulnerability assessments.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "intrusion-set",
│   │       │       "id": "intrusion-set--f4a2ad56-c5c9-4d88-848f-c56b689de36b",
│   │       │       "name": "Web Server Vulnerability Exploitation",
│   │       │       "description": "Adversaries exploit vulnerabilities in web servers to escalate privileges."
│   │       │   }
│   │       └── Sub-Procedures:
│   │           ├── Monitor application vulnerabilities in real time.
│   │           └── Implement sandboxing for vulnerable apps.
│   ├── Technique T1134: Access Token Manipulation
│   │   └── Sub-Technique T1134.001: Create Token
│   │       ├── Mitigation: Enforce strong password policies.
│   │       ├── Procedure: Monitor login attempts and alerts.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "malware",
│   │       │       "id": "malware--d6b8515b-aef0-445b-a142-dda7ff0a334b",
│   │       │       "name": "Token Manipulator",
│   │       │       "description": "A tool used by adversaries to manipulate access tokens."
│   │       │   }
│   │       └── Sub-Procedures:
│   │           ├── Implement two-factor authentication.
│   │           └── Conduct periodic access reviews.
│   └── Technique T1045: Nested Group Membership
│       └── Sub-Technique T1045.001: Add to Admin Group
│           ├── Mitigation: Regular operating system updates.
│           ├── Procedure: Utilize exploit detection mechanisms.
│           ├── STIX Example:
│           │   {
│           │       "type": "relationship",
│           │       "id": "relationship--8b33a255-ef3c-4298-8c04-f0a4a5351ff9",
│           │       "source_ref": "user-account--36b3c17a-945f-4fa1-903f-ba825c881cd8",
│           │       "target_ref": "group--cb1c4a8a-e66c-4b38-b541-98cf51e93e80",
│           │       "relationship_type": "member-of",
│           │       "description": "Adversary added a user to the Admin group for escalated privileges."
│           │   }
│           └── Sub-Procedures:
│               ├── Monitor for kernel mode activities.
│               └── Utilize comprehensive EDR solutions.
```

</details>

<details>
<summary> Defense Evasion Tactics</summary>

```plaintext
├── Tactic 5: Defense Evasion
│   ├── Technique T1070: Indicator Removal on Host
│   │   ├── Sub-Technique T1070.001: Clear Windows Event Logs
│   │   │   ├── Mitigation: Monitor file modification logs.
│   │   │   ├── Procedure: Conduct regular integrity checks.
│   │   │   ├── STIX Example:
│   │   │   │   {
│   │   │   │       "type": "indicator",
│   │   │   │       "id": "indicator--b4f8434f-8f8c-4b30-a3c4-16bfcd54ccee",
│   │   │   │       "indicator_type": "malicious-activity",
│   │   │   │       "pattern": "[file:name = 'eventlog.evtx']",
│   │   │   │       "description": "Detection of attempts to clear event logs."
│   │   │   │   }
│   │   │   └── Sub-Procedures:
│   │   │       ├── Use file integrity monitoring tools.
│   │   │       └── Analyze timestamps across file systems.
│   │   ├── Technique T1497: Virtualization/Sandbox Evasion
│   │   │   └── Sub-Technique T1497.001: Timing-Based Evasion
│   │   │       ├── Mitigation: Use threat detection systems.
│   │   │       ├── Procedure: Review event logs for unusual file behaviors.
│   │   │       ├── STIX Example:
│   │   │       │   {
│   │   │       │       "type": "malware",
│   │   │       │       "id": "malware--a2e7eca6-b15d-48eb-90e4-3d5effa212ab",
│   │   │       │       "name": "Evasive Malware",
│   │   │       │       "description": "Malware designed to evade detection in virtual environments."
│   │   │       │   }
│   │   │       └── Sub-Procedures:
│   │   │           ├── Analyze file contents for malicious signatures.
│   │   │           └── Implement behavioral analysis tools.
│   │   └── Technique T1562: Impair Defense
│   │       └── Sub-Technique T1562.001: Disable Antivirus Software
│   │           ├── Mitigation: Monitor for indicators of compromise.
│   │           ├── Procedure: Use host-based intrusion detection systems.
│   │           ├── STIX Example:
│   │           │   {
│   │           │       "type": "attack-pattern",
│   │           │       "id": "attack-pattern--bfb657d7-10f3-4ca1-8048-0631f744b32e",
│   │           │       "name": "Impairing Endpoint Protection",
│   │           │       "description": "Methods to disable security software to facilitate an attack."
│   │           │   }
│   │           └── Sub-Procedures:
│   │               ├── Regularly update and test indicators.
│   │               └── Implement thorough forensics procedures.
```

</details>

<details>
<summary> Credential Access Tactics</summary>

```plaintext
├── Tactic 6: Credential Access
│   ├── Technique T1003: Credential Dumping
│   │   ├── STIX Example:
│   │   │   {
│   │   │       "type": "malware",
│   │   │       "id": "malware--fd60a8a3-896c-4c61-84e9-978e5ee158f3",
│   │   │       "name": "Credential Dumper",
│   │   │       "description": "Malware that dumps credentials from memory."
│   │   │   }
│   │   │   └── Sub-Procedures:
│   │   │       ├── Monitor memory for suspicious access.
│   │   │       └── Utilize anti-malware tools.
│   │   ├── Technique T1555: Credentials from Password Stores
│   │   │   ├── STIX Example:
│   │   │   │   {
│   │   │   │       "type": "indicator",
│   │   │   │       "id": "indicator--effcca1e-7c8c-4d2a-879b-84f0f2c3e9f6",
│   │   │   │       "indicator_type": "malicious-activity",
│   │   │   │       "pattern": "[file:hashes.'SHA-256' = '2b93a1d75a1392bcbfa2361325b9f081b709029da0715d5861549d67af1fbd72']",
│   │   │   │       "description": "Detection of malicious access to password stores."
│   │   │   │   }
│   │   │   └── Sub-Procedures:
│   │   │       ├── Implement password manager training.
│   │   │       └── Review browser security settings.
│   │   └── Technique T1110: Brute Force
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "attack-pattern",
│   │       │       "id": "attack-pattern--ef67ab8c-5ef8-4047-b70e-5b142c27d788",
│   │       │       "name": "Brute Force Attack",
│   │       │       "description": "Attack to gain access through repeated guessing."
│   │       │   }
│   │       └── Sub-Procedures:
│   │           ├── Use multi-factor authentication.
│   │           └── Deploy rate limiting on login attempts.
```

</details>

<details>
<summary> Discovery Tactics</summary>

```plaintext
├── Tactic 7: Discovery
│   ├── Technique T1046: Network Service Scanning
│   │   ├── Sub-Technique T1046.001: Fingerprinting Services
│   │   ├── Sub-Technique T1046.002: Port Scanning
│   │   │   ├── Mitigation: Segment network and limit scanning.
│   │   │   ├── Procedure: Use intrusion detection for unusual scans.
│   │   │   ├── STIX Example:
│   │   │   │   {
│   │   │   │       "type": "attack-pattern",
│   │   │   │       "id": "attack-pattern--f62e793e-88be-4f88-a8ea-6ee0aa3a3f20",
│   │   │   │       "name": "Network Service Scanning",
│   │   │   │       "description": "Scanning for active services allows for vulnerabilities to be identified."
│   │   │   │   }
│   │   │   └── Sub-Procedures:
│   │   │       ├── Maintain an up-to-date network map.
│   │   │       └── Implement honeypots to detect scanning attempts.
│   │   ├── Technique T1083: File and Directory Discovery
│   │   │   ├── Sub-Technique T1083.001: List Files
│   │   │   │   ├── Mitigation: Restrict file access permissions.
│   │   │   │   ├── Procedure: Regularly audit file permissions.
│   │   │   │   ├── STIX Example:
│   │   │   │   │   {
│   │   │   │   │       "type": "sighting",
│   │   │   │   │       "id": "sighting--14fbc799-3b07-45de-afbc-4b292b16cf1f",
│   │   │   │   │       "related": ["attack-pattern--a2c235a5-8872-4f05-97fe-034970c0ccfe"],
│   │   │   │   │       "count": 3,
│   │   │   │   │       "description": "Detected multiple attempts to list files on sensitive directories."
│   │   │   │   │   }
│   │   │   │   └── Sub-Procedures:
│   │   │   │       ├── Monitor access for sensitive directories.
│   │   │   │       └── Enforce least privilege access policies.
│   │   │   └── Technique T1124: System Time Discovery
│   │   │       └── Sub-Technique T1124.001: NTP Queries
│   │   │           ├── Mitigation: Monitor for changes in account structures.
│   │   │           ├── Procedure: Conduct routine account audits.
│   │   │           ├── STIX Example:
│   │   │           │   {
│   │   │           │       "type": "relationship",
│   │   │           │       "id": "relationship--5d1b5768-067e-4b8c-a69a-69dc0f885577",
│   │   │           │       "source_ref": "attack-pattern--e9fea22b-ad3b-4a8d-bad0-9b80ff8fda27",
│   │   │           │       "target_ref": "malware--74ca5cbb-88c2-4f8f-88b9-2e04ac5bfbef",
│   │   │           │       "relationship_type": "uses",
│   │   │           │       "description": "Malware used NTP queries to determine the system time."
│   │   │           │   }
│   │   │           └── Sub-Procedures:
│   │   │               ├── Track privilege changes in user accounts.
│   │   │               └── Investigate anomalies in account usage.
```

</details>

<details>
<summary> Lateral Movement Tactics</summary>

```plaintext
├── Tactic 8: Lateral Movement
│   ├── Technique T1021: Remote Services
│   │   ├── Sub-Technique T1021.001: Remote Desktop Protocol
│   │   ├── Sub-Technique T1021.002: SMB/Windows Admin Shares
│   │   │   ├── Mitigation: Enforce strong authentication.
│   │   │   ├── Procedure: Monitor RDP access logs.
│   │   │   ├── STIX Example:
│   │   │   │   {
│   │   │   │       "type": "relationship",
│   │   │   │       "id": "relationship--abcd1234-5678-90ab-cdef-1234567890ab",
│   │   │   │       "relationship_type": "uses",
│   │   │   │       "source_ref": "tactic--7a9a8783-b7f6-4fb7-9ba4-23ecdf06ab1e",
│   │   │   │       "target_ref": "technique--b0a0cabc-5a2c-42c9-9c02-1a0dfa3e47d6",
│   │   │   │       "start_time": "2023-10-01T00:00:00.000Z",
│   │   │   │       "description": "Utilization of remote services during lateral movement."
│   │   │   │   }
│   │   │   └── Sub-Procedures:
│   │   │       ├── Disable RDP when not in use.
│   │   │       └── Use VPNs for enhanced security.
│   │   ├── Technique T1077: Windows Admin Shares
│   │   │   ├── Sub-Technique T1077.001: Access Admin Shares
│   │   │       ├── Mitigation: Disable unused shares.
│   │   │       ├── Procedure: Review share permissions regularly.
│   │   │       ├── STIX Example:
│   │   │       │   {
│   │   │       │       "type": "attack-pattern",
│   │   │       │       "id": "attack-pattern--e1234567-89ab-cdef-1234-567890abcdef",
│   │   │       │       "name": "Access Windows Admin Shares",
│   │   │       │       "description": "Attackers exploit admin shares to move laterally."
│   │   │       │   }
│   │   │       └── Sub-Procedures:
│   │   │           ├── Monitor for unauthorized access attempts.
│   │   │           └── Limit share access to specific user groups.
│   │   └── Technique T1080: Physical Access
│   │       └── Sub-Technique T1080.001: Component Removal
│   │           ├── Mitigation: Use strong authentication methods.
│   │           ├── Procedure: Monitor authentication attempts.
│   │           ├── STIX Example:
│   │           │   {
│   │           │       "type": "intrusion-set",
│   │           │       "id": "intrusion-set--fedcba98-7654-3210-fedc-ba9876543210",
│   │           │       "name": "Insider Threats",
│   │           │       "description": "Insider threats may involve physical component tampering."
│   │           │   }
│   │           └── Sub-Procedures:
│   │               ├── Implement credential guard for systems.
│   │               └── Regularly review authentication logs.
```

</details>

<details>
<summary> Discovery Tactics</summary>

```plaintext
├── Tactic 9: Collection
│   ├── Technique T1560: Archive Collected Data
│   │   ├── Sub-Technique T1560.001: Compress Data
│   │   ├── Sub-Technique T1560.002: Encrypt Data
│   │   │   ├── Mitigation: Limit data access based on roles.
│   │   │   ├── Procedure: Audit access logs to repositories.
│   │   │   ├── STIX Example:
│   │   │   │   {
│   │   │   │       "type": "malware",
│   │   │   │       "id": "malware--d7bb5c32-254a-4f09-bc77-b826730fe3a3",
│   │   │   │       "name": "Data Compressor",
│   │   │   │       "description": "A malware component responsible for compressing sensitive data.",
│   │   │   │       "created": "2023-09-01T00:00:00.000Z"
│   │   │   │   }
│   │   │   └── Sub-Procedures:
│   │   │       ├── Implement data segmentation according to sensitivity.
│   │   │       └── Review data access requests.
│   │   ├── Technique T1005: Data from Local System
│   │   │   ├── Sub-Technique T1005.001: Data from Files
│   │   │   ├── Sub-Technique T1005.002: Clipboard
│   │   │   │   ├── Mitigation: Encrypt sensitive local data.
│   │   │   │   ├── Procedure: Regularly review user data access.
│   │   │   │   ├── STIX Example:
│   │   │   │   │   {
│   │   │   │   │       "type": "indicator",
│   │   │   │   │       "id": "indicator--e2b961f6-45ff-4da1-bf85-99a564259c64",
│   │   │   │   │       "indicator_type": "data-detected",
│   │   │   │   │       "pattern": "[file:name = 'sensitive_data.txt']",
│   │   │   │   │       "valid_time": {
│   │   │   │   │           "start_time": "2023-10-01T00:00:00.000Z",
│   │   │   │   │           "end_time": "2023-10-31T00:00:00.000Z"
│   │   │   │   │       },
│   │   │   │   │       "description": "Detection of sensitive data file."
│   │   │   │   │   }
│   │   │   │   └── Sub-Procedures:
│   │   │   │       ├── Restrict local storage of sensitive data.
│   │   │   │       └── Monitor for unauthorized data access.
│   │   └── Technique T1041: Exfiltration Over Command and Control Channel
│   │       └── Sub-Technique T1041.001: Data Compression
│   │           ├── Mitigation: Monitor outbound traffic.
│   │           ├── Procedure: Analyze data exfiltration patterns.
│   │           ├── STIX Example:
│   │           │   {
│   │           │       "type": "intrusion-set",
│   │           │       "id": "intrusion-set--c3b9c5c1-8ad8-4e01-abf4-e30e6b7a2a92",
│   │           │       "name": "Data Exfiltration Group",
│   │           │       "description": "A group known for exfiltrating sensitive data through C2 channels.",
│   │           │       "first_seen": "2022-01-01T00:00:00.000Z",
│   │           │       "last_seen": "2023-10-01T00:00:00.000Z"
│   │           │   }
│   │           └── Sub-Procedures:
│   │               ├── Implement DLP solutions.
│   │               └── Log and analyze outgoing data transfers.
   ```

</details>

<details>
<summary> Exfiltration Tactics</summary>

```plaintext
├── Tactic 10: Exfiltration
│   ├── Technique T1043: Commonly Used Port
│   │   ├── Sub-Technique T1043.001: HTTP/S
│   │   ├── Sub-Technique T1043.002: DNS
│   │   │   ├── Mitigation: Block unauthorized web traffic.
│   │   │   ├── Procedure: Investigate unusual web access.
│   │   │   ├── STIX Example:
│   │   │   │   {
│   │   │   │       "type": "attack-pattern",
│   │   │   │       "id": "attack-pattern--5f6b070f-e5df-4c7e-a9af-331f2f65a7a1",
│   │   │   │       "name": "Commonly Used Port Exfiltration",
│   │   │   │       "description": "Exfiltration of data through standard network ports.",
│   │   │   │       "external_references": [
│   │   │   │           {
│   │   │   │               "source_name": "mitre-attack",
│   │   │   │               "url": "https://attack.mitre.org/techniques/T1043/",
│   │   │   │               "description": "MITRE ATT&CK technique."
│   │   │   │           }
│   │   │   │       ]
│   │   │   │   }
│   │   │   └── Sub-Procedures:
│   │   │       ├── Review web application logs frequently.
│   │   │       └── Use web application firewalls.
│   ├── Technique T1048: Exfiltration Over Alternative Protocol
│   │   └── Sub-Technique T1048.001: Exfiltration Over Web Services
│   │       ├── Mitigation: Limit access to staging areas.
│   │       ├── Procedure: Audit staging locations regularly.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "indicator",
│   │       │       "id": "indicator--a1c5a383-909f-4dd1-8699-c9c65d8f7e48",
│   │       │       "indicator_type": "exfiltration",
│   │       │       "pattern": "[http-request:method = 'POST']",
│   │       │       "valid_time": {
│   │       │           "start_time": "2023-10-01T00:00:00.000Z",
│   │       │           "end_time": "2023-12-01T00:00:00.000Z"
│   │       │       },
│   │       │       "labels": ["exfiltration"],
│   │       │       "description": "Detection of data being exfiltrated via HTTP POST requests."
│   │       │   }
│   │       └── Sub-Procedures:
│   │           ├── Monitor staging area for data movement.
│   │           └── Review file access permissions in staging areas.
│   └── Technique T1056: Input Data Manipulation
│       └── Sub-Technique T1056.001: Manipulate Key Inputs
│           ├── Mitigation: Employ regular backups.
│           ├── Procedure: Test recovery procedures.
│           ├── STIX Example:
│           │   {
│           │       "type": "malware",
│           │       "id": "malware--f23b8c86-e452-4ef4-bac9-cb6a0da14d56",
│           │       "name": "Keylogger",
│           │       "description": "Malware that captures keystrokes for data exfiltration.",
│           │       "first_seen": "2023-01-01T00:00:00.000Z",
│           │       "last_seen": "2023-09-30T00:00:00.000Z"
│           │   }
│           └── Sub-Procedures:
│               ├── Encrypt backups for added security.
│               └── Test decryption process to ensure data integrity.
   ```

</details>

<details>
<summary> Impact Tactics</summary>

```plaintext
├── Tactic 11: Impact
│   ├── Technique T1486: Data Encrypted for Impact
│   │   ├── Sub-Technique T1486.001: Encrypt Data In-Place
│   │   ├── Sub-Technique T1486.002: Encrypt Non-Data Files
│   │   │   ├── Mitigation: Monitor critical services.
│   │   │   ├── Procedure: Set alerts for service disruptions.
│   │   │   ├── STIX Example:
│   │   │   │   {
│   │   │   │       "type": "attack-pattern",
│   │   │   │       "id": "attack-pattern--da78ee15-114d-40f3-882e-e8df29f84b22",
│   │   │   │       "name": "Data Encrypted for Impact",
│   │   │   │       "description": "Attackers encrypt data to extort victims.",
│   │   │   │       "created": "2023-10-01T00:00:00Z"
│   │   │   │   }
│   │   │   └── Sub-Procedures:
│   │   │       ├── Create redundancy for critical services.
│   │   │       └── Test recovery options from service interruptions.
│   ├── Technique T1499: Resource Hijacking
│   │   └── Sub-Technique T1499.001: Cryptojacking
│   │       ├── Mitigation: Monitor usage of resources.
│   │       ├── Procedure: Analyze resource allocation patterns.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "indicator",
│   │       │       "id": "indicator--8b4841f7-faa7-413b-85c5-e2b2d2df7000",
│   │       │       "indicator_type": "malicious-activity",
│   │       │       "pattern": "[process:name = 'cryptominer.exe']",
│   │       │       "description": "Indicator of potential cryptojacking activity."
│   │       │   }
│   │       └── Sub-Procedures:
│   │           ├── Implement resource usage policies.
│   │           └── Conduct audits on resource allocation.
│   └── Technique T1561: Disk Wipe
│       └── Sub-Technique T1561.001: Remote Wiping
│           ├── Mitigation: Employ regular backups.
│           ├── Procedure: Test recovery procedures.
│           ├── STIX Example:
│           │   {
│           │       "type": "attack-pattern",
│           │       "id": "attack-pattern--72f7e791-ff8f-4b13-88d5-ab348e0c8122",
│           │       "name": "Disk Wipe",
│           │       "description": "An attacker attempts to delete files to prevent recovery.",
│           │       "created": "2023-10-01T00:00:00Z"
│           │   }
│           └── Sub-Procedures:
│               ├── Encrypt backups for added security.
│               └── Test decryption process to ensure data integrity.
   ```

</details>

<details>
<summary> C2 Tactics</summary>

```plaintext
├── Tactic 12: Command and Control (C2)
│   ├── Technique T1071: Application Layer Protocol
│   │   ├── Sub-Technique T1071.001: Web Protocols
│   │   ├── Sub-Technique T1071.002: File Transfer Protocols
│   │   │   ├── Mitigation: Analyze application traffic.
│   │   │   ├── Procedure: Implement firewall rules.
│   │   │   ├── STIX Example:
│   │   │   │   {
│   │   │   │       "type": "malware",
│   │   │   │       "id": "malware--dc1fe78a-d908-474e-bcbf-93a48192d3b0",
│   │   │   │       "name": "C2 Malware Example",
│   │   │   │       "description": "Malware that uses web protocols for C2.",
│   │   │   │       "created": "2023-10-01T00:00:00Z"
│   │   │   │   }
│   │   │   └── Sub-Procedures:
│   │   │       ├── Use anomaly detection systems on application traffic.
│   │   │       └── Review logs for unusual application behavior.
│   │   ├── Technique T1132: Data Encoding
│   │   │   └── Sub-Technique T1132.001: Base64 Encoding
│   │   │       ├── Mitigation: Monitor for unusual command patterns.
│   │   │       ├── Procedure: Review custom protocols in use.
│   │   │       ├── STIX Example:
│   │   │       │   {
│   │   │       │       "type": "indicator",
│   │   │       │       "id": "indicator--6c3710b8-05a9-4b51-b60e-9e24457f9d89",
│   │   │       │       "indicator_type": "malicious-activity",
│   │   │       │       "pattern": "[http-request:request_method = 'POST']",
│   │   │       │       "description": "Suspicious POST requests that may indicate encoded payloads."
│   │   │       │   }
│   │   │       └── Sub-Procedures:
│   │   │           ├── Implement logging for all unknown protocols.
│   │   │           └── Conduct a risk assessment of custom protocols.
│   │   ├── Technique T1045: Proxy
│   │   │   └── Sub-Technique T1045.001: Connect to Internal Services
│   │   │       ├── Mitigation: Monitor web service endpoints.
│   │   │       ├── Procedure: Regularly analyze proxy logs.
│   │   │       ├── STIX Example:
│   │   │       │   {
│   │   │       │       "type": "infrastructure",
│   │   │       │       "id": "infrastructure--b448b0f1-b7fa-4c65-b493-8778de5d19d0",
│   │   │       │       "name": "Proxy Infrastructure",
│   │   │       │       "description": "Proxy servers used for internal service connections.",
│   │   │       │       "created": "2023-10-01T00:00:00Z"
│   │   │       │   }
│   │   │       └── Sub-Procedures:
│   │   │           ├── Implement access controls on proxy configurations.
│   │   │           ├── Identify and block unauthorized proxies.
   ```

</details>

<details>
<summary> Reconnaissance Tactics</summary>

```plaintext
├── Tactic 13: Reconnaissance
│   ├── Technique T1041: Exfiltration Over Command and Control Channel
│   │   └── Sub-Technique T1041.001: Data Compression
│   │       ├── Mitigation: Monitor command and control traffic.
│   │       ├── Procedure: Use threat intelligence feeds.
│   │       └── Sub-Procedures:
│   │           ├── Maintain an updated list of known C2 domains.
│   │           └── Conduct blacklisting of malicious IPs.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "attack-pattern",
│   │       │       "id": "attack-pattern--b104e5c1-a1e5-4c8b-bc3c-1a53f29b7a0b",
│   │       │       "name": "Data Compression for Egress",
│   │       │       "description": "Technique for reducing size of data exfiltrated via C2 channels."
│   │       │   }
│   ├── Technique T1087: Account Discovery
│   │   ├── Sub-Technique T1087.001: Local Account
│   │   └── Sub-Technique T1087.002: Domain Account
│   │       ├── Mitigation: Limit account privileges.
│   │       ├── Procedure: Regular audits of user accounts.
│   │       └── Sub-Procedures:
│   │           ├── Implement role-based access control.
│   │           └── Track changes to user account statuses.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "indicator",
│   │       │       "id": "indicator--d7b68ba5-bf38-4c4e-a1cf-ec753f8bab26",
│   │       │       "indicator_type": "potentially-malicious",
│   │       │       "pattern": "[user-account:account-name = 'admin']",
│   │       │       "valid_time": {
│   │       │           "start_time": "2023-09-01T00:00:00.000Z",
│   │       │           "end_time": "2023-10-01T00:00:00.000Z"
│   │       │       },
│   │       │       "labels": ["reconnaissance"],
│   │       │       "description": "Monitoring for the usage of the admin account."
│   │       │   }
│   └── Technique T1018: Remote System Discovery
│       └── Sub-Technique T1018.001: Network Enumeration
│           ├── Mitigation: Restrict IP address access.
│           ├── Procedure: Monitor network access logs.
│           └── Sub-Procedures:
│               ├── Conduct regular network scans for vulnerabilities.
│               └── Implement network segmentation.
│           ├── STIX Example:
│           │   {
│           │       "type": "malware",
│           │       "id": "malware--7e5397cc-0c8b-4fef-99e1-c3461419f19a",
│           │       "name": "Network Scanner",
│           │       "description": "Malware designed to discover hosts on a network.",
│           │       "malware_types": ["remote-access-trojan"]
│           │   }
   ```

</details>

<details>
<summary> Resource Development Tactics</summary>

```plaintext
├── Tactic 14: Resource Development
│   ├── Technique T1570: Application Layer Protocol
│   │   ├── Sub-Technique T1570.001: External Application
│   │   └── Sub-Technique T1570.002: Host-Based Application
│   │       ├── Mitigation: Secure application configurations.
│   │       ├── Procedure: Regularly update and patch applications.
│   │       └── Sub-Procedures:
│   │           ├── Implement application whitelisting.
│   │           └── Conduct penetration testing on external applications.
│   │       ├── STIX Example:
│   │       │   {
│   │       │       "type": "tool",
│   │       │       "id": "tool--3bbf76ec-bb5c-41fa-aa89-fe3e634d7cab",
│   │       │       "name": "Network Application Tool",
│   │       │       "description": "Tool used for testing application security via the network."
│   │       │   }
│   └── Technique T1553: Compromise Software Supply Chain
│       └── Sub-Technique T1553.001: Dependencies
│           ├── Mitigation: Monitor for dependency vulnerabilities.
│           ├── Procedure: Use software composition analysis tools.
│           └── Sub-Procedures:
│               ├── Conduct risk assessments on external libraries.
│               └── Ensure compliance with software licensing.
│           ├── STIX Example:
│           │   {
│           │       "type": "intrusion-set",
│           │       "id": "intrusion-set--aabba03b-10c2-4aac-805c-bd4f7ee63655",
│           │       "name": "Supply Chain Attackers",
│           │       "description": "Group specializing in compromising software supply chains.",
│           │       "first_seen": "2022-05-01T00:00:00.000Z",
│           │       "last_seen": "2023-10-01T00:00:00.000Z"
│           │   }
   ```

</details>

<details>
<summary> Normalization Tactics</summary>

```plaintext
├── Tactic 15: Normalization
│   ├── Technique T1587: Compromise Existing Infrastructure
│   │   ├── Sub-Technique T1587.001: Compromise Networks
│   │   ├── Sub-Technique T1587.002: Compromise Database
│   │   │   ├── Mitigation: Regularly assess infrastructure security.
│   │   │   ├── Procedure: Conduct routine infrastructure testing.
│   │   │   ├── STIX Example:
│   │   │   │   {
│   │   │   │       "type": "attack-pattern",
│   │   │   │       "id": "attack-pattern--ce77fc9e-620b-4bfa-9dd8-dc6bbc3d9e4f",
│   │   │   │       "name": "Compromise Existing Infrastructure",
│   │   │   │       "description": "Gain unauthorized access to existing systems or networks.",
│   │   │   │       "created": "2023-10-01T00:00:00.000Z",
│   │   │   │       "modified": "2023-10-01T00:00:00.000Z"
│   │   │   │   }
│   │   │   └── Sub-Procedures:
│   │   │       ├── Ensure logging and monitoring of infrastructure.
│   │   │       └── Implement strict access control for network resources.
│   │   ├── Technique T1585: Platform Account Abuse
│   │   │   ├── Sub-Technique T1585.001: Exploit Default Credentials
│   │   │       ├── Mitigation: Enforce strong password policies.
│   │   │       ├── Procedure: Conduct device configuration audits.
│   │   │       ├── STIX Example:
│   │   │       │   {
│   │   │       │       "type": "indicator",
│   │   │       │       "id": "indicator--8e4d3402-eeff-4cc9-bc93-de4ce83bb2da",
│   │   │       │       "indicator_type": "user-account",
│   │   │       │       "pattern": "[user-account:user_id = 'default_admin']",
│   │   │       │       "valid_time": {
│   │   │       │           "start_time": "2023-10-01T00:00:00.000Z",
│   │   │       │           "end_time": "2023-12-01T00:00:00.000Z"
│   │   │       │       },
│   │   │       │       "labels": ["suspicious"],
│   │   │       │       "description": "Use of default credentials detected."
│   │   │       │   }
│   │   │       └── Sub-Procedures:
│   │   │           ├── Regularly update device firmware and configurations.
│   │   │           └── Educate users on account management best practices.
│   │   └── Technique T1522: File and Data Manipulation
│   │       └── Sub-Technique T1522.001: Data Corruption
│   │           ├── Mitigation: Backup critical files regularly.
│   │           ├── Procedure: Validate backups for integrity.
│   │           ├── STIX Example:
│   │           │   {
│   │           │       "type": "file",
│   │           │       "id": "file--f7e4fc4f-32b4-40c3-b5f1-3b478865d832",
│   │           │       "name": "CRITICAL_BACKUP.zip",
│   │           │       "hashes": {
│   │           │           "SHA-256": "b231f67a3cdbf8e79fa3c4b2b85d5e99a291d4bfe60b3dd63f46faf7dbdc3a5f"
│   │           │       },
│   │           │       "description": "Backup of critical data.",
│   │           │       "created": "2023-09-15T00:00:00.000Z"
│   │           │   }
│   │           └── Sub-Procedures:
│   │               ├── Implement verification checks post-backup.
│   │               └── Create alerts for unusual file access activities.
   ```

</details>
