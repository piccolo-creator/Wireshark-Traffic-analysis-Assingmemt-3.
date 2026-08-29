  Checking a DNS Query in Wireshark

This guide shows you how to pick a DNS request in Wireshark and look inside it to see what website a computer is trying to visit.

   What You Will Do
* Find a DNS request in your list.
* Open up its details to see the website name and query type.

## Steps

1.   Find a DNS Request
   * Type `dns` in the green filter bar at the top and press **Enter**.
   * Look down the **Info** column for a row that says `Standard query`.
   * Click on that row to select it. (In the picture, Packet **202** is selected).

2.   Open the Details
   * Look at the middle box on your screen (the Packet Details pane).
   * Click the small arrow next to **Domain Name System (query)** at the bottom to open it up.

## What the Image Shows

If you look at the selected packet (**Packet 202**), you can see this information:

* Who sent it: The computer at IP address `192.168.3.25`.
* Who received it: The router/DNS server at IP address `192.168.3.1`.
* The Transaction ID: `0x1da2` (this is just an ID number to match this request with its answer later).
* The Website Asked For: `umar-faruq-tdh.netlify.app`.
* The Type: `A` (this means the computer is asking for a standard IPv4 address).
