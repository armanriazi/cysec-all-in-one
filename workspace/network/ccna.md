## Introduction

<p align="center">
  <img src="..\assets\images\pdu.jpg" alt="PDU">
</p>

<p align="center">
  <img src="..\assets\images\ether-frame.jpg" alt="Ethernet frame">
  Preamble is the type of ethernet standard e.g, 1Gbps, 10Gbps, etc.
  All of frame sections will check by CRC and then results will put in to FCS block.
</p>

<p align="center">
  <img src="..\assets\images\cisco-icons.png" alt="ICONS">
</p>

## VLANs

<p align="center">
  <img src="..\assets\images\vlan-ranges.jpg" alt="Vlan Ranges">
</p>

VLAN will be configured in the OS of cisco switch.
VTP does not learn extended range VLANs (1005-4096).  
VLAN tag is used for identify packets on Native link.

### Vlan Types

- [x] Data: Seperating user data
- [x] Default: is 1 controling CDP, STP
- [x] Native: 802.1Q trunk port.tagged/untaged mechanism,
- [x] Management: admin configuration
- [x] Voice: VOIP with top priority than other kinds of VLANs.

### Link Types

- [x] Access: Only for carrying 1 VLAN
- [x] Native: multiple VLAN for carrying.

Here's the updated comparative table including the tagging rules for both ISL and IEEE 802.1Q:

| Feature                         | ISL (Inter-Switch Link)                              | IEEE 802.1Q                                    |
|---------------------------------|------------------------------------------------------|------------------------------------------------|
| **Type**                        | Cisco proprietary                                    | Open standard                                   |
| **Tagging Method**             | Adds a header (26 bytes) to the original frame with a VLAN field | Inserts a 4-byte tag (802.1Q header) in the Ethernet frame |
| **VLAN ID Size**               | Supports up to 1005 VLANs (0-1024 usable)           | Supports up to 4096 VLANs (0-4095 usable)     |
| **Frame Size**                 | Maximum frame size increases to 1522 bytes          | Maximum frame size remains at 1518 bytes       |
| **Trunking Protocol**          | Used primarily in Cisco devices                      | Widely used across multi-vendor environments    |
| **Compatibility**              | Limited to Cisco devices and implementations          | Supported by multiple vendors                   |
| **Overhead**                   | Higher due to additional header                      | Lower overhead with just 4-byte tagging        |
| **Performance**                | Potentially lower due to proprietary nature          | Generally better for mixed-vendor environments  |
| **Precedence**                 | Allows for more complex implementations               | Simpler and more standardized implementation      |
| **Tagging Rule**               | Adds a proprietary ISL header, encapsulating the original frame | Uses a standardized 802.1Q header, tagging the original Ethernet frame |

### Summary

- **ISL** is a Cisco proprietary protocol offering basic trunking capabilities, with a larger overhead for VLAN tagging and limited support for a specific number of VLANs (1005). It primarily operates in Cisco networking environments.
  
- **IEEE 802.1Q** is an open standard protocol that adds a tagging method using a 4-byte header to support a larger number of VLANs (4096). It is more widely supported and allows for interoperability across diverse vendors.

When choosing between ISL and IEEE 802.1Q, the decision largely depends on the hardware environment, compatibility needs, the number of VLANs required, and the specific requirements for performance and overhead in a given network.

<p align="center">
  <img src="..\assets\images\vlan-tag.jpg" alt="Vlan Ranges">
</p>

<p align="center">
  <img src="..\assets\images\vlan-802q.jpg" alt="Vlan Ranges">
</p>

### Native VLANs

Un-Tagged Frames on the native VLAN.

• When a Cisco switch trunk port receives untagged frames it forwards those frames to the native VLAN.

• Default native VLAN is VLAN 1.

• When you configure an 802.1Q trunk port, a default Port VLAN ID (PVID) is assigned the value of the native VLAN.

• All untagged traffic coming in or out of the 802.1Q port is forwarded based on the PVID value.

• Control traffic sent on the native VLAN should be untagged.

• If an 802.1Q trunk port receives a tagged frame on the NATIVE VLAN ONLY, it drops the frame.

• When configuring a switch port on a Cisco switch, you need to identify these devices and configure them so that they do not send tagged frames on the native VLAN.

<p align="center">
  <img src="..\assets\images\vlan-table.jpg" alt="Vlan Table">
</p>

**Note:** untagged traffic can be passed to a native VLAN in IEEE 802.1Q trunking.

### Native VLAN

- The **native VLAN** receives untagged traffic on a trunk port, typically configured as VLAN 1 (but can be any VLAN).

### Key Points

- **Untagged Traffic**: Frames without VLAN tags are associated with the native VLAN.
- **Mixed Traffic**: Trunk ports carry both tagged and untagged traffic, where untagged frames belong to the native VLAN.

### Security Implications

- Using native VLANs can introduce security vulnerabilities, such as VLAN hopping, where an attacker can send malicious untagged traffic to gain unauthorized access to other VLANs or devices[N1].

### Conclusion

It is possible to exploit the native VLAN feature to send malicious traffic, which can compromise network security. It’s crucial to configure native VLANs carefully, keep them consistent, and minimize exposure to untrusted traffic.

## Dynamic Trunking Protocol (DTP)

• Cisco proprietary protocol. Switches from other vendors do not support DTP.

• Automatically enabled on a switch port when certain trunking modes are configured on the switch port.

• DTP manages trunk negotiation only if the port on the other switch is configured in a trunk mode that supports DTP. • DTP supports both ISL and 802.1 Q trunks.

<p align="center">
  <img src="..\assets\images\trunk-table.jpg" alt="Trunk- Table">
  Connection between 2 switch
</p>
