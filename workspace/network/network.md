
# Models

## OSI

Open Systems Interconnection model is a conceptual framework used to understand and implement network communications. It consists of seven layers, each with distinct functions:

1. **Physical Layer**: This layer is responsible for the physical **connection between devices**, including the transmission and reception of raw binary data over a physical medium (e.g., cables, switches). It includes hardware elements like cables, switches, and the electrical signals that pass through them.

2. **Data Link Layer**[S1]: The data link layer ensures reliable communication between directly **connected nodes.** It manages **error detection and correction, framing, and flow control**. Common protocols at this layer include **Ethernet and Wi-Fi**.

3. **Network Layer**: This layer manages **routing and forwarding of data packets** across the network. It determines the best paths for data transmission and handles logical addressing (e.g., IP addresses). **Key protocols include IP (Internet Protocol).**

4. **Transport Layer**: The transport layer provides reliable data transfer services to the upper layers, ensuring error recovery and flow control. It breaks down messages into packets and is responsible for end-to-end communication. Common protocols include **TCP (Transmission Control Protocol) and UDP (User Datagram Protocol).**

5. **Session Layer**: This layer manages sessions, which are established and maintained for communication between applications. It handles the opening, closing, and management of sessions, **allowing for proper data synchronization.**

6. **Presentation Layer**: The presentation layer is responsible for **data translation, encryption, and compression**. It ensures that data is in a usable format for the application layer. This layer translates data formats and provides **data serialization/deserialization.**

7. **Application Layer**: The topmost layer provides services directly to end-user applications. It **encompasses protocols** for various application services, such as HTTP (for web browsing), FTP (for file transfer), and SMTP (for email).

Understanding the OSI model can help in troubleshooting network issues and improving communication protocols.

---

Certainly! Below are the two sections combined, providing both the OSI model overview and the ASCII art representations of Protocol Data Units (PDUs) at various layers of the OSI model.

---

### OSI Model Overview with PDUs and Protocols

```plaintext
+---------------------------------------------------+
|                      OSI Model                    |
+---------------------------------------------------+
| Layer 7: Application                               |
| +-----------------------------------------------+ |
| | PDU: Data                                     | |
| | Protocols:                                    | |
| |   - HTTP (Web)                               | |
| |   - FTP (File Transfer)                      | |
| |   - Telnet (Terminal Access)                 | |
| |   - DNS (Domain Name Service)                | |
| |   - SMTP (Email Transfer)                    | |
| |   - SNMP (Network Management)                | |
| +-----------------------------------------------+ |
|                                                   |
| Layer 6: Presentation                            | |
| +-----------------------------------------------+ |
| | PDU: Data                                     | |
| | Functions:                                    | |
| |   - Data Encoding                             | |
| |   - Data Compression                          | |
| |   - Encryption                                | |
| |   - Character Set Translation                 | |
| +-----------------------------------------------+ |
|                                                   |
| Layer 5: Session                                 | |
| +-----------------------------------------------+ |
| | PDU: Data                                     | |
| | Functions:                                    | |
| |   - Session Control                           | |
| |   - Establishing Connections                  | |
| |   - Session Termination                       | |
| |   - Synchronization                           | |
| +-----------------------------------------------+ |
|                                                   |
| Layer 4: Transport                               | |
| +-----------------------------------------------+ |
| | PDU: Segment for TCP / Datagram for UDP       | |
| | Protocols:                                    | |
| |   - TCP (Transmission Control Protocol)      | |
| |   - UDP (User Datagram Protocol)             | |
| | Functions:                                    | |
| |   - Reliable / Unreliable Delivery           | |
| |   - Flow Control                              | |
| |   - Segmentation and Reassembly               | |
| +-----------------------------------------------+ |
|                                                   |
| Layer 3: Network                                 | |
| +-----------------------------------------------+ |
| | PDU: Packet                                   | |
| | Protocols:                                    | |
| |   - IP (Internet Protocol)                   | |
| |   - ICMP (Internet Control Message Protocol) | |
| |   - IGMP (Internet Group Management Protocol) | |
| |   - ARP: (Address Resolution Protocol) | |
| | Functions:                                    | |
| |   - Routing                                   | |
| |   - Logical Addressing                        | |
| +-----------------------------------------------+ |
|                                                   |
| Layer 2: Data Link                              | |
| +-----------------------------------------------+ |
| | PDU: Frame                                    | |
| | Protocols:                                    | |
| |   - Ethernet                                  | |
| |   - PPP (Point-to-Point Protocol)           | |
| |   - HDLC (High-Level Data Link Control)      | |
| | Functions:                                    | |
| |   - MAC Addressing                            | |
| |   - Error Detection                           | |
| |   - Frame Synchronization                     | |
| +-----------------------------------------------+ |
|                                                   |
| Layer 1: Physical                               | |
| +-----------------------------------------------+ |
| | PDU: Bit                                      | |
| | Represents:                                   | |
| |   - Physical Medium (Cabling, Hubs)          | |
| |   - Electrical/Optical Signals                | |
| |   - Connector Types (RJ45, Fiber, etc.)      | |
| |   - Signal Types (Analog, Digital)           | |
| +-----------------------------------------------+ |
+---------------------------------------------------+
```

### Explanation of Each Layer and Its PDU

1. **Layer 7: Application**
   - **PDU**: Data
   - **Protocols**:
     - **HTTP**: Hypertext Transfer Protocol for web content.
     - **FTP**: File Transfer Protocol for sending/receiving files.
     - **Telnet**: Terminal emulation for remote access.
     - **DNS**: Domain Name System for name resolution.
     - **SMTP**: Simple Mail Transfer Protocol for email transmission.
     - **SNMP**: Simple Network Management Protocol for managing network devices.

2. **Layer 6: Presentation**
   - **PDU**: Data
   - **Functions**:
     - **Data Encoding**: Conversion of data to a format usable by the application layer.
     - **Data Compression**: Reducing data size for transmission efficiency.
     - **Encryption**: Securing data for confidentiality.
     - **Character Set Translation**: Translating character sets for application compatibility.

3. **Layer 5: Session**
   - **PDU**: Data
   - **Functions**:
     - **Session Control**: Establishes, manages, and terminates sessions.
     - **Synchronization**: Keeps applications in sync during communication.
     - **Session Termination**: Ensures proper closure of communication sessions.

4. **Layer 4: Transport**
   - **PDU**: Segment (for TCP) / Datagram (for UDP)
   - **Protocols**:
     - **TCP**: Ensures reliable, ordered delivery of data.
     - **UDP**: Allows for faster, connectionless communication.
   - **Functions**:
     - **Reliable/Unreliable Delivery**: Guarantees delivery with TCP; up to application with UDP.
     - **Flow Control**: Mechanisms for controlling data transmission rates.
     - **Segmentation and Reassembly**: Splits data into smaller segments and reassembles at the destination.

5. **Layer 3: Network**
   - **PDU**: Packet
   - **Protocols**:
     - **IP**: Handles addressing and routing packets across networks.
     - **ICMP**: Sends error messages and operational information.
     - **IGMP**: Manages multicast group memberships.
     - **ARP**: Resolves IP addresses to MAC addr within a local net

6. **Layer 2: Data Link**
   - **PDU**: Frame
   - **Protocols**:
     - **Ethernet**: The most common LAN technology.
     - **PPP**: Protocol used for direct connections between two nodes.
     - **HDLC**: Standard for transmitting data over point-to-point links.

7. **Layer 1: Physical**
   - **PDU**: Bit
   - **Represents**:
     - **Physical Medium**: Cables, switches, and other hardware.
     - **Electrical/Optical Signals**: Transmits bits as electrical pulses or light.
     - **Connector Types**: RJ45, fiber optic connectors, etc.

### Conclusion

This upgraded ASCII art representation provides a comprehensive view of the OSI model, clearly illustrating the layers, PDUs, protocols, and functions. Each layer builds on the last, ensuring data is correctly prepared, delivered, and interpreted across various network environments. This visual summary aids in understanding the structure and depth of communication in networked systems.

---

### ASCII Art Representations of PDUs

You're absolutely right to point out that the order of protocols within the stack was not traditional in my previous representation. Network protocols follow a specific hierarchy, and they are typically organized based on their functionality and how they interoperate. Here's a corrected version of the ASCII art that represents the correct order of protocols in the networking stack:

### Corrected Networking Protocol Stack

```plaintext
+--------------------------------------------------------+
|                     Application Layer                  |
| +----------------------------------------------------+ |
| |                     DNS Protocol                    | |
| | +---------------------------------------------+    | |
| | |                  DNS Header                 |    | |
| | | +-----------------------------------------+ |    | |
| | | | Transaction ID (16 bits)                | |    | |
| | | +-----------------------------------------+ |    | |
| | | | Flags (16 bits)                         | |    | |
| | | |   QR (1 bit)  | Opcode (4 bits)       | |    | |
| | | |   AA (1 bit)  | TC (1 bit)  | RD (1 bit) | |    | |
| | | |   RA (1 bit)  | Z (3 bits)  | RCODE (4 bits)| |  |
| | | +-----------------------------------------+ |    | |
| | | | Questions (16 bits)                   | |    | |
| | | +---------------------------------------+  |    | |
| | | | Answer RRs (16 bits)                  | |    | |
| | | +---------------------------------------+  |    | |
| | | | Authority RRs (16 bits)               | |    | |
| | | +---------------------------------------+  |    | |
| | | | Additional RRs (16 bits)              | |    | |
| | | +---------------------------------------+  |    | |
| | | |              Questions Section         | |    | |
| | | |              (Variable Length)         | |    | |
| | | +---------------------------------------+  |    | |
| | | |              Answers Section           | |    | |
| | | |              (Variable Length)         | |    | |
| | | +---------------------------------------+  |    | |
| | +---------------------------------------------+    | |
| +----------------------------------------------------+ |
+--------------------------------------------------------+

+--------------------------------------------------------+
|                     Transport Layer                    |
| +----------------------------------------------------+ |
| |                     TCP Segment                     | |
| | +------------------------------------------------+ | |
| | |                TCP Header                       | | |
| | | +--------------------------------+ +------------+ | |
| | | |     Source Port               | |  Dest Port | | |
| | | |            16 bits            | |    16 bits | | |
| | | +--------------------------------+ +------------+ | |
| | | | Sequence Number (32 bits)                 | | |
| | | +--------------------------------------------+ | |
| | | | Acknowledgment Number (32 bits)           | | |
| | | +--------------------------------------------+ | |
| | | | Data Offset | Flags | Window Size          | | |
| | | |   4 bits   | 9 bits|  16 bits             | | |
| | | +--------------------------------------------+ | |
| | | | Checksum (16 bits)                         | | |
| | | | Urgent Pointer (16 bits)                   | | |
| | | +--------------------------------------------+ | |
| | | |                Options (Variable)           | | |
| | | +--------------------------------------------+ | |
| | | |            Payload/Data                      | | |
| | | |                    (N bytes)                | | |
| | | +--------------------------------------------+ | |
| | +------------------------------------------------+ | |
| |                             + Checksum                |
| |                             + Flags                   |
| |                             + Sequence Number         |
| |                             + Acknowledgment Number   |
| |                             + Protocol (TCP)         |
| +----------------------------------------------------+ |
+--------------------------------------------------------+

+--------------------------------------------------------+
|                      Internet Layer                    |
| +----------------------------------------------------+ |
| |                     IP Packet                      | |
| | +------------------------------------------------+ | |
| | |                IP Header                        | | |
| | | +--------------------------------+ +-------------+ | |
| | | | Version | IHL | Type of Service | Total Length | | |
| | | |    4    |  4  |       8 bits      |   16 bits   | | |
| | | +--------------------------------+ +-------------+ | |
| | | | Identification (16 bits)                    | | |
| | | +---------------------------------------------+ | |
| | | | Flags  | Fragment Offset (13 bits)          | | |
| | | +---------------------------------------------+ | |
| | | | Time to Live | Protocol (8 bits)             | | |
| | | |   [1: ICMP]  [2: IGMP]  [6: TCP]            | | |
| | | +---------------------------------------------+ | |
| | | | Header Checksum (16 bits)                   | | |
| | | | Source IP Address (32 bits)                  | | |
| | | | Destination IP Address (32 bits)             | | |
| | | +---------------------------------------------+ | |
| | | |                   Options (Variable)         | | |
| | | +---------------------------------------------+ | |
| | | |                   Payload/Data                 | | |
| | | |                     (M bytes)                 | | |
| | | +---------------------------------------------+ | |
| | +------------------------------------------------+ | |
| |                             + Checksum                |
| |                             + Flags                   |
| |                             + Total Length            |
| |                             + Source/Destination IP   |
| +----------------------------------------------------+ |
+--------------------------------------------------------+

+--------------------------------------------------------+
|                     ICMP Packet                        |
| +----------------------------------------------------+ |
| |                     ICMP Header                    | |
| | +--------------------------------------------+    | |
| | | Type (8 bits)                           |      | |
| | | Code (8 bits)                           |      | |
| | | Checksum (16 bits)                     |      | |
| | | Identifier (16 bits)                  |      | |
| | | Sequence Number (16 bits)              |      | |
| | +--------------------------------------------+    | |
| | | Payload/Data (Variable Length)           |      | |
| | +--------------------------------------------+    | |
| +----------------------------------------------------+ |
|                             + Checksum                |
|                             + Type                   |
|                             + Code                   |
+--------------------------------------------------------+

+--------------------------------------------------------+
|                     IGMP Packet                        |
| +----------------------------------------------------+ |
| |                     IGMP Header                    | |
| | +--------------------------------------------+    | |
| | | Type (8 bits)                           |      | |
| | | Max Response Time (8 bits)             |      | |
| | | Checksum (16 bits)                     |      | |
| | | Group Address (32 bits)                |      | |
| | +--------------------------------------------+    | |
| | | Payload/Data (Variable Length)           |      | |
| | +--------------------------------------------+    | |
| +----------------------------------------------------+ |
|                             + Checksum                |
|                             + Type                   |
|                             + Group Address          |
+--------------------------------------------------------+
+-------------------------------------------------------------+
|                    ARP Datagram                             |
| +---------------------------------------------------------+ |
| | Hardware Type (16 bits)                                 | |
| |      - 1: Ethernet                                      | |
| |      - 6: IEEE 802.3                                    | |
| +---------------------------------------------------------+ |
| | Protocol Type (16 bits)                                 | |
| |      - 0x0800: IPv4                                     | |
| +---------------------------------------------------------+ |
| | Hardware Size (8 bits)                                  | |
| |      - 6: MAC Address                                   | |
| +---------------------------------------------------------+ |
| | Protocol Size (8 bits)                                  | |
| |      - 4: IPv4 Address                                  | |
| +---------------------------------------------------------+ |
| | Opcode (16 bits)                                        | |
| |      - 1: Request                                       | |
| |      - 2: Reply                                         | |
| +---------------------------------------------------------+ |
| | Sender MAC Address (48 bits)                            | |
| +---------------------------------------------------------+ |
| | Sender IP Address (32 bits)                             | |
| +---------------------------------------------------------+ |
| | Target MAC Address (48 bits)                            | |
| +---------------------------------------------------------+ |
| | Target IP Address (32 bits)                             | |
| +---------------------------------------------------------+ |
| | Optional Padding (Variable Length)                      | |
| +---------------------------------------------------------+ |
+-------------------------------------------------------------+
+--------------------------------------------------------+
|                    Data Link Layer                    |
| +----------------------------------------------------+ |
| |                     Ethernet Frame                  | |
| | +------------------------------------------------+ | |
| | |                   Ethernet Header                 | | |
| | | +-----------------------------------+ +-----------+ | |
| | | | Destination MAC Address (48 bits) | | Source MAC Address (48 bits) | | |
| | | +-----------------------------------+ +-----------+ | |
| | | | Type (Ethertype) (16 bits)            | | | 
| | | | [0800: IP] [0806: ARP] [0001: IGMP]  | | |
| | | +-------------------------------------+  | | | 
| | | |               Payload/Data            |  |   | 
| | | |                    (D bytes)          |  |   |
| | | +-------------------------------------+  |   |
| | | |               Frame Check Sequence (FCS) (32 bits)                 | |
| | | +----------------------------------------------------+ |
| | +----------------------------------------------------+ |
| +--------------------------------------------------------+
|                             + FCS                     |
|                             + Type                    |
|                             + Destination/Source MAC   |
+--------------------------------------------------------+
```

### Changes Made

1. **Application Layer**: The top layer is where the DNS protocol resides.
2. **Transport Layer**: The TCP segment displays as it properly belongs in this segment of the stack.
3. **Internet Layer**: ICMP and IGMP are indicated within the protocol section, showing that they operate at this layer.
4. **Data Link Layer**: Ethernet frame is shown here, accurately reflecting its place in the networking stack.

```plaintext
+------------------+
|    Application    |
|    Layer          |
|  +--------------+ |
|  |  DNS         | |  <- Uses UDP
|  +--------------+ |
|                  |
|  +--------------+ |
|  |  HTTP        | |  <- Uses TCP
|  +--------------+ |
|                  |
|  +--------------+ |
|  |  FTP         | |  <- Uses TCP
|  +--------------+ |
|                  |
|  +--------------+ |
|  |  SMTP        | |  <- Uses TCP
|  +--------------+ |
+------------------+

+------------------+
|    Transport      |
|    Layer          |
|  +--------------+ |
|  |  TCP         | |  <- Reliable, Connection-Oriented
|  +--------------+ |
|  |  UDP         | |  <- Unreliable, Connectionless
|  +--------------+ |
|  |  IGMP        | |  <- Internet Group Management Protocol
|  +--------------+ |
+------------------+

+------------------+
|    Internet       |
|    Layer          |
|  +--------------+ |
|  |  IP          | |  <- Internet Protocol
|  +--------------+ |
|  |  ICMP        | |  <- Internet Control Message Protocol
|  +--------------+ |
|  |  ARP         | |  <- Address Resolution Protocol
|  +--------------+ |
+------------------+

+------------------+
|    Link          |
|    Layer          |
|  +--------------+ |
|  |  Ethernet     | |
|  +--------------+ |
|  |  Wi-Fi        | |
|  +--------------+ |
+------------------+
```

### PDU Sizes Summary for ASCII Art

#### TCP Segment

Total Size: 20 + N (TCP Header + Data)

#### IP Packet

Total Size: 20 + M (IP Header + Data)

#### Ethernet Frame

Total Size: 14 + D + 4 (Ethernet Header + Data + FCS)

### Explanation of the Above Sections

1. **TCP Segment:**
   - **TCP Header**: Includes fields such as Source Port, Destination Port, Sequence Number, Acknowledgment Number, Flags, and Checksum.
     - **Flags**: Control flags like SYN, ACK, FIN, etc.
     - **Checksum**: For error-checking the header and data.
     - **Payload/Data**: The actual data being transmitted.

2. **IP Packet:**
   - **IP Header**: Contains fields like Version, Header Length (IHL), Type of Service, Total Length, and more.
     - **Checksum**: Verifies the integrity of the packet.
     - **Source and Destination IP Addresses**: Indicate where the packet is from and going.

3. **Ethernet Frame:**
   - **Ethernet Header**: Includes Destination and Source MAC Addresses, and Ethertype.
     - **Payload/Data**: The data being carried.
     - **Frame Check Sequence (FCS)**: A CRC value used for integrity checking.

### Conclusion

These representations showcase how protocol headers, checksums, flags, and the contents of PDUs are structured at different layers of the OSI model. Each protocol has defined fields to manage the transmission of data effectively, ensuring integrity and proper delivery across networks.

---

## TCP/IP

or Internet Protocol Suite, is a more streamlined networking framework compared to the OSI model. It consists of four layers, each corresponding to certain functionalities in the network communication process. Here’s a breakdown of the TCP/IP model layers:

1. **Application Layer**: This is the topmost layer of the TCP/IP model. It encompasses all protocols that provide services directly to user applications. This layer is responsible for processes such as data formatting, encryption, and application-level interactions. Common protocols include:
   - **HTTP/HTTPS**: For web browsing.
   - **SMTP**: For email transmission.
   - **FTP**: For file transfer.
   - **DNS**: For domain name resolution[S1].

2. **Transport Layer**: This layer provides reliable or unreliable delivery of data between applications. It ensures that messages are delivered in the correct order and without errors. The key protocols at this layer are:
   - **TCP (Transmission Control Protocol)**: Provides **reliable, connection-oriented service with error recovery and flow control**.
   - **UDP (User Datagram Protocol)**: Provides an **unreliable, connectionless service suitable for applications that require fast transmission without the overhead of reliability.**[S1]

3. **Internet Layer**: The internet layer is responsible for **addressing, packaging, and routing functions**. It manages the delivery of packets across different networks and provides logical addressing through IP addresses. Key protocols include:
   - **IP (Internet Protocol)**: The primary protocol for **routing packets** across networks (with versions IPv4 and IPv6).
   - **ICMP (Internet Control Message Protocol)**: Used for **diagnostic and error-reporting**[S1] purposes (e.g., ping).
   - **ARP (Address Resolution Protocol)**: **Resolves IP addresses to MAC addresses.**[S1]

4. **Network Interface Layer (or Link Layer)**: This is the lowest layer, which is responsible for the physical transmission of data over a network medium. It encompasses the hardware and protocols that operate on the local network segment. Functions include **framing, addressing, and error detection.** Common protocols and technologies at this layer include:
   - **Ethernet**: The standard for wired local area networks (LAN).
   - **Wi-Fi**: Wireless local area networking technology.
   - **PPP (Point-to-Point Protocol)**: Used for direct connections between two network nodes.

### Summary

- **Application Layer**: Interfaces with user applications.
- **Transport Layer**: Handles end-to-end communication and error-checking.
- **Internet Layer**: Manages packet addressing and routing.
- **Network Interface Layer**: Deals with the physical transmission of data.

---

## Network Islolation

### assets on net

- Internal [firewalls](./firewall.md)
- [Access control list(ACL)](../identification/identification.md)
- Demateralized Zone(DMZ)

#### DMZ

- DNS
- FTP
- VoIP
- Web Servers
