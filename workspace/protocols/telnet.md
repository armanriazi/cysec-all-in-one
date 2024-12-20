### Understanding Telnet Modes: Active and Passive Connections

When it comes to Telnet, while it traditionally focuses on establishing direct connections, informal references to "active" and "passive" modes can be made regarding its use and data flow. Here’s a combined guide focusing on how these modes manifest in a Telnet context, emphasizing a passive mode scenario alongside a practical example.

### List of commands

| **Command** | **Protocol** | **Description**                                     |
|-------------|--------------|-----------------------------------------------------|
| `telnet <hostname> <port>` | Telnet        | Establish an active connection to the specified hostname and port. |
| `PASV`      | FTP          | Request the server to enter passive mode, providing an IP address and port for the client to connect to for data transfer. Also returns a response indicating the passive connection details. |
| `PORT`      | FTP          | The command used by the client in active mode to specify the IP address and port where the server should connect back for data transfer. |
| `USER <username>` | FTP          | Send username for authentication when connecting to an FTP server. |
| `PASS <password>` | FTP          | Send password for authentication after the `USER` command in FTP sessions. |
| `GET <file>` | FTP          | Request to retrieve a file from the FTP server.       |
| `PUT <file>` | FTP          | Send a file to the FTP server for storage.             |
| `LIST`      | FTP          | Request to list the files and directories in the current directory on the FTP server.  |
| `STAT`      | FTP          | Request status of the current connection or specific file in the FTP protocol.      |
| `QUIT`      | Telnet/FTP   | Terminate the Telnet or FTP session gracefully.         |
| `HELP`      | Telnet/FTP   | Request a list of supported commands or help information. |

### Explanation of Some Key Commands

- **PASV**: This command allows the FTP client to enter the passive mode, where the server informs the client of the IP address and port number to use for the data connection. It is crucial for clients behind firewalls or NAT that cannot accept incoming connections.
- **PORT**: In contrast to passive mode, the PORT command is used in active mode, where the client specifies its own IP and port for the server to connect back to.
- **GET/PUT**: These commands are commonly used in FTP for downloading (GET) or uploading (PUT) files.

### Note

While Telnet does not have an extensive command set like FTP, its primary role is to provide a command-line interface to interact with remote servers. Still, some of these commands highlight the distinctions between how data connections can be established in various protocols.

#### 1. Active Mode

In an **active** mode scenario, the Telnet client proactively connects to a Telnet server. Here’s how this works:

- **Establishing an Active Telnet Connection**:
  1. Open the Command Prompt (Windows) or Terminal (Linux/Mac).
  2. Use the command:

     ```bash
     telnet <hostname or IP address> <port>
     ```

     - **Example**: To connect to a Telnet server at `192.168.1.10` on the default Telnet port (23):

     ```bash
     telnet 192.168.1.10 23
     ```

- **Connection Process**:
  - This command generates a **SYN** packet from the client to the server’s port, opening a TCP connection. Once connected, the client can send commands and receive responses.

#### 2. Passive Mode Scenario

While Telnet lacks a formal “passive” mode like FTP, a **passive-like approach** can be simulated. In this context, the passive mode emphasizes observing without actively sending commands immediately after connection, perhaps by waiting for incoming data.

1. **Connecting using Passive Mode Logic**:
   - When interacting with a server expecting a response after the `PASV` command (akin to FTP), you might simulate a passive environment through tools.

2. **Example of a Telnet-style PASSIVE Connection**:
   - After connecting to the server, let’s assume the server provides a simulated passive output (akin to FTP's PASV output). Using Telnet, send a hypothetical PASV command:

     ```bash
     pasv
     ```

   - The server then responds with an IP address and two port numbers in a format such as:

     ```
     227 Entering Passive Mode (192,168,1,10,196,12)
     ```

   - The example IP shows the server's address as `192.168.1.10`, and the port numbers as `196` and `12`.

3. **Calculating the Listening Port**:
   - Convert the returned data from the PASV response into the actual port number:
     - Formula: **Port = (HighByte * 256) + LowByte**
     - From the example above:
       - HighByte = `196`
       - LowByte = `12`
     - The calculation is as follows:

       ```
       Port = (196 * 256) + 12
            = 50176 + 12
            = 50188
       ```

   - Understanding how to manipulate the response allows the user to determine which port to connect to next, providing a low-level interaction with the server in a simulated passive mode.

Finnaly to connect to source from destination we put in:

```bash
telnet ip 50188
```

### Wireshark Monitoring: Capturing Telnet Traffic

#### Step-by-Step Wireshark Monitoring

Statistics=>conversations=>IPv4=>Apply as Filter=> Selected `A->B`
Filter `FTP` protocol and then Click Right=>Follow=>TCP Stream. Will see all of prior put in commands.

### Summary

- **Active Mode**: Initiated via a straightforward Telnet command, where the client actively connects to the server.
- **Passive Mode**: Simulated by waiting for server data, potentially after considered commands like `PASV`, and interpreting responses (e.g., calculating port numbers).
- **Wireshark**: A powerful tool for visualizing and analyzing all ongoing Telnet communications.

### Security Note

Always remember that Telnet transmits data unencrypted. For secure communications, consider using protocols like SSH, which provide necessary authentication and encryption layers.
