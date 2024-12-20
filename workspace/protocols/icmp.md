Here’s a concise cheat sheet for the Internet Control Message Protocol (ICMP), including information about its types, error handling, and queries presented in tabular format for clarity.

### ICMP Cheat Sheet

---

#### Overview

- **ICMP** (Internet Control Message Protocol) is a network layer protocol used by network devices to send error messages and operational information indicating success or failure during communication.

#### Common Uses

- **Error Reporting:** Notify hosts of issues in communications.
- **Diagnostics:** Used in tools like `ping` and `traceroute`.

---

### ICMP Types Table

| ICMP Type | Description                                    | Code | Common Usage               |
|-----------|------------------------------------------------|------|----------------------------|
| 0         | Echo Reply                                     | 0    | Respond to ping requests    |
| 3         | Destination Unreachable                        | 0-15 | Indicate unreachable hosts/ports |
| 4         | Source Quench                                  | 0    | Request sender to decrease transmission rate |
| 5         | Redirect                                       | 0-1  | Notify hosts of better routes |
| 8         | Echo Request                                   | 0    | Initiate ping requests      |
| 11        | Time Exceeded                                  | 0-1  | Indicate packet hop limit exceeded |
| 12        | Parameter Problem                              | 0-1  | Indicate an issue with header parameters |
| 13        | Timestamp Request                              | 0    | Request timestamp from the destination |
| 14        | Timestamp Reply                                | 0    | Respond to timestamp requests |
| 15        | Information Reply                              | 0    | Not commonly used           |

---

### ICMP Error Handling Table

In the context of ICMP (Internet Control Message Protocol), the numbers **3** and **0** refer to specific fields in the ICMP message that indicate the type of error and the code associated with that type.

### ICMP Error Message Structure

ICMP messages typically have the following header fields:

1. **Type (8 bits):** Indicates the type of the message (e.g., error message or echo request).
2. **Code (8 bits):** Provides additional context for the type (gives more specific information about the error).
3. **Checksum (16 bits):** Used for error-checking the header and data.
4. **Unused (32 bits):** Usually set to zero, used in some ICMP types for future use.
5. **Identifier (16 bits):** An identifier used for matching requests with replies (used in echo requests/replies).
6. **Sequence Number (16 bits):** A sequence number for the echo requests/replies to track multiple messages (used in echo requests/replies).

### Specific Example

For the ICMP message type you provided:

- **Type = 3:** This indicates **Destination Unreachable**, which is the type of the ICMP message.
- **Code = 0:** This indicates **Network Unreachable**.

The Type and Code together can help pinpoint exactly what the issue is within the broader category of destination unreachable messages.

### ICMP Error Handling Table (Detailed)

Here's the modified error handling table with specified headers, illustrating the connection between Type and Code:

| ICMP Type | ICMP Code | Meaning               | Recommended Action                  |
|-----------|-----------|-----------------------|-------------------------------------|
| 3         | 0         | Network Unreachable    | Check routing configuration          |
| 3         | 1         | Host Unreachable       | Verify that the target host is operational |
| 3         | 2         | Protocol Unreachable   | Check routing configuration or application protocol support |
| 3         | 3         | Port Unreachable       | Ensure that the service is running on the target |
| 11        | 0         | Time to Live Exceeded  | Examine routing paths for loops     |
| 11        | 1         | Fragment Reassembly Time Exceeded | Investigate maximum transmission unit (MTU) settings |

### Summary

- **3:** ICMP Type for "Destination Unreachable"
- **0:** ICMP Code for "Network Unreachable"

This table provides a clear understanding of the relationship between ICMP types and codes, helping network engineers and administrators troubleshoot issues effectively.

---

### ICMP Queries Table

| ICMP Type | Description                                    | Common Tools       | Example Command             |
|-----------|------------------------------------------------|---------------------|-----------------------------|
| 8         | Echo Request                                   | `ping`              | `ping [destination]`       |
| 0         | Echo Reply                                     | `ping`              | (Automatically received upon ping) |
| 13        | Timestamp Request                              | Custom Tools        | `ping -t [destination]` (with timestamp option) |
| 14        | Timestamp Reply                                | Custom Tools        | (Automatically received upon timestamp request) |

---

### Key Characteristics

- **Transport Protocol:** ICMP operates at the network layer (Layer 3) of the OSI model.
- **Connectionless:** It does not establish a connection before sending messages.
- **Error Handling:** Allows hosts to communicate error and status information back to the sender.

### Common Commands Related to ICMP

- **Ping (Echo Request):**
  - To check the reachability of a host:

  ```bash
  ping [hostname or IP]
  ```

- **Traceroute (Trace Route):**
  - To track the path packets take to reach a destination:

  ```bash
  traceroute [hostname or IP]  (Linux/Unix)
  ```

  ```bash
  tracert [hostname or IP]  (Windows)
  ```

---

This cheat sheet summarizes the key aspects of ICMP, including its function, types, error handling, and common queries. The tabular format provides easy reference to critical information, making it straightforward to understand ICMP's role in network communications.
