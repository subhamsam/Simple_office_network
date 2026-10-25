# Simple VLAN Network

A Cisco Packet Tracer lab with 5 VLANs on two switches, connected through a router. DHCP is used for hosts ip configuration. ACL is used to prevent other vlan from accessing server at vlan 20. 

**Tool:** Cisco Packet Tracer 9.0.1
**File:** `project1_simpleNetworkDesign.pkt`

## Topology

![Topology](topology.png)

## Addressing

| VLAN | Network | Devices |
|---|---|---|
| 10 | 192.168.10.0/24 | PC0 (.1), PC1 (.2), Router1 (.10) |
| 20 | 192.168.20.0/24 | PC8 (.1), PC9 (.2), Server1 (.10) |
| 30 | 192.168.30.0/24 | PC2 (.1), PC3 (.2) |
| 40 | 192.168.40.0/24 | PC4 (.1), PC5 (.2) |
| 50 | 192.168.50.0/24 | PC6 (.1), PC7 (.2) |

- **Switch0:** VLANs 10, 30, 40
- **Switch1:** VLANs 20, 50
- **Router0:** connects both switches and routes between VLANs
- **DHCP:** for automatically provide ip address

## What I did

1. Created the VLANs and assigned the ports on both switches.
2. Connected the switches to Router0.
3. Set up routing between the VLANs on Router0.
4. Gave every device an IP address with DHCP server.
5. Tested with ping.
6. Add ACLs to prevent hosts from other vlan from accessing server
   at vlan 20.

## Tests

| Test | Result |
|---|---|
| PC0 to PC1 (same VLAN) | Pass |
| PC0 to PC2 (VLAN 10 to 30) | Pass |
| PC0 to PC6 (VLAN 10 to 50) | Pass |
| vlan10 to Server1 | failed | acls working fine |
| vlan20 to server1 | passed | acls working fine |

## How to open

Open the `.pkt` file in Cisco Packet Tracer 9.0.1 or later.

## What I learned

VLANs, trunk and access ports, and routing between VLANs , DHCP server, ACL configuration
