Starting a TCP Network Capture in Wireshark

This guide covers launching a new network packet capture session from the Wireshark splash screen to record TCP connections and web traffic.

## What You Will Do
* Choose your active network interface.
* Start a live capture session to record web traffic like TCP connections.
* Stop the capture once the web page finishes loading.

## Steps

1. **Select the Network Interface**
   * Look under the **Capture** section in the lower half of the screen.
   * Double-click **eth0** from the interface list (it is highlighted in blue as the active interface connected to the internet).

2. **Start the Capture**
   * Click the blue **Shark Fin icon** in the top-left toolbar to begin recording live packets.

3. **Generate TCP Traffic**
   * Open your web browser and go to a website (for example, `https://example.com`).
   * Wait for the web page to load completely so all TCP connections are recorded.

4. **Stop the Recording**
   * Click the **Red Square icon** next to the shark fin in the top toolbar to halt the live capture.

