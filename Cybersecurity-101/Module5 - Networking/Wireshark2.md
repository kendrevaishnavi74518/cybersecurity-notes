# Wireshark 
## 1. Packet Numbers
* Wireshark assigns a **unique number** to every captured packet.
* Helps:
  * Count packets.
  * Locate specific packets.
  * Return to a specific point during investigation.
  * Track events in large captures.

## 2. Go to Packet
The **Go** menu and toolbar can be used to:

* Navigate directly to a specific packet number.
* Move between packets.
* Track packets **within a frame/conversation**.
* Find the next packet belonging to a particular part of a conversation.

## 3. Find Packets
Use:
**`Edit → Find Packet`**
Wireshark can search packet **content** to locate events of interest, such as intrusion patterns or failure traces.

### Search Input Types
1. **Display filter**
2. **Hex**
3. **String**
4. **Regex**

* **String** and **Regex** are commonly used.
* Searches are **case-insensitive by default**.
* Case sensitivity can be enabled.

### Search Fields
Search can be performed in:

* **Packet List**
* **Packet Details**
* **Packet Bytes**

⚠️ **Important:** Search the pane where the required information actually exists.

## 4. Mark Packets
Marking helps analysts identify packets for further investigation.

### Uses
* Point to an event of interest.
* Identify packets for later analysis.
* Help select packets for export.

### How
* Use **Edit** menu or **Right-click → Mark/Unmark**.

### Important
* Marked packets appear **black**, regardless of their original colour.
* Marks are **session-specific** and are lost after closing the capture file.

## 5. Packet Comments
Packet comments allow analysts to attach notes to specific packets.

### Uses
* Explain suspicious/important packets.
* Record investigation findings.
* Help other analysts understand the event.

**Difference from marking:**
| Feature     | Mark                       | Comment                  |
| ----------- | -------------------------- | ------------------------ |
| Purpose     | Identify packet            | Add explanatory notes    |
| Persistence | Lost after closing capture | Stored in capture file   |
| Appearance  | Packet becomes black       | Adds comment information |

## 6. Export Packets
Large PCAP files may contain thousands of packets.

Wireshark allows analysts to **export selected packets** so they can:
* Focus on suspicious traffic.
* Remove unnecessary information from further analysis.
* Share only relevant packets during an investigation.

Access through the **File** menu.

## 7. Export Objects (Files)
Wireshark can extract **files transferred over the network**.

Useful for security analysts investigating shared/transferred files.

Supported protocols mentioned:

* **DICOM**
* **HTTP**
* **IMF**
* **SMB**
* **TFTP**

## 8. Time Display Format
By default, Wireshark displays packet time as:
**Seconds Since Beginning of Capture**

You can change the format using:
**`View → Time Display Format`**

The source notes that **UTC Time Display Format** is commonly useful for better investigation.

## 9. Expert Info
**Expert Info** detects specific protocol states that may indicate:

* Possible anomalies
* Errors
* Network problems

⚠️ Expert Info provides **suggestions**, not guaranteed conclusions. It can produce **false positives and false negatives**.

### Severity Levels

| Severity  | Colour | Meaning                                      |
| --------- | ------ | -------------------------------------------- |
| **Chat**  | Blue   | Normal/usual workflow information            |
| **Note**  | Cyan   | Notable events, e.g. application error codes |
| **Warn**  | Yellow | Warnings, unusual errors/problem statements  |
| **Error** | Red    | Problems such as malformed packets           |

### Common Information Groups
| Group          | Meaning                    |
| -------------- | -------------------------- |
| **Checksum**   | Checksum errors            |
| **Deprecated** | Deprecated protocol usage  |
| **Comment**    | Packet comment detection   |
| **Malformed**  | Malformed packet detection |

### Viewing Expert Info
* **Lower-left section of Status Bar**
* `Analyse → Expert Information`

It can show:

* Packet number
* Summary
* Protocol/group
* Total occurrences

## 1. Packet Filtering
Wireshark provides a powerful **filter engine** to reduce traffic and focus on events of interest.

### Two Types of Filters
| Filter             | Purpose                                       |
| ------------------ | --------------------------------------------- |
| **Capture Filter** | Captures **only** packets matching the filter |
| **Display Filter** | Displays **only** packets matching the filter |

> **Golden rule:** *“If you can click on it, you can filter and copy it.”*

Filtering can be done using:
* Filter queries
* Right-click menu / GUI options

## 2. Apply as Filter
Used to filter packets based on a **specific field/value**.

### How
* Select a field/value.
* Right-click → **Apply as Filter**
* Or: `Analyse → Apply as Filter`

The **Status Bar** shows:
* Total packets
* Displayed packets

## 3. Conversation Filter
Used when you want to investigate **all packets related to a conversation**.
Focuses on linked:
* IP addresses
* Port numbers
* Related packets

### How
* Right-click → **Conversation Filter**
* Or: `Analyse → Conversation Filter`

**Difference:**
* **Apply as Filter** → filters based on one specific value.
* **Conversation Filter** → filters the related conversation/traffic.

## 4. Colourise Conversation
Similar to Conversation Filter, but it **does not apply a display filter**.

Instead, it:
* Highlights related packets.
* Keeps the number of displayed packets unchanged.
* Works with Wireshark's colouring rules.

### How
`View → Colourise Conversation`

To undo:
`View → Colourise Conversation → Reset Colourisation`

## 5. Prepare as Filter
Used to **create a display filter without immediately applying it**.

### How
* Right-click → **Prepare as Filter**
* Wireshark places the query in the filter bar.
* Press **Enter** to execute it.
* Can combine conditions using **and/or** options.

### Difference
| Option                | Action                                     |
| --------------------- | ------------------------------------------ |
| **Apply as Filter**   | Creates **and applies** filter             |
| **Prepare as Filter** | Creates filter but **waits for execution** |

## 6. Apply as Column
Adds a selected packet field as a **column** in the Packet List Pane.

### How
* Right-click → **Apply as Column**
* Or: `Analyse → Apply as Column`

### Purpose
Allows analysts to compare a specific field/value **across many packets**.

Columns can be enabled/disabled from the top of the Packet List Pane.

## 7. Follow Stream
Wireshark normally displays traffic in individual packet portions.

**Follow Stream** reconstructs the traffic into a **continuous application-level view**.

### Uses
* Reconstruct application-level communication.
* Understand the event/conversation.
* View unencrypted data such as:

  * Usernames
  * Passwords
  * Transferred data

### How
Right-click → **Follow TCP/UDP/HTTP Stream**
Or:
`Analyse → Follow TCP/UDP/HTTP Stream`

In the stream window:
* **Blue** → server traffic
* **Red** → client traffic

Following a stream automatically creates and applies a filter for that stream.

### Remove Filter
Click the **X** on the right side of the Display Filter Bar to return to all packets.

# 8. Simple Display Filter Queries
Use the **Display Filter Bar** to quickly narrow down large captures.

### Filter by Protocol Name
Simply enter the protocol name:
```text
http
```

Other examples:
```text
arp
dhcp
ftp
smtp
pop
imap
```

### Filter by Port Number
Use:
```text
tcp.port == <port>
udp.port == <port>
```
Example — HTTP:
```text
tcp.port == 80
```

### Filter by IP Address
Use:
```text
ip.addr == <IP address>
```

Example:
```text
ip.addr == 192.168.1.2
```
