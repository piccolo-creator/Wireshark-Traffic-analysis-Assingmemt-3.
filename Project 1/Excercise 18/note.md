# Examining a TLS Client Hello Packet

This guide shows you how to select a TLS Client Hello packet in Wireshark and inspect its handshake properties, version settings, and supported cipher suites.

## What You Will Do
* Locate an outbound cryptographic handshake initialization packet.
* Expand the secure socket layer to view supported encryption algorithms.

## Steps

1. **Find the Client Hello Packet**
   * Ensure your packet stream is filtered using the `tls` keyword.
   * Look down the **Info** column for an outbound packet that contains `Client Hello`.
   * Click on that row to select it. (In the picture, Packet **29** is selected).

2. **Open the Protocol Details**
   * Move down to the Packet Details pane (middle section of the screen).
   * Click the small arrow next to **Transport Layer Security** to expand it.
   * Expand the nested **Handshake Protocol: Client Hello** block to view detailed cryptographic properties.

## What the Image Shows

By expanding the layers of your selected row (**Packet 29**), you verified these secure connection parameters:

* **The Request Event:** `Handshake Protocol: Client Hello (1)` (The browser is starting a secure handshake negotiation).
* **The Record Version:** `Version: TLS 1.0 (0x0301)` / `Version: TLS 1.2 (0x0303)` (The initial wrapper protocols used for maximum backward compatibility with older servers).
* **Cryptographic Options:** `Cipher Suites (17 suites)` (The browser is presenting a list of 17 distinct encryption algorithms it is capable of running).
* **Target Website Name (SNI Extension):** Inside the extensions dropdown, it lists `server_name (len=20) name=ads.mozilla.org` (This reveals the exact secure domain destination requested by the browser).

