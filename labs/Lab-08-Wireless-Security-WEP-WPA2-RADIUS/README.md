# Wireless Network Security (WEP, WPA2-PSK, and WPA2-Enterprise RADIUS)

**Domain:** Network Security  
**Packet Tracer Topology:** [`wep_wpa2_radius.pka`](./wep_wpa2_radius.pka)

## Overview & Methodology
Evaluates wireless encryption protocols and implements enterprise wireless authentication in Cisco Packet Tracer:
1. **WEP Vulnerability Analysis:** Demonstrates why legacy WEP encryption and static shared hex keys are insecure due to weak RC4 initialization vector (IV) reuse and trivial offline key recovery.
2. **WPA2-PSK vs. 802.1X WPA2-Enterprise (RADIUS):** Configures an enterprise wireless LAN backed by a centralized **RADIUS authentication server** using AES-CCMP encryption, providing per-user credentials, centralized access revocation, and enterprise scalability over shared PSKs.
