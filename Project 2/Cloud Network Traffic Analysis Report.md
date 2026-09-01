☁️ **********Cloud Network Traffic Analysis Report**********

**Author Profile:** Victor  
**Environment Baseline:** eth0 (Ubuntu 22.04 / Linux)  
**Target Domain:** umar-faruq-tdh.netlify.app  
**Local Client Host IP:** 10.0.2.15 / 192.168.3.25  

---

 1. **Executive Summary**
This report documents a hands-on network visibility and deep-packet analysis exercise. Live traffic was captured across local network interfaces to dissect foundational web infrastructure behaviors (DNS, TCP, HTTP, and TLS layers). Low-level packet parameters including hardware MAC addresses, client/server IP mappings, TCP window constraints, and transaction handshake indicators were verified. These on premise baseline visibility elements are mapped explicitly into cloud architecture defense mechanisms, translating protocol forensics directly into enterprise AWS and Azure cloud security controls.

---

 2. **Protocol Analysis & Lab Baseline Finding**

| Layer / Protocol | Key Parameters Observed | Security / Behavioral Significance |
| :--- | :--- | :--- |
| **DNS Layer** *(Domain Resolution)* | • **Target:** umar-faruq-tdh.netlify.app<br>• **Request Types:** A, AAAA, HTTPS (65)<br>• **Trans. ID Match:** 0x1da2 / 0xaf77<br>• **Resolved IPs:** 63.176.8.218, 35.157.26.135 | Validates network exit paths and external domain resolution mapping. Identifies mapping patterns across geometric infrastructures and content delivery distributions. |
| **TCP Layer** *(Transport & Control)* | • **3-Way Handshake:** [SYN] -> [SYN, ACK] -> [ACK]<br>• **Flags:** 0x002 / 0x012 / 0x010<br>• **Connection Port:** Src Port 55488 / Dst Port 443<br>• **Sequence / Ack Tracking:** Rel Seq 1 / Ack 40 | Confirms stateful validation parameters. Establishes stateful tracking baselines necessary to profile anomalous connection bursts or denial-of-service attempts. |
| **HTTP Layer** *(Application Payload)* | • **Request Method:** GET /success.txt?ipv4<br>• **Headers:** Host: ://firefox.com<br>• **Response Phrase:** 200 OK<br>• **Cleartext Payload Expose:** 'success' | Highlights unencrypted layer risks. Demonstrates how plain-text queries permit middle-box credential extraction and data modifications. |
| **TLS Layer** *(Cryptographic Layer)* | • **Handshake Phases:** Client Hello / Server Hello<br>• **Suite:** TLS_AES_128_GCM_SHA256 (0x1301)<br>• **Verification Target:** commonName=*.mozilla.com<br>• **Encryption State:** Change Cipher Spec | Confirms complete data encryption. Obfuscates application layer vectors while providing strong authentication through chain-of-trust i

3. **Translation into Cloud Native Security Controls**

Low-level protocol characteristics captured during testing directly map to high-level cloud visibility frameworks. Below is the blueprint converting packet metrics into cloud platform architectures:

 A. Amazon Web Services (AWS) Architecture Translation
*   **AWS VPC Flow Logs:** The observed layer-3 routing fields (Client Source IP `10.0.2.15`, Remote Destination IP `63.176.8.218`, Ports `55488 -> 443`, and Protocol `6` for TCP) align perfectly with standard VPC flow record layouts. This parameter symmetry permits cloud automation rules to profile baseline host performance without deploying OS agents.
*   **AWS Security Groups:** Based on the TCP and TLS session handshakes targeting port 443, a least-privilege egress Security Group template must restrict outbound routing strictly to outbound TCP port 443, eliminating risky generic outbound structures (`0.0.0.0/0` traffic parameters).
*   **Route 53 Resolver DNS Logs:** Capturing structural DNS queries (like type A requests matching transaction `0xaf77`) inside cloud instances maps natively to Route 53 Query Logging, exposing unauthorized resource exfiltration behaviors.

 B. Microsoft Azure Architecture Translation
*   *Azure NSG Flow Logs:* State parameters extracted from the three-way handshake matching flag bits `0x010 (ACK)` map natively to Azure Network Security Group Flow Logging tracking layers. These logs document traffic decisions (Allow/Deny) alongside data tracking sizes.
*   *Azure Application Gateway & WAF:* The cleartext payload extraction test (reconstructing the `://firefox.com` URI and verifying standard text responses) proves where deep-packet inspection defenses must occur. In Azure, these plain-text strings are monitored via Web Application Firewalls (WAF) to block malicious string injections before routing requests downstream.

---

4. *Incident Response & Monitoring Recommendations*

1.  *Deploy Cloud Network Detection & Response (NDR):* Implement out-of-band packet mirroring (such as AWS Traffic Mirroring or Azure Virtual Network TAP) to stream live payload infrastructure directly to centralized Security Operations Center (SOC) analytical layers without hindering production pipeline compute velocities.
2.  *Implement TLS Decryption Profiles:* Since application content after packet 923 becomes fully unreadable (Encrypted Application Data), establish dedicated decryption endpoints on cloud load balancers. This configuration exposes potential malicious control signals hiding inside standard encrypted traffic profiles.
3.  *Enforce Continuous Behavioral Baselining:* Integrate AWS CloudWatch or Azure Monitor metric patterns to automatically generate high-priority alerting signals if anomalous DNS query volumes or unauthorized internal port communication spikes are observed across cloud instance endpoints.
