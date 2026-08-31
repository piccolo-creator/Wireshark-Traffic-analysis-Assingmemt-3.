 Filtering HTTP Traffic in Wireshark

This guide demonstrates how I isolated and display Hypertext Transfer Protocol (HTTP) traffic from your overall network capture.

 What I Did
* Apply a protocol filter to hide unrelated network traffic.
* Isolated plain text web request methods and server status codes.

 Steps

1. Located the Filter Bar
  Find the text box at the very top of the Wireshark window.

2. Apply the HTTP Filter
   * Type lowercase `http` into the green filter bar.
   * Pressed Enter on your keyboard to update the display pane.

 What the Image Shows

Your packet log has updated dynamically to isolate your unencrypted web sessions:

* Protocol Column: The display lists filtered `HTTP` packets exclusively.
* Traffic Summary: The capture isolates two primary transactional logs between the host and the web server:
  * Packet 1822 (Outbound Request): Sent from your local host (`10.0.2.15`) to the server (`172.66.147.243`) stating `GET / HTTP/1.1`.
  * Packet 1830 (Inbound Response): Sent from the server (`172.66.147.243`) back to your host (`10.0.2.15`) stating `HTTP/1.1 200 OK  (text/html)`.
* Active Status: The bottom status bar shows that **2 packets** matching the HTTP profile are being displayed out of the 1,505 total packets recorded.

