# Network Traffic Analysis with Wireshark

As a security analyst, analyzing network traffic is essential to understand the data transmitted across systems. In this activity, I utilized Wireshark to examine a sample packet capture file and applied filters to efficiently navigate through the packet information.

## Scenario

I investigated traffic to a website by analyzing a network packet capture file containing data related to a user's connection to an internet site. The objectives were to:

- Identify the source and destination IP addresses involved in the web browsing session.
- Examine the protocols used during the connection.
- Analyze data packets to determine the type of information exchanged between systems.

## Task 1: Exploring Data with Wireshark

1. **Opening the Packet Capture File**

   I began by opening the packet capture file (`sample.pcap`) with Wireshark. This file contains data captured from a system that made web requests to a site.




2. **Understanding the Wireshark Interface**

   Upon opening the file, Wireshark displayed a list of network packets. Key columns include:

   - **No.**: Index number of the packet.
   - **Time**: Timestamp of the packet.
   - **Source**: Source IP address.
   - **Destination**: Destination IP address.
   - **Protocol**: Protocol used in the packet.
   - **Length**: Total length of the packet.
   - **Info**: Additional information about the packet's data.

   *[Insert annotated screenshot highlighting these columns]*

3. **Identifying Specific Packets**

   I scrolled through the packet list to locate packets where the 'Info' column starts with 'Echo (ping) request'. These packets use the ICMP protocol.

   *[Insert screenshot of an ICMP Echo request packet]*

## Task 2: Applying Filters and Inspecting Packets

1. **Filtering by IP Address**

   To focus on traffic associated with a specific IP address, I applied the following filter:


