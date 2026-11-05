# HTTPS Traffic Analysis & Man-in-the-Middle (MITM) Proxying

**Domain:** Network Security

## Overview & Methodology
Compares direct end-to-end TLS handshakes against TLS interception through an HTTPS inspection proxy using **Wireshark** and **Burp Suite**:
1. **Direct TLS Session Inspection:** Captured baseline HTTPS traffic to verify that application payloads remain encrypted when traversing the network without a proxy.
2. **HTTPS Proxy Interception & Certificate Chain Analysis:** Routed browser traffic through an interception proxy to observe split-TLS termination, certificate authority (CA) warning behavior when the proxy CA is untrusted, and decrypted HTTP payload visibility once the proxy certificate is trusted.

## Technical Evidence & Screenshots

![image1](assets/image1.png)

![image10](assets/image10.png)

![image11](assets/image11.png)

![image12](assets/image12.png)

![image13](assets/image13.png)

![image14](assets/image14.png)

![image15](assets/image15.png)

![image16](assets/image16.png)

![image2](assets/image2.png)

![image3](assets/image3.png)

![image4](assets/image4.png)

![image5](assets/image5.png)

![image6](assets/image6.png)

![image7](assets/image7.png)

![image8](assets/image8.png)

![image9](assets/image9.png)
