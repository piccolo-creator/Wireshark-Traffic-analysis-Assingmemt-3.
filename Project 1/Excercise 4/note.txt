# Checking a DNS Response in Wireshark

This guide shows you how to pick a DNS response packet in Wireshark and check its details to find the response code and answer data.

## What You Will Do
* Locate the matching DNS response packet.
* Open its details to inspect the server's reply flags and transaction codes.

## Steps

1. **Find the DNS Response**
   * Make sure your traffic is filtered by typing `dns` at the top and pressing **Enter**.
   * Look down the **Info** column for the row that contains `Standard query response` and matches your query.
   * Click on the row to highlight it. (In the picture, Packet **255** is selected).

2. **Open the Response Details**
   * Look at the middle box on your screen (the Packet Details pane).
   * Expand the **Domain Name System (response)** section by clicking the small arrow next to it.
   * Expand the **Flags** section inside it to see how the server answered.

## What the Image Shows

If you look at the details for the selected packet (**Packet 255**), you can see this information:

* **The Packet Row:** `255 243.345950784 192.168.3.1 192.168.3.25 DNS 118 Standard query response 0xaf77 A umar-faruq-tdh.netlify.app A 63.176.8.218 A 35.157.26.135`
* **Transaction ID:** `0xaf77` (links this answer directly back to the original request).
* **Response Status:** Inside Flags, it shows `Reply code: No error (0)`, which means the domain name was found successfully.
* **Answer Count:** The section shows `Answer RRs: 2`, indicating the server returned two resolved web addresses.

