# Examining a TLS Server Hello Packet

This guide shows you how to select a TLS Server Hello packet in Wireshark and inspect the final connection settings chosen by the web server.

## What You Will Do
* Locate the server's handshake response packet.
* Open the secure protocol configurations to see the agreed-upon security parameters.

## Steps

1. **Find the Server Hello Packet**
   * Keep your packet stream filtered with the `tls` keyword.
   * Look down the **Info** column for an incoming packet from the server that contains `Server Hello`.
   * Click on that row to select it. (In the picture, Packet **36** is highlighted in blue).

2. **Open the Response Details**
   * Move down to the Packet Details pane (middle section of the screen).
   * Click the small arrow next to **Transport Layer Security** to expand it.
   * Expand the nested **Handshake Protocol: Server Hello** block.

## What the Image Shows

By opening the layers of your selected row (**Packet 36**), you verified the server's chosen cryptographic settings:

* **The Server Response:** `Handshake Protocol: Server Hello (2)` (The remote web server accepts the connection request and establishes the rules).
* **The Final Version:** `Version: TLS 1.2 (0x0303)` (The system selected TLS 1.2 as the encryption layer framework).
* **The Selected Cipher Suite:** `Cipher Suite: TLS_AES_128_GCM_SHA256 (0x1301)` (Out of all options sent by your computer, the server picked this specific, secure formula to protect all data transferring next).
* **Supported Extensions:** Under the extensions dropdown, it tracks `Extension: supported_versions` showing that it explicitly locks down the connection rules to **TLS 1.3** specifications for the operational payload.

