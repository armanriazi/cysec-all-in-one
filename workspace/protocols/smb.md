### SMB Cheat Sheet

#### Overview

- **SMB (Server Message Block)** is a network file sharing protocol used for providing shared access to files, printers, and serial ports. It operates at the Application Layer (Layer 7) of the OSI model.

#### Common Uses

- Accessing files and networks shares on remote servers.
- Printing to shared printers on the network.
- Interprocess communication between programs on the same server.

#### Common SMB Message Types

| SMB Message Type        | Description                                         | Purpose                                        |
|-------------------------|-----------------------------------------------------|------------------------------------------------|
| SMB_COM_READ            | Request to read a file from the server.            | Used to retrieve the contents of a file.      |
| SMB_COM_WRITE           | Request to write data to a file on the server.     | Used to modify an existing file or create a new one. |
| SMB_COM_CREATE          | Request to create a new file or directory.         | Used for creating new resources in shared folders. |
| SMB_COM_DELETE          | Request to delete a file or directory.              | Used to remove files or folders from the server. |
| SMB_COM_TRANSACTION      | Perform a transaction over the SMB session.        | Used for complex operations that require multiple steps. |

#### SMB Packet Structure

| Field                     | Size (bytes) | Description                                                   |
|---------------------------|--------------|---------------------------------------------------------------|
| Protocol ID               | 2            | Always set to 0xFF534D42 ('SMB')                             |
| Command                   | 1            | Indicates the type of SMB command being issued               |
| Error Code                | 2            | Error code indicating the result of the SMB command          |
| Flags                     | 2            | Flags indicating various options (e.g., case sensitivity)    |
| PID High                  | 2            | High word of the process ID                                   |
| UID                       | 2            | User ID assigned when a connection is established             |
| MID                       | 2            | Multiplexer ID for tracking requests                           |
| Word Count                | 1            | Number of words in the parameter block                        |
| Parameter Block           | Variable      | Parameters specific to the command being requested            |
| Data Block                | Variable      | Contains the data associated with the request (file contents, etc.) |

#### Common SMB Ports

| Port  | Description                                        |
|-------|----------------------------------------------------|
| 445   | Direct SMB over TCP without NetBIOS encapsulation. |
| 139   | SMB over NetBIOS, commonly used for legacy systems. |

#### Security Considerations

- **SMB Signing:** Provides integrity and authenticity for SMB communications.
- **SMB Encryption:** Protects data in transit to prevent eavesdropping and tampering.
- **Guest Access:** Should be disabled to prevent unauthorized access to shared resources.

#### Common Commands for SMB Scanning and Enumeration

| Command                                     | Description                                      |
|---------------------------------------------|--------------------------------------------------|
| `nmap -p 445 --script=smb-os-discovery <target>` | Discover the operating system on a target SMB server. |
| `nbtscan -r <target>`                       | Scans for NetBIOS services and shares on target IPs.  |
| `enum4linux -a <target>`                    | Enumerates SMB shares, users, and groups from a target. |

This cheat sheet provides a quick reference for understanding and utilizing the SMB protocol, including its structure, common commands, and security considerations.