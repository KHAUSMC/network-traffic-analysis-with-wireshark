# Exploring Data with Wireshark

## Task 1: Exploring a Packet Capture File

In this task, I will open a network packet capture file containing data from a system that made web requests to a site. I'll use Wireshark to analyze how the data is presented.

### Steps:
1. I will open the packet capture file by double-clicking the sample file on the Windows desktop, which will launch Wireshark.

   ![Wireshark Packet Capture](https://i.imgur.com/sSkYCcl.png)


2. **Understanding the Sample File**:
   - The file icon features a shark's fin over three rows of binary digits.
   - It has a `.pcap` extension, though Windows might hide it by default.

   **Note**: If a software update dialog appears, I will click **Skip this version**.

3. **Exploring Wireshark's Interface**:
   - I will maximize the Wireshark window by double-clicking the title bar next to `sample.pcap`.
   - A list of network packets will be displayed, making it necessary to apply filters later.

   ![Wireshark Packet Capture](https://i.imgur.com/cTdEikj.png)


4. **Key Packet Properties**:
   - **No.**: The packet's index number.
   - **Time**: When the packet was captured.
   - **Source**: The originating IP address.
   - **Destination**: The receiving IP address.
   - **Protocol**: The type of protocol used.
   - **Length**: The packet size.
   - **Info**: Packet details, interpreted by Wireshark.

   ![Packet Properties](images/packet_properties.png)

5. **Interpreting Packet Colors**:
   - Light blue packets represent **DNS traffic**.
   - Green packets contain a mix of **TCP and HTTP traffic**.


6. **Finding an Echo (Ping) Request**:
   - I will scroll through the packet list until I see an entry where the **Info** column starts with _"Echo (ping) request"_.
  
     ![Wireshark Packet Capture](https://i.imgur.com/EPXsies.png)


---

## Task 2: Applying a Basic Wireshark Filter and Inspecting a Packet

Now, I will filter network traffic to inspect a specific IP address.

### Steps:
1. I will enter the following filter in the **Apply a display filter...** text box:
   ```plaintext
   ip.addr == 142.250.1.139
   ```
   - Then, I'll press **ENTER** or click the **Apply display filter** button.

   ![Wireshark Packet Capture](https://i.imgur.com/AAMNGhG.png)


2. **Observing Filtered Traffic**:
   - The list will now show only packets where the source or destination IP matches `142.250.1.139`.
   - Two primary colors remain:
     - **Light pink**: ICMP packets.
     - **Light green**: TCP and HTTP packets.


3. **Inspecting a TCP Packet**:
   - I will double-click the first packet where **Protocol** is **TCP**, opening the **Packet Details Pane**.

    ![Wireshark Packet Capture](https://i.imgur.com/9nK4R9f.png)

4. **Exploring the Packet Structure**:
   - **Frame**: Provides general details (frame length, arrival time).
   - **Ethernet II**: Displays **source and destination MAC addresses**.
   - **IPv4**: Shows **source/destination IP addresses** and protocol type.
   - **TCP**: Displays **ports, sequence numbers, and flags**.

5. **Clearing the Filter**:
   - I will click the **X (Clear display filter)** button in the Wireshark filter bar.

---

## Task 3: Using Filters to Select Specific Packets

I will now apply filters to isolate packets based on IP and MAC addresses.

### Steps:
1. **Filtering by Source IP**:
   ```plaintext
   ip.src == 142.250.1.139
   ```

2. **Filtering by Destination IP**:
   ```plaintext
   ip.dst == 142.250.1.139
   ```

3. **Filtering by MAC Address**:
   ```plaintext
   eth.addr == 42:01:ac:15:e0:02
   ```
   - This isolates packets linked to a specific MAC address.

---

## Task 4: Using Filters to Explore DNS Packets

Now, I will filter for DNS traffic.

### Steps:
1. **Applying a DNS Filter**:
   ```plaintext
   udp.port == 53
   ```
   - This lists all **DNS query and response traffic**.

   ![DNS Filter Applied](https://i.imgur.com/AZ2ZC66.png)

2. **Inspecting a DNS Query**:
   - I will double-click the **first packet** and expand the **Domain Name System (query)** subtree.
   - The **website queried** should appear as `opensource.google.com`.

   ![DNS Query](https://i.imgur.com/yLE9bWX.png)

3. **Inspecting a DNS Response**:
   - I will double-click the **fourth packet** and expand **Answers** under **Domain Name System (query)**.
  
   ![DNS Query](https://i.imgur.com/3s1Q2li.png)  

---

## Conclusion

By completing these tasks, I gained hands-on experience with **Wireshark**, learning to:
- Open and navigate packet capture files.
- Apply **filters** to locate specific network traffic.
- Inspect packet details at various **protocol layers**.
- Analyze **DNS, TCP, and ICMP packets**.

These techniques are essential for **network analysis, troubleshooting, and cybersecurity investigations**.

---

**More screenshots and visual examples will be added soon!**
