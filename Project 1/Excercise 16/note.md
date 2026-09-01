# Starting an TLS Network Capture in Wireshark

This guide covers launching a fresh network packet capture session from the Wireshark splash screen to record secure HTTPS traffic and TLS handshakes.

 What You Will Do
* Choose your active network interface.
* Start a live capture session to record encrypted web traffic.
* Navigate to an HTTPS website to generate TLS handshakes.
* Stop the capture once the web page finishes loading.

 Steps

1. **Select the Network Interface**
   * Look under the **Capture** section in the lower half of the screen.
   * Double-click **eth0** from the interface list (it is highlighted in blue as the active interface connected to the internet).

2. **Start the Capture**
   * Click the blue **Shark Fin icon** in the top-left toolbar to begin recording live traffic.

3. **Generate HTTPS Traffic**
   * Open your web browser and go to a secure website (for example, `https://example.com`).
   * Wait for the web page to load completely so the full cryptographic handshake is recorded.

4. **Stop the Recording**
   * Click the **Red Square icon** next to the shark fin in the top toolbar to halt the live capture.

