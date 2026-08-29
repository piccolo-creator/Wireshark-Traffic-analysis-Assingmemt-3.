# Reviewing DNS Resolution Parameters in Wireshark

This guide summarizes how to inspect the communication path and specific record properties of an active DNS response packet.

## What You Did
* Found the source and destination IP addresses responsible for the DNS traffic.
* Looked inside the query structure to determine the record type being requested by the client application.

## Steps

1. **Identify the Communication Path**
   * Check the **Source** and **Destination** address fields on the highlighted packet row to map the traffic flow.

2. **Verify the Query Type**
   * Navigate to the Packet Details pane at the bottom.
   * Expand the **Queries** drop-down menu to view the structural parameters of the request.

## What Your Lab Proof Shows

By looking at the highlighted packet (**Packet 203**), you verified the following details:

* **Source Address:** `192.168.3.1` (The network DNS gateway responding to your client).
* **Destination Address:** `192.168.3.25` (Your local machine receiving the answer).
* **Target Domain:** `umar-faruq-tdh.netlify.app`.
* **Record Type:** `HTTPS (65)` (This indicates the system requested specialized HTTPS service endpoints rather than a basic IPv4 tracking record).
* **Transaction Status:** The Flags dropdown displays a `Reply code: No error (0)`, proving the request finished successfully without failing.

