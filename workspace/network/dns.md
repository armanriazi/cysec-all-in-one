Sure! Below is the combined cheat sheet that includes both the DNS records table and the command-line tools for querying and managing DNS.

---

### DNS Cheat Sheet

#### Overview

The Domain Name System (DNS) is a hierarchical naming system used to translate human-readable domain names (e.g., <www.example.com>) into numerical IP addresses (e.g., 192.0.2.1) required for locating and identifying computer services and devices.

#### Common DNS Record Types

| Record Type | Purpose                                              | Example                         |
|-------------|------------------------------------------------------|---------------------------------|
| **A**       | Maps a domain name to an IPv4 address               | example.com    -> 192.168.1.1  |
| **AAAA**    | Maps a domain name to an IPv6 address               | example.com    -> 2001:db8::1  |
| **CNAME**   | Alias one domain name to another                     | <www.example.com> -> example.com  |
| **MX**      | Specifies mail servers for the domain                | example.com    -> mail.example.com (Priority: 10) |
| **TXT**     | Holds text information for various purposes          | example.com    -> "v=spf1 include:_spf.example.com ~all" |
| **NS**      | Indicates the authoritative servers for the domain   | example.com    -> ns1.example.com |
| **SRV**     | Specifies the location of services                   | _sip._tcp.example.com -> 5 5060 sipserver.example.com |

#### Common DNS Command-Line Tools

1. **`nslookup`**: Utility for querying the DNS.

   - **Basic Query**:

     ```bash
     nslookup example.com
     ```

   - **Query a Specific Record Type (e.g., MX)**:

     ```bash
     nslookup -query=MX example.com
     ```

   - **Use a Specific DNS Server**:

     ```bash
     nslookup example.com 8.8.8.8
     ```

2. **`dig` (Domain Information Groper)**: Advanced tool for DNS queries.

   - **Basic Query**:

     ```bash
     dig example.com
     ```

   - **Query a Specific Record Type (e.g., CNAME)**:

     ```bash
     dig example.com CNAME
     ```

   - **Query with Detailed Output**:

     ```bash
     dig +short example.com
     ```

   - **Query a Specific DNS Server**:

     ```bash
     dig @8.8.8.8 example.com
     ```

3. **`host`**: Simple utility for DNS lookups.

   - **Basic Query**:

     ```bash
     host example.com
     ```

   - **Query a Specific Record Type (e.g., A)**:

     ```bash
     host -t A example.com
     ```

   - **Query a Specific Record Type (e.g., MX)**:

     ```bash
     host -t MX example.com
     ```

4. **`whois`**: Retrieves ownership and registration information for a domain.

   - **Basic Query**:

     ```bash
     whois example.com
     ```

5. **`ping`**: Resolves a hostname to an IP address.

   - **Basic Ping Command**:

     ```bash
     ping example.com
     ```

6. **`traceroute`**: Shows the path packets take to reach a domain.

   - **Basic Command**:

     ```bash
     traceroute example.com
     ```

7. **`dig` for DNSSEC** (if enabled):

   - **Query a DNSKEY Record**:

     ```bash
     dig example.com DNSKEY
     ```

   - **Query a DS Record**:

     ```bash
     dig example.com DS
     ```

### Summary

Understanding both DNS record types and common command-line tools is essential for effective domain management and troubleshooting DNS-related issues. These commands will help you query and verify DNS configurations efficiently.
