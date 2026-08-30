# Following a TCP Stream in Wireshark

This guide shows you how to group individual packets together into a single, readable conversation stream to review the entire data exchange between a client and a server.

## What You Will Do
* Reconstruct a full network conversation using the "Follow TCP Stream" feature.
* Analyze the raw, color-coded exchange between your local machine and the web host.

## Steps

1. **Open the TCP Stream**
   * Right-click on any TCP packet in your filtered packet list.
   * Hover over **Follow** and select **TCP Stream** from the pop-up menu.

2. **Examine the Reconstructed Stream**
   * Review the new pop-up window showing the entire conversation.
   * Read the data sequentially to trace how the two systems communicated.

## What the Image Shows

By analyzing the data inside your open TCP stream window, you can verify these details:

* **The Filter Change:** Wireshark automatically changed your display filter bar in the background to `tcp.stream eq 1` to isolate only this specific conversation thread.
* **The Target Domain:** Right at the top of the stream, you can see the plain-text host reference for `umar-faruq-tdh.netlify.app`.
* **Data Flow Highlights (Stream 1):** 
  * The red text blocks show data sent from your client machine (`10.0.2.15`).
  * The blue text blocks show incoming encrypted data payloads returned from the remote web server (`63.176.8.218`).
  * The bottom status bar tracks that this **Entire conversation** contains **3,719 bytes** of total data.

