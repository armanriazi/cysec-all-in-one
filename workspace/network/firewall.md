## Firewall

### Limitation of Firewall

- Does not prevent backdoor attack[S1]
- Does not prevent password misuse
- Does not protect the net from internal atks
- Cannot do anything if the net design and conf is faulty
- Not able to prevent social engineering threats

<p align="center">
  <img src="..\assets\images\firewall-1.jpg" alt="Firewall[1]">
</p>


#### Packet filtering

- ip
- protocols
- ports
- rules

### WAF

WAFs stands for **Web Application Firewalls**.

A Web Application Firewall is a security solution designed to monitor, filter, and protect web applications from various types of online threats and attacks, including SQL injection, cross-site scripting (XSS), and other application-layer vulnerabilities. WAFs operate at the application layer (Layer 7 of the OSI model) and analyze incoming traffic to and from a web application.

Key features of WAFs include:

- **Traffic Monitoring**: Analyzing HTTP/HTTPS traffic to identify and block malicious requests.
- **Rule-Based Protection**: Applying predefined or custom rules to filter out harmful traffic.
- **Threat Detection**: Utilizing security policies to recognize abnormal behavior and potential attacks.
- **Session Protection**: Managing and securing user sessions to prevent session hijacking.

WAFs can be deployed as hardware appliances, software solutions, or cloud-based services.

Here’s the updated comparison table of popular Web Application Firewalls (WAFs), including both commercial and open-source options, along with their estimated usage rates and their integration capabilities with Intrusion Detection Systems (IDS), Intrusion Prevention Systems (IPS), and other filtering products.

| **WAF Tool**                          | **Deployment**                | **Key Features**                                                | **Supported Platforms**                   | **Pricing**                   | **Rate of Usage (Approx.)** | **Integration with IDS/IPS**                 |
|---------------------------------------|-------------------------------|---------------------------------------------------------------|------------------------------------------|-------------------------------|------------------------------|------------------------------------------------|
| **AWS WAF**                           | Cloud-Based                   | Integrates with AWS services, SQL injection/XSS protections    | Rust, Node.js, Java, .NET Core           | Pay-as-you-go                 | ~20%                          | Excellent (works well with AWS Shield, etc.) |
| **Cloudflare WAF**                    | Cloud-Based                   | Global CDN, DDoS protection, OWASP rules                      | Rust, Node.js, Java, .NET Core           | Freemium and paid plans       | ~30%                          | Excellent (integrates with Cloudflare's security suite) |
| **Imperva WAF**                       | Cloud-Based/On-Premises     | Advanced threat intelligence, bot protection                   | Rust, Node.js, Java, .NET Core           | Subscription-based             | ~15%                          | Very Good (integrates with various IPS solutions) |
| **F5 Advanced WAF**                   | On-Premises/Cloud            | Application security, DDoS protection, API security           | Java, .NET Core                         | License-based                  | ~10%                          | Very Good (has strong integration capabilities) |
| **Barracuda WAF**                     | Hardware/VM/Cloud             | Malware scanning, identity protection                           | Rust, Node.js, Java, .NET Core           | Subscription-based             | ~8%                           | Good (supports integration with various security tools) |
| **ModSecurity (with Nginx/Apache)** | Open Source/Gatekeeper        | OWASP Core Rule Set, customizable rules                        | Rust, Node.js, Java, .NET Core           | Free (self-hosted)            | ~5%                           | Good (can integrate with IDS/IPS via configuration) |
| **NAXSI**                             | Open Source                   | Nginx module for filtering malicious requests                   | Nginx (works well with Ruby)            | Free (self-hosted)            | ~3%                           | Moderate (requires additional configuration for IDS integration) |
| **WebKnight**                         | Open Source                   | .NET application firewall, customizable rules                  | .NET Framework                          | Free (self-hosted)            | ~2%                           | Moderate (can work with IDS but less common) |
| **Openresty + Lua**                  | Open Source                   | Customizable application security based on NGINX and Lua scripts | Rust, Node.js, Java, .NET Core          | Free (self-hosted)            | ~2%                           | Moderate (requires manual configuration for integration) |
| **Access Control WAF**               | Open Source                   | Focus on managing access control and authentication            | Java, .NET Core                         | Free (self-hosted)            | <1%                           | Low (minimal integration capabilities) |

### Key

- **Excellent**: Seamless integration with multiple IDS/IPS and filtering products.
- **Very Good**: Strong integration capabilities, generally easy to configure.
- **Good**: Detectable integration; some configuration may be required.
- **Moderate**: Feasible integration but potentially more complex or less common.
- **Low**: Limited to no integration with IDS/IPS systems.

When evaluating a WAF’s integrity and compatibility with IDS/IPS systems, it’s crucial to assess the ease of integration and the level of support provided by each WAF. Each organization's specific requirements and existing security infrastructure will guide the choice of which WAF is the best fit.



##### Circuit-level gw

- Between session and transportlayer of OSI model
- App layer of TCP/IP model

A circuit-level gateway is a **type of firewall** that operates at the transport layer (Layer 4) of the OSI model. It provides a means of controlling network traffic over a network, primarily focused on **monitoring and managing TCP connections**. Here are the key characteristics and functionalities of circuit-level gateways:

###### Key Characteristics

1. **Connection Monitoring**:
   - A circuit-level gateway establishes a virtual circuit between clients and servers in a networked environment and monitors the traffic that passes through it.

2. **Session Management**:
   - Circuit-level gateways maintain the state of each connection. They keep track of sessions and verify that packets are part of a valid session.

3. **Protocol Independence**:
   - They can work with any protocol that operates above the transport layer, allowing them to provide security for a variety of applications.

4. **No Packet Inspection**:
   - **Unlike application-layer gateways, circuit-level gateways do not inspect the contents of packets; they only monitor the headers and are concerned with the state and management of connections.**

5. **Performance**:
   - Circuit-level gateways tend to be faster than application-layer gateways because they do not analyze the data content, leading to lower processing overhead.

###### Functions

- **Traffic Filtering**: Circuit-level gateways can enforce policies for which **types of traffic are allowed or denied** based on the established connections.
- **Address Translation**: Some circuit-level gateways may perform Network Address Translation (NAT), allowing multiple devices on a local network to share a single public IP address.
- **Security**: They provide a level of security by **preventing unauthorized access to internal networks and managing which external entities can establish connections.**

###### Use Cases

- **VPNs (Virtual Private Networks)**: Circuit-level gateways are often **used in VPNs** to establish secure connections between remote users and internal networks.
- **Network Address Translation (NAT)**: They can **perform NAT, which helps in managing IP address usage.**

##### Limitations

- **Limited Inspection**[S1]: Due to the lack of deep packet inspection, circuit-level gateways may be less effective at detecting certain types of malicious activities or sophisticated attacks compared to application-level firewalls.
- **State Management**[S1]: If the connection state is not properly managed, it could lead to vulnerabilities, such as session hijacking.

In summary, circuit-level gateways serve a crucial role in managing TCP connections and providing a basic structural layer of security in network communications, particularly **suitable for scenarios where performance and session management are priorities**.

##### App layer gw

- packet headers/data
- filtering content/URL
- authentication

##### App proxy

- filters messages at app layer to protect net resources
- known as a proxy firewall/gw firewall

##### SMLI

- advance packet filtering for all 7 layers

###### Stateless Multilayer Inspection (SMLI)

1. **Definition**:
   - SMLI is a technique used in network security where **packets are analyzed at multiple layers of the OSI model** without maintaining state information about the connection. It **focuses on inspecting each packet independently.**

2. **Purpose**:
   - The goal of SMLI is to enhance security by applying checks at various protocol layers—such as the network layer, transport layer, and sometimes the application layer—**without needing to remember connection states.**[S1]

3. **Features**:
   - **Packet Filtering**: Performs filtering based on predefined rules **without needing context from previous packets.**[S1]
   - **Layered Inspection**: Evaluates packets according to multiple layers of protocols to identify potentially malicious traffic.
   - **Simplicity**: Simpler to implement compared to stateful inspection since it does not require management of connection states.

4. **Use Cases**:
   - **Firewalls**: **Used in some firewall** implementations to filter traffic based on objective criteria at different layers.
   - **Intrusion Detection Systems (IDS)**: Employed in IDS to quickly analyze and respond to potential threats without needing a deep contextual understanding of sessions.

###### Importance in Cybersecurity

- SMLI can be beneficial for environments where speed is crucial, and quick decisions on packet handling are required. It provides a straightforward mechanism for filtering traffic but may **not be as effective at identifying sophisticated attacks that require context, such as those relying on session information or established connections.**

> Remember: SMLI used in firewall, Circuit-gw used in VPN

##### NAT

- allows devices on a private net to **communicate with the internet**
- **hiding their IP address from external devices**

##### VPN

- protect against unauthorized:
- users **intercepting & exploiting a VPN** con.

<p align="center">
  <img src="..\assets\images\firewall-osi.jpg" alt="Firewall-OSI[1]">
</p>

