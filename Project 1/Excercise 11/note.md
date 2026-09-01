Starting an HTTP Network Capture in Wireshark

This guide covers launching a fresh network packet capture session from the Wireshark splash screen to record unencrypted HTTP requests and responses.

 What I did
* I Chose an active network interface.
* I Started a live capture session to record web traffic.
* Navigated to an HTTP website to generate unencrypted packet data.
* Then Stopped the capture once the web page finishes loading.

  Steps

1. Selected the Network Interface
   * Looked under the Capture section in the lower half of the screen.
   * Double-click your active interface connected to the internet (such as eth0** or wi-fi).

2. Start the Capture
   * Clicked the blue Shark Fin icon in the top-left toolbar to begin recording live traffic.

3. Generate HTTP Traffic
   * Opened my web browser and went to an unencrypted website.
   * Waited for the web page to load completely.

4. Stop the Recording
   * Clicked the Red Square icon next to the shark fin in the top toolbar to halt the live capture.

 Expected Output Summary
The main window populated with live rows of data tracking your internet traffic, saving a temporary capture stream that explicitly captures the plain-text HTTP handshakes between your host and the web server.

