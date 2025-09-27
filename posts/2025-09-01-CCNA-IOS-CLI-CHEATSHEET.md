---
title: "CCNA IOS CLI Commands Cheatsheet"
layout: page
---
*Posted on: September 1st, 2025*
A practical quick-reference for Cisco IOS CLI — covering IPv4, routing, VLANs, trunking, STP, EtherChannel, and more. This guide is designed for **CCNA study** and my **networking homelab**.
---
This cheatsheet is a handy reference for on-premise network engineering — from configuring interfaces and VLANs to verifying routing and spanning tree — the day-to-day building blocks of managing enterprise switches and routers.
---
# **CCNA IOS CLI Cheatsheet** 
| Command | Description |
| :---- | :---- |
| **IPv4 & Interface Configuration** |  |
| `show ip interface brief` | Show status and IP info for interfaces |
| `interface <name><number>` | Enter interface configuration mode |
| `ip address <ip> <mask>` | Assign IP address and subnet mask |
| `description ## <text> ##` | Add description to interface |
| `no shutdown` | Enable interface |
| **Notes** | Network Address \= all 0s in host section Broadcast Address \= all 1s in host section Static routing uses IP address \+ exit interface Netmask refers to destination subnet mask |
| **Routing** |  |
| `show ip route` | Show routing table |
| `ip route <dest> <mask> <next-hop>` | Add static route |
| `ip routing` | Enable Layer 3 routing on switch |
| `ip route 0.0.0.0 0.0.0.0 <next-hop>` | Default route |
| **Notes** | After enabling `ip routing`, route like normal \<next-hop\> is usually ip address  |
| **VLANs** |  |
| `show vlan brief` | Show VLANs |
| `vlan <number>` | Create/configure VLAN |
| `switchport mode access` | creates access port for vlans |
| `switchport access vlan <vlan-number>` | all the ports defined in config will be set to \<vlan-number\> |
| **Trunking** |  |
| `show interface trunk` | Show trunk interfaces |
| `switchport mode trunk` | Configure trunk mode |
| `switchport trunk allowed vlan <list>` | Allow VLANs on trunk |
| `switchport trunk native vlan <vlan>` | configure native VLAN |
| **Router-on-a-Stick (ROAS)** |  |
| `interface g0/0.<subint>` | Enter subinterface mode |
| `encapsulation dot1q <vlan>` | Set VLAN encapsulation |
| `ip address <ip> <mask>` | Assign IP to subinterface |
| `encapsulation dot1q <vlan> native` | configure the native VLAN on a **ROUTER** subinterface |
| **Inter-VLAN Routing (SVI)** |  |
| `interface vlan <number>` | Create VLAN SVI(Switch Virtual Interface) |
| `ip address <ip> <mask>` | Assign IP |
| `no shutdown` | Enable SVI |
| **Routed Ports** |  |
| `no switchport` | Convert interface to routed port (for multilayer switches) |
| **Show Commands** |  |
| `show interfaces status` | Show interface status |
| `show ip interface brief` | Quick IP/interface summary |
| `show interface trunk` | Show trunks |
| `show vlan` | Show VLANs |
| `show int <interface>` | Show specific interface |
| `show ip route` | Show routing table |
| `show spanning-tree` | show spanning tree info |
| `show spanning-tree vlan <vlan #>` | Spanning tree info for a certain vlan |
| **Defaults** |  |
| `default interface <int>` | Reset interface to default |
| **DTP AND VTP** |  |
| `switchport nonegotiate` | disable DTP negotiation on an interface |
| `vtp mode transparent` | safest setting for labs |
| **STP** |  |
| `spanning-tree portfast` | enable portfast ( no need to learn and listen to forward state) |
| `spanning-tree portfast default` | enables portfast only on access ports |
| `spanning-tree bpduguard enable` | enable bpdu guard |
| `spanning-tree bpduguard enable default` | enable globally |
| `spanning-tree mode ?` | show spanning tree modes |
| `spanning-tree vlan <vlan-number> root primary` | sets as root bridge |
| `spanning-tree vlan <vlan-number> root secondary` | sets as secondary root bridge |
| `spanning-tree vlan ?` | configure STP port settings |
| **RSTP** |  |
| `spanning-tree link–type ?` | manually configure RSTP link type |
| **ETHERCHANNEL** |  |
| `port-channel load-balance <method>` | sets the load balancing algorithm |
| `show etherchannel load-balance` | Displays the current load-balancing method used by the switch. |
| `show etherchannel summary` | Shows a summary of EtherChannels |
| `channel-group <number> mode ?` | configures an interface to be part of an etherchannel |
| `show etherchannel port-channel` | displays information about the virtual port-channel interfaces on the switch |
| `channel-protocol <protocol>` | forces interface to use specific protocol |
| **FLOATING STATIC ROUTES** |  |
| `ip route <DEST-NETWORK> <MASK> <NEXT-HOP> or <EXIT-INT> <AD>` | DEST-NETWORK \= Target network (e.g., 192.168.4.0). MASK \= Subnet mask (e.g., 255.255.255.0). NEXT-HOP \= IP of the next router. \[AD\] \= Optional Administrative Distance. Default \= 1 (static). configures a floating static route by making the route higher AD than the dynamic

---
 This cheatsheet is part of my CCNA prep — I’ll be adding more CLI references as I progress more in prep for the CCNA.
---