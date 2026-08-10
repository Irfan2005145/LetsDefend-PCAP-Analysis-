# LetsDefend-PCAP-Analysis-
# PCAP Network Traffic Analysis – LetsDefend

## Overview

This project documents a practical PCAP analysis performed using
Wireshark as part of a LetsDefend cybersecurity challenge.

The investigation focused on analyzing HTTP traffic, identifying
communicating hosts, investigating a file transfer, and identifying
web-server information from the captured network traffic.

## Objective

The objective of this investigation was to analyze the provided
network capture and answer investigation questions by examining
network packets and HTTP communications.

### Key investigation areas

- Source and destination IP identification
- HTTP traffic analysis
- File transfer investigation
- Web server identification
- Upload directory identification
- TCP communication analysis
- Network traffic timing analysis

---

## Tools Used

- Wireshark
- LetsDefend
- Linux

---

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

---

## 1. HTTP Traffic Analysis

The first step was to filter the captured traffic using:

```text
http
