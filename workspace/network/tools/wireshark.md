### Wireshark Capture Filters Cheat Sheet

#### Modes

- **Promiscuous mode**:

Is a network interface mode that allows the network device (NIC) to intercept and read every packet that travels across the network, regardless of its destination MAC address. This mode is particularly useful in packet capturing and network monitoring.

#### Basic Filters

- **All Traffic**: ``
- **Specific Protocol (e.g., TCP)**: `tcp`
- **Specific Protocol (e.g., UDP)**: `udp`
- **Specific Protocol (e.g., ICMP)**: `icmp`
- **Specific Protocol (e.g., HTTP)**: `tcp port 80`

#### IP Address Filters

- **Capture Traffic from a Specific IP**: `host 192.168.1.10`
- **Capture Traffic to a Specific IP**: `host 192.168.1.10`
- **Capture Traffic from a Specific Subnet**: `net 192.168.1.0/24`
- **Capture Traffic to/from Multiple IPs**: `host 192.168.1.10 or host 192.168.1.20`

#### Port Filters

- **Capture Traffic on a Specific Port**: `port 443`
- **Capture Incoming Traffic on a Specific Port**: `dst port 443`
- **Capture Outgoing Traffic on a Specific Port**: `src port 443`
- **Capture Traffic on a Range of Ports**: `portrange 8000-9000`

#### Protocol-Specific Filters

- **HTTP Traffic**: `tcp port 80 or tcp port 8080`
- **HTTPS Traffic**: `tcp port 443`
- **DNS Traffic**: `udp port 53`
- **FTP Traffic**: `tcp port 21`

#### Complex Filters

- **Combine Filters with AND**: `tcp and host 192.168.1.10`
- **Combine Filters with OR**: `tcp or udp`
- **Exclude Specific Traffic**: `tcp and not port 22`

#### Time-based Filters

- **Capture Traffic Within a Specific Time Frame** (Note: Wireshark capture filters do not provide this capability directly. Use display filters post-capture for time filtering).

### Examples

1. **Capture only TCP traffic from a specific host**:

   ```plaintext
   tcp and host 192.168.1.10
   ```

2. **Capture only HTTP and HTTPS traffic**:

   ```plaintext
   tcp port 80 or tcp port 443
   ```

3. **Capture all traffic except for DNS and HTTP**:

   ```plaintext
   not (port 53 or port 80)
   ```

4. **Capture traffic to a specific subnet, excluding a particular IP**:

   ```plaintext
   net 192.168.1.0/24 and not host 192.168.1.5
   ```

### Note

- **Capture Filters vs. Display Filters**: Capture filters are set before capturing traffic and limit what gets captured. Display filters are applied after capturing and can be used to analyze the captured packets.
- **Syntax**: Be mindful of the correct syntax for capture filters, which is slightly different from display filters.

### How to Apply Filters in Wireshark

- In Wireshark, go to **Capture Options** and enter your capture filter in the "Capture Filter" field.
  
Using the above filters will help you efficiently capture and analyze only the relevant network traffic. If you have any specific scenarios in mind or need more filters, feel free to ask!

---

Here’s a concise cheat sheet of commonly used display filters for Wireshark (as of the latest version). You can use these filters to capture or analyze specific types of network traffic more effectively.

### Wireshark Display Filters Cheat Sheet

#### Basic Protocol Filters

- **HTTP:** `http`
- **HTTPS:** `tls`
- **DNS:** `dns`
- **TCP:** `tcp`
- **UDP:** `udp`
- **ICMP:** `icmp`
- **ARP:** `arp`
- **RTP:** `rtp`
- **SMTP:** `smtp`
- **POP3:** `pop`
- **IMAP:** `imap`

#### Address and Port Filters

- **Source IP Address:** `ip.src == x.x.x.x`
- **Destination IP Address:** `ip.dst == x.x.x.x`
- **Source Port:** `tcp.srcport == 80`
- **Destination Port:** `tcp.dstport == 443`
- **Any IP Address:** `ip.addr == x.x.x.x`
- **Any TCP Port:** `tcp.port == 80`

#### Protocol and Application-Specific Filters

- **Show all HTTP requests:** `http.request`
- **Show all HTTP responses:** `http.response`
- **Show all DNS queries:** `dns.qr == 0`
- **Show all DNS responses:** `dns.qr == 1`
- **Show all traffic to a specific web server:** `http.host == "example.com"`

#### Logical Filters

- **AND Operator:** `tcp && http` (SHOW TCP packets that also contain HTTP)
- **OR Operator:** `http || dns` (SHOW HTTP or DNS packets)
- **NOT Operator:** `!http` (SHOW packets that are NOT HTTP)

#### Field Filters

- **Filtering by Content:** `frame contains "abc"` (SHOW packets containing the string "abc")
- **Filtering by Length:** `frame.len > 100` (SHOW packets longer than 100 bytes)
- **Filtering by TCP Flags:** `tcp.flags.syn == 1` (SHOW SYN packets)
  
#### Time-Related Filters

- **Filtering packets in a certain time frame:** `frame.time >= "2023-03-01 00:00:00" && frame.time <= "2023-03-02 00:00:00"`

#### Miscellaneous Filters

- **Follow TCP Stream:** `tcp.stream eq 0` (SHOW all packets in the TCP stream with index 0)
- **Coloring Filters** (to be used in the Coloring Rules):
  - **HTTP:** `http`
  - **Telnet:** `telnet`
  
### Combining Filters

You can combine filters using parentheses for complex queries:

```plaintext
((ip.src == 192.168.1.1 && tcp.dstport == 80) || (ip.src == 192.168.1.2 && tcp.dstport == 443))
```

### Additional Useful Filters

- **Malformed Packets:** `malformed`
- **Errors:** `tcp.analysis.flags`
- **Duplicate Acknowledgments:** `tcp.analysis.ack_rtt`

### Tips for Using Filters in Wireshark

- Start typing in the Display Filter toolbar; Wireshark provides autocomplete suggestions.
- Use color coding to quickly identify packets of interest based on your filters.

