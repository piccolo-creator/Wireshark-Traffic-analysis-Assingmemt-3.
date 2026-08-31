 Examining an HTTP Response

This guide shows you how I pick an HTTP response packet in Wireshark and inspect the server headers, status codes, and type of content sent back to your browser.

 What You Will Do
* Select an inbound web server response from your filtered list.
* Expand the protocol layer to view status codes and content configurations.

 Steps

1. Find the HTTP Response
   * Make sure your traffic display is filtered using the `http` keyword.
   * Look down the Info column for an inbound response row that says `HTTP/1.1 200 OK`.
   * Click on that row to select it. (In the picture, Packet **1830** is selected).

2. Open the Protocol Details
   * Look at the middle box on your screen (the Packet Details pane).
   * Click the small arrow next to Hypertext Transfer Protocol at the bottom to open it up.

 What the Image Shows

If you look at the selected packet (**Packet 1830**), you can read the plain-text server details:

* The Status Code: `Status Code: 200` and `Response Phrase: OK` (This indicates that the server successfully found and delivered the requested web page).
* The Content Type: `Content-Type: text/html\r\n` (This tells the browser that the incoming data payload is a standard HTML text document).
* The Server Software: `Server: cloudflare\r\n` (This shows that the website is hosted behind a Cloudflare server infrastructure).
* Content Encoding: `Content-Encoding: gzip\r\n` (Indicates the website data was compressed with gzip to save bandwidth during transmission).
* Link to Request: `[Request In: 1822]` (Wireshark automatically pairs this response to the original outbound query found in packet 1822).

