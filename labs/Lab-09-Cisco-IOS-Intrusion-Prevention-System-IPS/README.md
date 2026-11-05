# Configuring Cisco IOS Intrusion Prevention System (IPS)

**Domain:** Network Security  
**Packet Tracer Topology:** [`cisco_ios_ips.pka`](./cisco_ios_ips.pka)

## Overview & Methodology
Configures inline signature-based intrusion prevention on a Cisco IOS perimeter router:
1. **IOS IPS Rule & Signature Storage:** Configured the router's flash signature storage location (`ip ips config location`), created the IPS rule (`ip ips name iosips`), and enabled syslog alerting (`ip ips notify log`).
2. **Inline Packet Drop Enforcement:** Unretired the ICMP Echo Request signature (`2004:0`) and modified its `event-action` to `deny-packet-inline` (`produce-alert`), applying the rule outbound on `FastEthernet0/0` to block unauthorized inbound ping sweeps while allowing legitimate outbound replies.
