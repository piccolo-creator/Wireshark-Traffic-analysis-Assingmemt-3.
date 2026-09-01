# Filtering TLS Traffic in Wireshark

This guide demonstrates how to isolate and display Transport Layer Security (TLS) traffic from your overall network capture.

## What You Will Do
* Apply a security protocol filter to hide unrelated network traffic.
* Isolate secure cryptographic handshakes and encrypted application data streams.

## Steps

1. **Locate the Filter Bar**
   * Find the text box at the very top of the Wireshark window (directly underneath the main tool menu).

2. **Apply the TLS Filter**
   * Type lowercase `tls` into the green filter bar.
   * Press **Enter** on your keyboard to update the display pane.

## What the Image Shows

Your packet log has updated dynamically to isolate your secure cryptographic sessions:

* **Protocol Column:** The display lists filtered `TLSv1.2` and `TLSv1.3` packets exclusively.
* **Traffic Summary:** The capture isolates secure tracking logs passing between your local host address (`10.0.2.15`) and various remote secure web services (such as `34.107.243.93` and `151.101.1.91`).
* **Connection Highlights:** 
  * **Packet 29:** Outbound initialization tagged as `Client Hello (SNI=ads.mozilla.org)`.
  * **Packet 36:** Inbound server answer tagged as `Server Hello, Change Cipher Spec, Application Data, Application Data`.
* **Active Status:** The bottom status bar shows that **40 packets** matching the TLS profile are being displayed out of the 135 total packets recorded.
