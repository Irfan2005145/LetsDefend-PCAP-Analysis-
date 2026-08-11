# PCAP Network Traffic Analysis – LetsDefend

## Overview

This project documents a practical PCAP analysis performed using
Wireshark as part of a LetsDefend cybersecurity challenge.

The investigation focused on analyzing HTTP traffic, identifying
communicating hosts, investigating a file transfer, and identifying
web-server information from the captured network traffic.

--------------------------------------------------------------------------------------------------------------------------

## Objective

The objective of this investigation was to analyze the provided
network capture and answer investigation questions by examining
network packets and HTTP communications.

--------------------------------------------------------------------------------------------------------------------------

### Key investigation areas

- Source and destination IP identification
- HTTP traffic analysis
- File transfer investigation
- Web server identification
- Upload directory identification
- TCP communication analysis
- Network traffic timing analysis

--------------------------------------------------------------------------------------------------------------------------

## Tools Used

- Wireshark
- LetsDefend
- Linux

--------------------------------------------------------------------------------------------------------------------------

## Investigation Methodology

The investigation was performed using the following process:

1. Loaded the PCAP file into Wireshark.
2. Reviewed the captured network traffic.
3. Filtered HTTP traffic.
4. Identified relevant source and destination IP addresses.
5. Investigated HTTP requests and responses.
6. Examined the file transfer activity.
7. Investigated the web server information.
8. Identified the upload directory.
9. Examined TCP communication and transfer timing.
10. Documented the findings.

--------------------------------------------------------------------------------------------------------------------------

1. Identify the sender and receiver

The investigation required identifying the sender and receiver
associated with the relevant communication.

The identified endpoints were:

Sender:
192.168.235.137

Receiver:
192.168.235.131

The source and destination fields in Wireshark were used to determine
the direction of communication.

--------------------------------------------------------------------------------------------------------------------------

2. HTTP Stream Analysis

Screenshot: 02-http-stream.png

Description

The second screenshot shows the relevant communication after using
Wireshark's Follow HTTP Stream functionality.

Following the HTTP stream allowed the complete client-server
communication to be examined rather than analyzing individual packets
separately.

The HTTP response contains important server information:

HTTP/1.1 200 OK
Server: Apache/2.4.54 (Win64) OpenSSL/1.1.1p PHP/8.0.25
X-Powered-By: PHP/8.0.25

The stream also contains the following message:

file uploaded at uploads/file

This provided direct evidence for several investigation findings.

Important findings from the stream

Web server:

Apache

Uploaded file:

file

Upload directory:

uploads

The stream analysis therefore confirmed that a file was uploaded to
the web server and revealed the location where the file was stored.

--------------------------------------------------------------------------------------------------------------------------

3. TCP Conversation Analysis

Screenshot: 03-tcp-conversations.png

Description

The third screenshot shows Wireshark's Conversations window with
the TCP conversation list.

The Conversations feature provides an overview of communication
between network endpoints.

The table displays information including:

Address A
Port A
Address B
Port B
Number of packets
Number of bytes
Packet direction

For example, the capture contains communication between:

192.168.235.131
        ↕
192.168.235.137

The screenshot also shows other connections involving external
addresses over TCP port 443.

This view was useful for understanding the overall communication
pattern in the PCAP and identifying hosts that generated significant
network activity.

----------------------------------------------------THANK-YOU-------------------------------------------------------------
