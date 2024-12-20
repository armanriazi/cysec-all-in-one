# Network

Thank you for providing the TCP Wrappers content. I'll correct and fix errors, elaborate on the commands, and provide explanations for each part. Here's the corrected and expanded version:

### TCP Wrappers

```bash
# Check if the SSH daemon is linked against libwrap
ldd /usr/sbin/sshd | grep libwrap

# Navigate to the /etc directory
cd /etc/

# List files in the /etc directory
ls -l | grep hosts

# If hosts.allow or hosts.deny don't exist, create them
touch hosts.allow hosts.deny

# Edit the hosts.allow file
nano hosts.allow

# Add these options, possibly one of them:
sshd, telnet, ftp: 192.168.12.133 DENY
ALL: ALL
ALL: LOCAL
ALL: KNOWN
ALL: UNKNOWN
ALL: PARANOID

# Exit nano
exit

# Edit the hosts.deny file
nano hosts.deny

# Add this line to hosts.deny
ALL EXCEPT sshd: ALL

# Exit nano
exit

# Test SSH access
ssh user@ip

# If successful, test again after modifying hosts.deny
ssh user@ip
```

### Explanation of TCP Wrappers Commands

1. `ldd /usr/sbin/sshd | grep libwrap`: Checks if the SSH daemon is linked against libwrap, which is necessary for TCP Wrappers functionality.

2. `cd /etc/` and `ls -l | grep hosts`: Navigate to the /etc directory and list files related to hosts.

3. `touch hosts.allow hosts.deny`: Creates these files if they don't exist.

4. `nano hosts.allow`: Edits the file that allows access to services.

5. In `hosts.allow`, the options mean:
   - `sshd, telnet, ftp: 192.168.12.133 DENY`: Denies access from the specified IP address for SSH, Telnet, and FTP services.
   - `ALL: ALL`: Allows all services for all clients (this overrides more specific rules).
   - `ALL: LOCAL`: Allows local connections.
   - `ALL: KNOWN`: Allows known hosts.
   - `ALL: UNKNOWN`: Allows unknown hosts (use with caution).
   - `ALL: PARANOID`: Allows paranoid mode (blocks packets without source IP).

6. `exit` exits the nano editor.

7. `nano hosts.deny`: Edits the file that denies access to services.

8. In `hosts.deny`, `ALL EXCEPT sshd: ALL` means deny all services except SSH for all clients.

9. `ssh user@ip`: Tests SSH access before and after modifications.

TCP Wrappers work by reading both `/etc/hosts.allow` and `/etc/hosts.deny` files in order. The first matching rule determines the outcome:

- A match in `hosts.allow` grants access.
- A match in `hosts.deny` denies access.

If there's no match in either file, access is granted by default.

Remember to restart affected services after making changes to these files for them to take effect. Also, be cautious when using wildcards and broad rules, as they can potentially lock you out of your system if not configured correctly.

## Curl

- Using curl command to ckeck status of 'Access-Control-Allow-Origin'

```bash
curl -I -X OPTIONS \                                                                                                                              
  -H "Origin: http://192.168.33.18:4000" \
  -H 'Access-Control-Request-Method: POST' \
  'http://192.168.33.18:4000/api/contact-us/message' 2>&1 | grep 'Access-Control-Allow-Origin'
```

```bash
curl -X POST http://..com -d '' | grep x | wc –l
```

### Iptable

In `iptables`, the terms "DROP" and "REJECT" refer to two different actions that can be taken on packets that match a specified rule. Here’s a breakdown of the differences along with the states that include these actions:

### Difference Between DROP and REJECT

| Feature             | DROP                                        | REJECT                                      |
|---------------------|--------------------------------------------|---------------------------------------------|
| Action              | Silently discard the packet                | Send an error response back to the sender  |
| Response to Sender  | None (no notification)                     | Yes (ICMP response or TCP RST)             |
| Use Case            | Use when you want to be stealthy          | Use when you want to inform the sender     |
| Performance Impact  | Generally lower overhead due to no reply   | Slightly higher overhead due to reply       |

### Packet States in iptables

In `iptables`, rules can be defined for various states of connection tracking. The states are usually as follows:

| State         | Description                                               |
|---------------|----------------------------------------------------------|
| NEW           | A packet that starts a new connection                    |
| ESTABLISHED   | A packet that is part of an existing connection           |
| RELATED       | A packet that is related to an existing connection        |
| INVALID       | A packet that doesn't match any known connection          |
| UNTRACKED     | A packet that bypasses connection tracking                |

### Summary of States with DROP and REJECT

When configuring `iptables`, you can specify rules based on these connection tracking states. Both `DROP` and `REJECT` can be used in conjunction with any of these states, but you would typically use:

- **DROP** for connections you want to ignore completely (e.g., due to security policies).
- **REJECT** for connections where you want to communicate that the packet is not allowed (helpful for debugging or user feedback).

[IP Table Commands](./iptable.md)

### netsh

```bash
netsh interface portproxy add v4tov4 listenport=35999 listenaddress=0.0.0.0 connectport=80 connectaddress=0.0.0.0
```

```bash
netsh http delete urlacl url=http://*:35999/ user=Everyone
```

### netstat

```bash
service ssh start
netstat -antp|grep ssh
```

## Mac Address

Show:

```bash
arp -a
```
