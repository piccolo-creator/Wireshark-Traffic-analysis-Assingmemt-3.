# Examining TLS Certificate Information

This guide shows you how to locate a TLS Certificate packet in Wireshark and inspect its identity details, security signatures, and validity timeframes.

## What You Will Do
* Locate an inbound packet containing the server's cryptographic identity document.
* Open the security details to check who issued the certificate and how long it is valid.

## Steps

1. **Find the Certificate Packet**
   * Keep your packet stream filtered with the `tls` keyword.
   * Scan the **Info** column for an incoming server response that contains `Certificate`.
   * Click on that row to select it. (In the picture, Packet **244** is highlighted in blue).

2. **Open the Certificate Details**
   * Move down to the Packet Details pane (middle section of the screen).
   * Expand **Transport Layer Security** > **Handshake Protocol: Certificate**.
   * Open the nested **Certificate** entries down to the **signedCertificate** block to read the plain-text credentials.

## What the Image Shows

By opening the certificate metadata fields for **Packet 244**, you verified these identity details:

* **The Target Domain (Subject):** `commonName=://mozilla.com` (This verifies the exact site identity the certificate is protecting).
* **The Authority (Issuer):** `rdnSequence` matching Mozilla services infrastructure.
* **The Algorithm Type:** `signature (sha256WithRSAEncryption)` (Shows the secure hashing and encryption methods used to seal this document).
* **Validity Period:** 
  * **notBefore:** `2026-08-10 12:30:09 (UTC)` (The exact date and time the certificate became active).
  * **notAfter:** `2026-11-08 12:30:08 (UTC)` (The expiration date when the certificate will cease to be trusted).


