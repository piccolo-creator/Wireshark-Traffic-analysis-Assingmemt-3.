# Examining the TCP Three-Way Handshake

This guide shows you how to locate and analyze the TCP three-way handshake packets (SYN, SYN-ACK, and ACK) to understand how a reliable connection is established.

## What You Will Do
* Locate the initial connection request (SYN).
* Find the server's acknowledgment reply (SYN-ACK).
* Identify the final handshake validation (ACK).
* Inspect the TCP flag signals for each stage.

## Steps

1. **Locate and Analyze the SYN Packet**
   * Scan your filtered traffic for a row with `[SYN]` in the Info column.
   * Click on the row to view its details. (In the first picture, Packet **18** is selected).
   * Expand the **Flags** section in the details pane to verify the SYN flag bit is active.

2. **Locate and Analyze the SYN-ACK Packet**
   * Look directly below for the response from the server labeled `[SYN, ACK]`.
   * Click on the row to view its details. (In the second picture, Packet **19** is selected).
   * Expand the **Flags** section to verify both the Acknowledgment and Syn flags are active.

3. **Locate and Analyze the Final ACK Packet**
   * Find the final response from your machine labeled `[ACK]`.
   * Click on the row to view its details. (In the third picture, Packet **20** is selected).
   * Expand the **Flags** section to verify only the Acknowledgment flag is active.

## What the Images Show

By moving through your screenshot proofs step-by-step, you documented the structural flags of the connection:

* **Stage 1 (Packet 18 - SYN):** Sent from your local host `10.0.2.15` to the server `63.176.8.218`. The bottom pane shows `Flags: 0x002 (SYN)` is active with a Sequence Number of `0`.
* **Stage 2 (Packet 19 - SYN-ACK):** Sent from the server `63.176.8.218` back to your host `10.0.2.15`. The bottom pane shows `Flags: 0x012 (SYN, ACK)` is active, acknowledging your request.
* **Stage 3 (Packet 20 - ACK):** Sent from your local host `10.0.2.15` back to the server `63.176.8.218`. The bottom pane shows `Flags: 0x010 (ACK)` is active, completing the handshake.
* **Bonus Data (Packet 21 - Client Hello):** The fourth image shows the very next packet after the handshake where the secure `TLSv1.3` data transmission begins for `umar-faruq-tdh.netlify.app`.

