 Wireshark DNS Traffic Filter Guide

This guide details how to filter and isolate Domain Name System (DNS) traffic within a network packet capture using Wireshark.

Objective
Isolate and display only the DNS query and response packets from the overall network traffic capture to analyze domain resolution activity.

Step-by-Step Instructions

1. **Open the Capture File**
   * Load your packet capture file (`.pcap` or `.pcapng`) into Wireshark.
2. **Locate the Filter Bar**
   * Find the green/white display filter text box directly below the main toolbar.
3. **Apply the DNS Filter**
   * Type lowercase `dns` into the filter bar.
   * Press **Enter** or click the blue arrow icon on the right side of the bar.
4. **Analyze the Output**
   * View the packet list pane to inspect the filtered records.

## Expected Output Analysis

Once the filter is applied, the main display pane will dynamically update to show only DNS-specific data:

* **Protocol Column:** Every visible packet will be marked explicitly as **DNS**.
* **Info Column Details:** 
  * **Standard query:** Outgoing requests mapping domain names to IP addresses (e.g., `A www.google.com`).
  * **Standard query response:** Incoming answers containing the requested IP mappings or authoritative server details.
* **Packet Details Pane:** Expanding the **Domain Name System (query)** section reveals deeper structural information including transaction IDs, flags, queries, and answers.

