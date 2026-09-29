# Wireshark

## 1. Use Cases
**Wireshark** is a powerful **network traffic analyser** used for:
   * **Network troubleshooting**
   * Detect network load failures, congestion, and other problems.
   * **Security analysis**
   * Detect rogue hosts, abnormal port usage, and suspicious traffic.
   * **Protocol analysis**
   * Investigate protocol details, response codes, and payload data.

### Important Note
* Wireshark is **not an IDS**.
* It allows analysts to **inspect and investigate packets**.
* It **does not modify packets**; it only reads them.
* Detecting anomalies depends heavily on the **analyst's knowledge and investigation skills**.

## 2. Wireshark GUI
Main sections of the Wireshark interface:

| Section                         | Purpose                                                              |
| ------------------------------- | -------------------------------------------------------------------- |
| **Toolbar**                     | Packet sniffing, filtering, sorting, summarising, exporting, merging |
| **Display Filter Bar**          | Query and filter packets                                             |
| **Recent Files**                | Recently opened capture files                                        |
| **Capture Filter & Interfaces** | Capture filters and available network interfaces                     |
| **Status Bar**                  | Tool status, profile, and packet information                         |

**Network interface:** Connection point between a computer and a network, e.g. `lo`, `eth0`, `ens33`.

## 3. Loading PCAP Files
Wireshark can load a `.pcap` file using:
* **File menu**
* Drag and drop
* Double-clicking the file

After loading a PCAP, Wireshark provides three main packet-analysis panes:

| Pane                     | Purpose                                                               |
| ------------------------ | --------------------------------------------------------------------- |
| **Packet List Pane**     | Summary of packets: source, destination, protocol, packet information |
| **Packet Details Panel** | Detailed protocol breakdown of selected packet                        |
| **Packet Bytes Pane**    | Hexadecimal and decoded ASCII representation of packet                |

### Packet Investigation
Select a packet from the **Packet List Pane** → its detailed information appears in the other panes.

## 4. Packet Colouring
Wireshark colours packets according to different **conditions and protocols** to make traffic easier to analyse.

### Types of Colouring Rules
1. **Temporary rules**
   * Available only during the current Wireshark session.

2. **Permanent rules**
   * Saved in the preference/profile file.
   * Available in future sessions.

### Useful Menus
* **View → Coloring Rules** → create permanent colouring rules.
* **Colourise Packet List** → enable/disable packet colouring.
* Right-click menu can also be used for colouring/filtering.

**Purpose:** Quickly identify protocols or events of interest and spot anomalies.

## 5. Traffic Sniffing
Wireshark uses buttons to control packet capture:

| Button   | Function                      |
| -------- | ----------------------------- |
| 🔵 Blue  | Start packet capture/sniffing |
| 🔴 Red   | Stop capture                  |
| 🟢 Green | Restart capture               |

The **Status Bar** shows:
* Sniffing interface
* Number of collected packets

## 6. Merge PCAP Files
Wireshark can combine multiple PCAP files into one.

**Steps:**
1. `File → Merge`
2. Select the second PCAP file.
3. Wireshark displays its packet count.
4. Click **Open** to merge.
5. **Save the merged PCAP** before working on it.

## 7. View PCAP File Details
File details are useful when handling multiple PCAP files.

Information includes:
* **File hash**
* **Capture time**
* **Capture file comments**
* **Interface**
* **Statistics**

### Access
`Statistics → Capture File Properties`

Or click the **PCAP icon at the bottom-left**.

# Packet Dissection
## 1. What is Packet Dissection?
**Packet dissection** (also called **protocol dissection**) means:

* Investigating packet details by **decoding protocols and fields**.
* Wireshark supports a large number of protocols for dissection.
* Custom **dissection scripts** can also be written.
* Wireshark uses **OSI layers** to break down packets for analysis.

## 2. Viewing Packet Details
* Select a packet in the **Packet List Pane** to view its details.
* **Double-click** a packet to open details in a new window.
* Packets can contain **5–7 layers** based on the OSI model.
* Clicking a field in the **Packet Details Panel** highlights its corresponding bytes in the **Packet Bytes Pane**.

## 3. Packet Dissection Layers
A sample HTTP packet shows **7 distinct sections**:
| Section                  | OSI Layer | Information                                         |
| ------------------------ | --------: | --------------------------------------------------- |
| **Frame / Packet**       |   Layer 1 | Frame/packet information and Physical-layer details |
| **Source [MAC]**         |   Layer 2 | Source and destination MAC addresses                |
| **Source [IP]**          |   Layer 3 | Source and destination IPv4 addresses               |
| **Protocol**             |   Layer 4 | TCP/UDP details and source/destination ports        |
| **Protocol Errors**      |   Layer 4 | TCP segments that needed reassembly                 |
| **Application Protocol** |   Layer 5 | Protocol details such as HTTP, FTP, SMB             |
| **Application Data**     |   Layer 5 | Application-specific data                           |

