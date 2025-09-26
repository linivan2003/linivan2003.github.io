---
title: "Network Fundamentals Cheatsheet"
layout: single
---

This post is a quick overview of networking fundamentals — the foundation for CCNA studies, my homelab experiments, and also the research work I’m doing at UCLA’s Internet Research Lab. These fundamentals cover how data moves through the network stack, how devices discover each other, and how communication stays reliable and secure. These cheatsheets are based on CS118 at UCLA.

---

## Key Topics Covered
- **Network Performance** — latency, throughput, packet loss, bottlenecks  
- **HTTP & DNS** — basic web communication and name resolution:contentReference[oaicite:0]{index=0}  
- **Transport Layer** — UDP (simple, fast) vs TCP (reliable, congestion control):contentReference[oaicite:1]{index=1}  
- **LANs & Switches** — Ethernet, collision domains, MAC learning, VLANs:contentReference[oaicite:2]{index=2}  
- **Network Layer** — IP addressing, subnets, routing, BGP:contentReference[oaicite:3]{index=3}  
- **Security** — TLS over TCP for encrypted transport:contentReference[oaicite:4]{index=4}  
- **Link Layer** — ARP, framing, error detection:contentReference[oaicite:5]{index=5}  
---

## 📝 Why This Matters
- **CCNA prep** → These are the building blocks of every exam domain.  
- **Homelab** → Routing, switching, VLANs, and TCP/UDP are what you configure day-to-day.  
- **Automation** → Understanding fundamentals makes tools like Ansible or Netmiko meaningful.  
- **Research** → These same layers and protocols are what new models like NDN (Named Data Networking) try to evolve.  

---

Stay tuned — I’ll be posting more **focused cheatsheets** (VLANs, STP, Routing, etc.) and **tiny automation labs** (Python + Netmiko/Ansible) to go deeper on each area.