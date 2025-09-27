---
title: "CCNA IOS CLI COMMANDS"
layout: default
---
# **CCNA IOS CLI Commands Cheatsheet**
*Posted on: July 4th, 2025*
---
A practical quick-reference for Cisco IOS CLI — covering IPv4, routing, VLANs, trunking, STP, EtherChannel, and more.  
This guide is designed for **CCNA study** and my **networking homelab**.

---

This cheatsheet is a handy reference for on-premise network engineering — from configuring interfaces and VLANs to verifying routing and spanning tree — the day-to-day building blocks of managing enterprise switches and routers.

---

## IPv4 & Interface Configuration
| Command | Description |
|---------|-------------|
| `show ip interface brief` | Show status and IP info for interfaces |
| `interface <name><number>` | Enter interface configuration mode |
| `ip address <ip> <mask>` | Assign IP address and subnet mask |
| `description ## <text> ##` | Add description to interface |
| `no shutdown` | Enable interface |

**Notes:**  
- Network Address = all 0s in host section  
- Broadcast Address = all 1s in host section  
- Static routing uses IP address + exit interface  
- Netmask refers to destination subnet mask  

---

## Routing
| Command | Description |
|---------|-------------|
| `show ip route` | Show routing table |
| `ip route <dest> <mask> <next-hop>` | Add static route |
| `ip routing` | Enable Layer 3 routing on switch |
| `ip route 0.0.0.0 0.0.0.0 <next-hop>` | Default route |

**Notes:** After enabling `ip routing`, `<next-hop>` is usually the router’s IP.  

---

## VLANs
| Command | Description |
|---------|-------------|
| `show vlan brief` | Show VLANs |
| `vlan <number>` | Create/configure VLAN |
| `switchport mode access` | Configure access port for VLANs |
| `switchport access vlan <vlan-number>` | Assign access port to VLAN |

---

## Trunking
| Command | Description |
|---------|-------------|
| `show interface trunk` | Show trunk interfaces |
| `switchport mode trunk` | Configure trunk mode |
| `switchport trunk allowed vlan <list>` | Allow VLANs on trunk |
| `switchport trunk native vlan <vlan>` | Configure native VLAN |

---

## Router-on-a-Stick (ROAS)
| Command | Description |
|---------|-------------|
| `interface g0/0.<subint>` | Enter subinterface mode |
| `encapsulation dot1q <vlan>` | Set VLAN encapsulation |
| `ip address <ip> <mask>` | Assign IP to subinterface |
| `encapsulation dot1q <vlan> native` | Configure native VLAN on router subinterface |

---

## Inter-VLAN Routing (SVI)
| Command | Description |
|---------|-------------|
| `interface vlan <number>` | Create VLAN SVI (Switch Virtual Interface) |
| `ip address <ip> <mask>` | Assign IP |
| `no shutdown` | Enable SVI |

---

## Routed Ports
| Command | Description |
|---------|-------------|
| `no switchport` | Convert interface to routed port (on multilayer switches) |

---

## Show Commands
| Command | Description |
|---------|-------------|
| `show interfaces status` | Show interface status |
| `show ip interface brief` | Quick IP/interface summary |
| `show interface trunk` | Show trunks |
| `show vlan` | Show VLANs |
| `show int <interface>` | Show specific interface |
| `show ip route` | Show routing table |
| `show spanning-tree` | Show spanning tree info |
| `show spanning-tree vlan <vlan #>` | Spanning tree info for a VLAN |

---

## Defaults
| Command | Description |
|---------|-------------|
| `default interface <int>` | Reset interface to default |

---

## DTP & VTP
| Command | Description |
|---------|-------------|
| `switchport nonegotiate` | Disable DTP negotiation |
| `vtp mode transparent` | Safest setting for labs |

---

## STP
| Command | Description |
|---------|-------------|
| `spanning-tree portfast` | Enable PortFast |
| `spanning-tree portfast default` | Enable PortFast only on access ports |
| `spanning-tree bpduguard enable` | Enable BPDU guard |
| `spanning-tree bpduguard enable default` | Enable BPDU guard globally |
| `spanning-tree mode ?` | Show STP modes |
| `spanning-tree vlan <vlan> root primary` | Set switch as root bridge |
| `spanning-tree vlan <vlan> root secondary` | Set switch as secondary root |
| `spanning-tree vlan ?` | Configure STP VLAN settings |

---

## RSTP
| Command | Description |
|---------|-------------|
| `spanning-tree link-type ?` | Manually configure RSTP link type |

---

## EtherChannel
| Command | Description |
|---------|-------------|
| `port-channel load-balance <method>` | Set load-balancing algorithm |
| `show etherchannel load-balance` | Show current load-balancing method |
| `show etherchannel summary` | Show EtherChannel summary |
| `channel-group <number> mode ?` | Add interface to EtherChannel |
| `show etherchannel port-channel` | Show port-channel interface info |
| `channel-protocol <protocol>` | Force EtherChannel protocol |

---

## Floating Static Routes
| Command | Description |
|---------|-------------|
| `ip route <DEST-NETWORK> <MASK> <NEXT-HOP/EXIT-INT> [AD]` | Configure floating static route |

**Notes:**  
- `DEST-NETWORK` = Target network (e.g., `192.168.4.0`)  
- `MASK` = Subnet mask (e.g., `255.255.255.0`)  
- `NEXT-HOP` = IP of the next router  
- `[AD]` = Administrative Distance (default = 1). Use higher AD to make it “floating.”  

---

This cheatsheet is part of my CCNA prep — I’ll be adding more CLI references as I progress in my studies.
