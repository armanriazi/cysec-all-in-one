
### Revised Horizontal Flow for Threat Modeling Techniques

#### 1. STRIDE

```
User => System => STRIDE Threats => (Spoofing=> Tampering=> Repudiation=> Information Disclosure=> 
                                     Denial of Service=> Elevation of Privilege)
```

---

#### 2. PASTA

```
Business Goals => Technical Scope => Application Design => Threat Analysis => Security Controls => Security Testing
```

---

#### 3. OCTAVE

```
Organizational Goals => Identify Assets/Vulnerabilities/Threats => Risk Analysis => Develop Risk Mitigation Strategies
```

---

#### 4. TRIKE

```
Stakeholders => Identify Assets/Values => Identify Threats/Vulnerabilities => Threat Analysis => Risk Management/Mitigation
```

### Tables for Integrity & Relationships

#### Table: Threat Modeling Techniques Comparison

| Technique      | Focus                                  | Values                                             |
|----------------|----------------------------------------|---------------------------------------------------|
| STRIDE         | Threat categorization                  | Identifies 6 types of potential threats           |
| PASTA          | Risk-centric analysis                  | Focus on application lifecycle and architecture    |
| OCTAVE         | Risk management                        | Emphasis on asset and organizational goals         |
| TRIKE          | Risk quantification                   | Emphasizes stakeholder engagement and risk value   |

### High-Level Relationship Model

This model outlines the relationships between the main components of threat modeling:

```
Assets => Vulnerabilities => Threats => Security Controls
```

### Low-Level Relationship Model

This model provides more details about the components and their interconnections:

```
+------------------+                  +------------------+
|     Assets       |                  |     Threats      |
| (Data, Systems)  | <--------------> | (Types of Attacks)|
+------------------+                  +------------------+
          |                                     ^
          |                                     |
          |                                     |
          v                                     |
   +------------------+                  +------------------+
   |  Vulnerabilities  | <--------------> |   Threat Actions  |
   | (Weaknesses)     |                  | (Exploits)       |
   +------------------+                  +------------------+
          |                                     |
          |                                     |
          v                                     |
   +------------------+                  +------------------+
   | Security Controls | <--------------> |  Security Measures|
   | (Mitigations)    |                  | (Defense Mechanisms)|
   +------------------+                  +------------------+
```

### Explanation of Models

1. **High-Level Relationship Model**:
   - **Assets** represent the critical items that need protection (e.g., sensitive data).
   - **Vulnerabilities** are weaknesses in the system that could be exploited by threats.
   - **Threats** are potential events that could lead to harm or damage to the assets.
   - **Security Controls** are the measures put in place to mitigate the identified vulnerabilities that threats might exploit.

2. **Low-Level Relationship Model**:
   - Provides a more detailed view of the interactions between components.
   - Involves stakeholders in identifying and evaluating **assets** and **threats**.
   - Links **vulnerabilities** with their potential **threat actions** (exploits) and connects **security controls** with specific **security measures** (like access control mechanisms) that can be employed to safeguard the assets effectively.

This structured approach ensures a clear, comprehensive understanding of the relationships, risks, and mitigation strategies within a threat modeling framework.
