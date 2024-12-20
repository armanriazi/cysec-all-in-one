
### IGMP Cheat Sheet

#### Overview

- **IGMP (Internet Group Management Protocol)** is used by hosts and adjacent routers on an IP network to establish multicast group memberships. It operates at the Network Layer (Layer 3) of the OSI model.

#### Common Uses

- Managing and controlling multicast groups in an IPv4 network.

#### IGMP Message Types

| IGMP Type     | Description                                   | Purpose                                      |
|---------------|-----------------------------------------------|----------------------------------------------|
| Membership Query | Message sent by routers to ask which multicast groups are joined by hosts. | Used to learn about group memberships.       |
| Membership Report | Sent by hosts to report their multicast group memberships to routers. | Informs routers of the active memberships.   |
| Leave Group    | Informs routers that a host is leaving a multicast group. | Signals that the group should be maintained or closed if empty. |

#### IGMP Packet Structure

| Field                | Size (bits)  | Description                                          |
|----------------------|--------------|------------------------------------------------------|
| Type                  | 8            | Type of IGMP message (e.g., Query, Report)         |
| Max Response Time     | 8            | Time allowed before responding to a Query           |
| Checksum              | 16           | Error-checking field                                 |
| Group Address         | 32           | Address of the multicast group                       |
| Source Address        | 32           | Address of the host sending the report (optional)    |
