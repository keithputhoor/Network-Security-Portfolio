# Network Security Portfolio

![Subject](https://img.shields.io/badge/Domain-Network_Security-00897b?style=flat-square)
![Cisco IOS](https://img.shields.io/badge/Cisco_IOS-Packet_Tracer-1ba0d7?style=flat-square)
![IPsec VPN](https://img.shields.io/badge/IPsec-Site--to--Site_VPN-2e7d32?style=flat-square)
![Firewall](https://img.shields.io/badge/Firewall-Zone--Based_Policy_ZPF-ef6c00?style=flat-square)
![802.1X](https://img.shields.io/badge/Wireless-WPA2_Enterprise_RADIUS-6a1b9a?style=flat-square)

Enterprise network security architecture, Cisco Packet Tracer (`.pkt` / `.pka`) topologies, firewall/VPN configurations, and practical network defense labs completed for **Network Security**.

---

## Flagship Project: CloudCafe Multi-Site Enterprise Network Security Architecture

📂 **Location:** [`project-cloudcafe-enterprise-network/`](./project-cloudcafe-enterprise-network/)  
📄 **Full Architecture Report:** [`project-cloudcafe-enterprise-network/ARCHITECTURE_REPORT.md`](./project-cloudcafe-enterprise-network/ARCHITECTURE_REPORT.md)  
🖧 **Cisco Packet Tracer Topology:** [`project-cloudcafe-enterprise-network/cloudcafe-enterprise-network.pkt`](./project-cloudcafe-enterprise-network/cloudcafe-enterprise-network.pkt)

```mermaid
flowchart LR
    subgraph HQ["Site-A Primary HQ (Router R1)"]
        VLANs["7 Departmental VLANs<br/>(192.168.10.0/24 - .60.0/24)<br/>Extended ACL 100"] --> R1["HQ Router R1<br/>Zone-Based Policy Firewall (ZPF)"]
        DMZ["DMZ Web & DNS (.70.0/24)<br/>ACL 102 (HTTPS 443 Only)"] --> R1
        WLAN["Staff WLAN (VLAN 200)<br/>WPA2-Enterprise + RADIUS (.200.3)"] --> R1
    end

    subgraph WAN["Untrusted ISP WAN"]
        R1 <==>|"IPsec VPN Tunnel (ESP AES/SHA)<br/>10.1.1.2 <-> 10.2.2.2"| R2["ISP Router R2"]
    end

    subgraph Branch["Site-B Remote Branch (Router R3)"]
        R2 <==> R3["Branch Router R3"]
        R3 --> BranchLAN["Delivery (.100.0/24) &<br/>Customer Care (.110.0/24)"]
        R3 --> GuestWiFi["Isolated Guest Wi-Fi<br/>(WPA2-PSK)"]
    end
```

---

## Network Security — Lab Portfolio

All practical network defense implementations and Packet Tracer topologies are organized under [`labs/`](./labs/):

| Lab | Topic | Key Technologies & Protocols | Directory |
| :--- | :--- | :--- | :--- |
| **Lab 03** | Securing Email Communication & Digital Certificates | OpenSSL X.509 Keypair Generation, Public Key Exchange, S/MIME Encrypted Mail, Packet Tracer Topology | [`labs/Lab-03-Securing-Email-Communication-and-Certificates/`](./labs/Lab-03-Securing-Email-Communication-and-Certificates/) |
| **Lab 04** | HTTP Request Interception & Parameter Tampering | Burp Suite Proxy Interception, Price/PID Parameter Manipulation, Wireshark HTTP PCAP Analysis | [`labs/Lab-04-HTTP-Request-Interception-BurpSuite/`](./labs/Lab-04-HTTP-Request-Interception-BurpSuite/) |
| **Lab 05** | Site-to-Site IPsec VPN Implementation | Cisco IOS `securityk9`, ISAKMP Phase 1 Policy, IPsec ESP Transform Sets, Crypto Map Verification | [`labs/Lab-05-Site-to-Site-IPsec-VPN/`](./labs/Lab-05-Site-to-Site-IPsec-VPN/) |
| **Lab 06** | HTTPS Traffic Analysis & MITM Proxying | TLS Certificate Interception, HTTPS Proxy Inspection vs. Direct TLS Handshakes | [`labs/Lab-06-HTTPS-Traffic-Analysis-and-MITM/`](./labs/Lab-06-HTTPS-Traffic-Analysis-and-MITM/) |
| **Lab 07** | Zone-Based Policy Firewall (ZPF) Configuration | Cisco IOS Security Zones (`IN-ZONE`, `OUT-ZONE`), Class-Maps, Stateful `inspect` Policy-Maps, Zone-Pairs | [`labs/Lab-07-Zone-Based-Policy-Firewall-ZPF/`](./labs/Lab-07-Zone-Based-Policy-Firewall-ZPF/) |
| **Lab 08** | Wireless Security: WEP, WPA2-PSK & WPA2-Enterprise | WEP Weakness Analysis, WPA2-PSK vs. 802.1X WPA2-Enterprise RADIUS Server Authentication | [`labs/Lab-08-Wireless-Security-WEP-WPA2-RADIUS/`](./labs/Lab-08-Wireless-Security-WEP-WPA2-RADIUS/) |
| **Lab 09** | Cisco IOS Intrusion Prevention System (IPS) | IOS IPS Signature Storage, `ip ips sdf`, Inline Packet Drop (`deny-packet-inline`) Verification | [`labs/Lab-09-Cisco-IOS-Intrusion-Prevention-System-IPS/`](./labs/Lab-09-Cisco-IOS-Intrusion-Prevention-System-IPS/) |
