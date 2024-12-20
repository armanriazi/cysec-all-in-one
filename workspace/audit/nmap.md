
[T1]

## Enumeration

• Interrogate discovered services to obtain available information
• We will use nmap scripts (.nse) dpkg —L nmap -> `/usr/share/nmap/scripts/`
• Script categories:
• default, discovery, auth, safe, intrusive, exploit, dos, vuln, http

• Examples

```bash
nmap --script smb-enum-shares.nse -p'445 —n 192.168.1.1 
nmap --script smb-enum-users.nse -p 445 —n 192.168.1.1 
nmap --script discovery 192.168.1.1
nmap --script dns-zone-transfer.nse --script-args dnszonetransfer.domain=abc.xyz.com -p 53 ns.xyz.com
```

## NMap

Purpose: Nmap (Network Mapper) is primarily a network scanning tool used for network discovery and security auditing.

Key Features:

Network Discovery: Can discover hosts and services on a network, mapping out devices and their open ports.
Service and OS Detection: Nmap can identify running services and their versions, and even guess the operating system of the target devices.
Scripting Engine: Nmap supports a scripting engine (NSE) that allows users to use scripts to automate various tasks and extend functionality.
Flexible Scanning Options: Offers a variety of scanning techniques (e.g., TCP SYN scan, UDP scan), highly configurable for different scenarios.
Command-Line Based: While there are GUIs available (like Zenmap), Nmap is primarily a command-line tool, appealing to power users and network administrators.

### Usecase

- [x] Monitoring ports, etc.
- [x] Running jobs

### Sub tools

- [x] ZenMap
- [x] ZCat
- [x] NCrack
- [x] NDiff
- [x] NPing

```bash
nmap -{types(s)} -{opt(s)} {target}
```

<p align="center">
  <img src="..\assets\images\nmap1.jpg" alt="Nmap1">
</p>

<p align="center">
  <img src="..\assets\images\nmap2.jpg" alt="Nmap2">
</p>

<p align="center">
  <img src="..\assets\images\nmap-commands.jpg" alt="Nmap3">
</p>

### Using

To find open ports:

```bash
nmap -A ip
```

```bash
# do not use selay_scan with max_parallelism
nmap -P0 -n -sS --max_hostgroup 1 --max-retries 0 --max_parallelism 10 ip
```

```bash
nmap -T5 ip
```

Syn explorer:

```bash
nmap -sS -T5 ip
```

Null explorer:

```bash
nmap -sN -T5 ip
```

Ack explorer:

```bash
nmap -sA -T5 ip
```

Idle explorer:

```bash
nmap -v -O -Pn -n ip
```

Scan some IPs from a file:

```bash
nmap -iL file.txt
```

Fast scan to show open common ports

```bash
nmap -F ip
```

Scan specified range ports

```bash
nmap -p 1-1000 targetip
```

scan as a timing on Target IP

```bash
nmap -p 1-65535 -T4 -A -Pn -v targetip
```

outout scan to a file

```bash
nmap -oG testoutput.txt targetip
```

output: `Network Distance : 1 hop` means the rate/distance of a Zambii!
`TCP Sew Prediction: Difficulty=195 (Good Luck)`

So, It is not ideal rate but we can use it as a Zambii system (our target).

### Review for scanning

- [x] Sending Syn/Ack to zambii, we will get RST of a partition.
- [x] Sending a bad package to zambii
- [x] Sending RST package form zambii
- [x] Repeatting

```bash
# Pn do not need to ping
# sI doing disabled explorer on zambii sys with ip1
nmap -p ports(,,) -Pn -SI ip1 ip2
```

### Avoid penetration detection system

Messing up the information stored in the firewall and making it difficult for the system administrator to check the firewall information.

```bash
# -D doing expolorer on a bait
# -P ports
nmap -D IPs, ME -p Ports -Pn ip
# Nmap scan report for ip
```

### Scripts

#### Using buil-in scripts

```bash
cd /usr/local/share/nmap/scripts
ls -lah
nmap --script-help "banner.nse"
nmap -Pn -sC ip
nmap -v -p ports --script=smb-os-discovery targetip
```

#### Writing a customize script

```bash
# After adding Script.nse file to another scripts of nmap, run:
nmap -script-updatedb
# use created file
```

# Question[Interview]: Discussing the use of FIN/ACK scans as an alternative to SYN attacks can be advantageous for bypassing firewalls anonymously[S2]?

In a cybersecurity interview, if you're discussing techniques for bypassing firewalls or conducting reconnaissance, mentioning "FinAck" as an alternative to "SynAttack" should be approached with caution, ensuring you explain the concepts clearly and appropriately. Here's how you can elaborate on this topic:

##### Explanation of FIN/ACK and SYN Attacks

```phyton
 def analyze_packet_type(packet):
    alert_level = 'UNKNOWN'  # Default alert level
       if packet.type == 'SYN':
           # Higher chance of detection
           alert_level = 'HIGH'
       elif packet.type == 'FIN/ACK':
           # May bypass some detection methods
           alert_level = 'MEDIUM'
       return alert_level
    enumerate(numbers)

# Example usage of enumerate
numbers = [1, 2, 3, 4, 5]
for index, number in enumerate(numbers):
    print(f"Index: {index}, Number: {number}")
```

1. **SYN Attack**:
   - A SYN attack (or SYN flood attack) exploits the TCP three-way handshake process. In this attack, the attacker sends a flood of SYN (synchronize) packets to a target server with spoofed IP addresses, overwhelming the server's ability to respond and potentially causing denial of service.
   - **Detection**: Firewalls and intrusion detection systems (IDS) are often equipped to detect unusual SYN traffic patterns, making SYN attacks easier to identify.

2. **FIN/ACK Attack**:
   - A FIN/ACK attack takes advantage of TCP’s connection termination process. The attacker sends FIN (finish) packets to a target, which are used to indicate the end of a TCP connection. This can confuse firewalls and may not trigger the same defensive measures as SYN floods since FIN packets are generally associated with legitimate connection termination.
   - Such attacks are less common and can be used to probe for open ports or to bypass certain firewall restrictions, as they may not look suspicious immediately.

##### Discussion in an Interview Context

When discussing the merits of using FIN/ACK over SYN attacks during an interview, consider these aspects:

- **Stealth**: Explain that FIN/ACK packets might evade some firewall rules, particularly if the firewall mainly monitors for SYN packets.
- **Intrusion Testing**: Describe scenarios where a penetration tester might use FIN/ACK packets to check for vulnerabilities in a network's security configuration.
- **Network Behavior Understanding**: Emphasize the importance of understanding how different types of packets interact with firewalls and IDS systems, advocating for a thorough knowledge of TCP/IP and network protocols.

##### Ethical Considerations

It’s crucial to stress that any discussion of these techniques should be framed within an ethical context:

- **Legal Permission**: Engage in ethical hacking only with explicit permission from the system owner. Unauthorized attempts to exploit vulnerabilities are illegal and unethical.
- **Purpose of Knowledge**: Stress that understanding these techniques is essential for cybersecurity professionals to protect networks, conduct penetration testing responsibly, and respond to potential threats effectively.

In summary, while discussing FIN/ACK versus SYN attacks in a cybersecurity interview, you should effectively communicate the technical details, risks, and ethical implications of these methods. This approach will demonstrate not only your technical acumen but also your awareness of the importance of ethical conduct in cybersecurity practices.

Certainly! When discussing FIN/ACK and SYN attacks in a cybersecurity context, using tools like Nmap for practical demonstrations can enhance your understanding and provide concrete examples to share during your interview. Here's how you can incorporate specific Nmap commands related to these concepts:

#### Nmap and Port Scanning Techniques

##### 1. **SYN Scan Using Nmap**

A SYN scan is one of the most common methods used to identify open ports on a target system. The command for conducting a SYN scan with Nmap is:

```bash
nmap -sS <target_ip>
```

- **Explanation**: The `-sS` flag instructs Nmap to perform a SYN scan. This method sends SYN packets to ports and waits for a response to determine the state of each port (open, closed, or filtered).

##### 2. **FIN Scan Using Nmap**

A FIN scan can be used to attempt to evade firewall rules, as it sends FIN packets to probe ports. Here’s how you can perform a FIN scan with Nmap:

```bash
nmap -sF <target_ip>
```

- **Explanation**: The `-sF` flag tells Nmap to execute a FIN scan, sending FIN packets to the specified target. If a port is closed, the system will respond with a RST (reset) packet. If the port is open, there will typically be no response, which can help in determining the state of the port without triggering certain firewall rules.

##### Practical Discussion Points

When discussing these commands in your interview, consider the following points:

- **Packet Behavior**: Explain how different packets (SYN vs. FIN) interact with firewalls. For example, a SYN scan can be easily detected, while a FIN scan may be less likely to raise alarms because FIN packets are used in legitimate connection termination.
  
- **Evasion Techniques**: Highlight why understanding these techniques is essential for network security professionals. For instance, using FIN scans can help an ethical hacker determine firewall behavior without triggering standard defenses.

- **Reconnaissance Value**: Discuss the implications of these scans in reconnaissance phases of penetration testing, emphasizing the need for stealthy methods to gather information about a target without alerting them prematurely.

