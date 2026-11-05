# Configuring and Verifying a Site-to-Site IPsec VPN

**Domain:** Network Security  
**Packet Tracer Topology:** [`site_to_site_ipsec_vpn.pka`](./site_to_site_ipsec_vpn.pka)

## Overview & Methodology
Configures and verifies a Cisco IOS Site-to-Site IPsec VPN tunnel across an untrusted WAN backbone:
1. Enables the Cisco IOS `securityk9` technology package.
2. Defines interesting traffic ACLs matching branch-to-HQ LAN subnets.
3. Configures IKE Phase 1 ISAKMP policy (encryption, hash, authentication `pre-share`, DH group, lifetime) and peer pre-shared keys.
4. Configures IKE Phase 2 IPsec transform-set (`esp-aes` / `esp-sha-hmac`), binds the crypto map to the outbound WAN serial interface, and verifies encrypted packet encapsulation via `show crypto ipsec sa`.
