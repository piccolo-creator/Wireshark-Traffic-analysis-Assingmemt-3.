Analyzing an Individual TCP Packet

This guide shows you how to choose a single TCP packet from your filtered capture list and extract its network routing addresses, connection ports, and tracking sequence numbers.

## What You Will Do
* Pick a specific TCP packet row from your filtered stream.
* Map out the source and destination IP addresses and ports.
* Read the sequence parameters and transmission flags inside the detail panel.

## Steps

1. **Select a Target TCP Packet**
   * Make sure your traffic display is filtered using the `tcp` keyword.
   * Click on any individual TCP row to populate its technical properties. (In your picture, Packet **37** is highlighted in blue).

2. **Isolate Routing Information**
   * Look at the **Source** and **Destination** headers on the highlighted packet row to see how the traffic flows.

3. **Inspect the TCP Protocol Header**
   * Move down to the Packet Details pane and select the **Transmission Control Protocol** section.
   * Review the source port, destination port, sequence numbers, and acknowledgment fields.

## What the Image Shows

By inspecting your selected row (**Packet 37**), you verified these technical parameters:

* **Network Addresses:** The packet is sent from a remote web server at Source IP `151.101.189.91` back to your local client machine at Destination IP `192.168.3.25`.
* **Connection Ports:** The communication originates from standard web service port **Source Port: 443** (HTTPS) and targets your local application endpoint at **Destination Port: 55488**.
* **Sequence Metrics:** 
  * **Sequence Number:** `1` (The current position in the data stream relative to the start).
  * **Acknowledgment Number:** `40` (The next byte position this server expects to receive back from your machine).
* **Control Signaling:** The Flags parameter reads `0x010 (ACK)`, verifying this packet acts as a standard acknowledgment update holding a small window sizing index of `271`.

