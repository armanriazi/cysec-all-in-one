
### ARP Cheat Sheet

#### Overview

- **ARP (Address Resolution Protocol)** is used to map IP addresses to MAC (Media Access Control) addresses. It operates at the Data Link Layer (Layer 2) of the OSI model.

#### Common Uses

- Resolving IP addresses to MAC addresses for communication within a local area network (LAN).

#### ARP Message Types

| ARP Type    | Description                                   | Purpose                                      |
|-------------|-----------------------------------------------|----------------------------------------------|
| ARP Request | A request to find the MAC address associated with an IP address. | Used to dynamically discover MAC addresses.   |
| ARP Reply   | Response to an ARP request, containing the MAC address corresponding to the requested IP. | Provides the MAC address for the IP address asked. |

#### ARP Packet Structure

| Field                | Size (bits) | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| Hardware Type        | 16          | Type of network (Ethernet is 1)                      |
| Protocol Type        | 16          | Protocol type (IPv4 is 0x0800)                       |
| Hardware Address Length | 8         | Length of the MAC address (typically 6)              |
| Protocol Address Length | 8         | Length of the IP address (typically 4)               |
| Operation            | 16          | 1 = Request, 2 = Reply                                |
| Sender MAC Address   | 48          | MAC address of the sender (the requester)            |
| Sender IP Address    | 32          | IP address of the sender                             |
| Target MAC Address   | 48          | MAC address of the target (empty in ARP requests)    |
| Target IP Address    | 32          | IP address of the target                             |

