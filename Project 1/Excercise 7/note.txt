Filtering TCP Traffic in Wireshark

This guide demonstrates how to isolate and display Transmission Control Protocol (TCP) traffic from your overall network capture.

## What You Will Do
* Apply a protocol filter to hide unrelated traffic.
* Isolate TCP connections, handshakes, and application data streams.

## Steps

1. **Locate the Filter Bar**
   * Find the text box at the very top of the Wireshark window (directly underneath the main tool menu).

2. **Apply the TCP Filter**
   * Type lowercase `tcp` into the green filter bar.
   * Press **Enter** on your keyboard to update the display pane.

## What the Image Shows

Your packet log has updated dynamically to isolate your active connections:

* **Protocol Column:** The display lists filtered `TCP` packets along with secure socket layers labeled as `TLSv1.2`.
* **Traffic Summary:** The capture isolates data streams passing between your local host address (`192.168.3.25`) and various remote web server locations on the internet (such as `104.20.23.154` and `151.101.189.91`).
* **Active Status:** The bottom status bar shows that **3,005 packets** matching the TCP profile are being displayed out of the 6,712 total packets recorded.
