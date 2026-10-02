## Tcpdump
The Tcpdump tool and its libpcap library are written in C and C++ and were released for Unix-like systems in the late 1980s or early 1990s. Consequently, they are very stable and offer optimal speed. The libpcap library is the foundation for various other networking tools today. Moreover, it was ported to MS Windows as winpcap.

## 1. Basic Usage
Running `tcpdump` without arguments only verifies that it is installed.

In real scenarios, specify:
* **What interface** to listen on
* **Where** to save packets
* **How** to display packets

## 2. Specify Network Interface
Use:
```bash
tcpdump -i INTERFACE
```
* `-i eth0` → capture on a specific interface.
* `-i any` → capture on **all available interfaces**.

Find available interfaces with:
```bash
ip address show
```
or:
```bash
ip a s
```

Example interfaces:
```text
lo
ens5
```

## 3. Save Captured Packets
Use:
```bash
tcpdump -w FILE
```

Example:
```bash
tcpdump -i wlo1 -w data.pcap
```

* Saves captured packets to a `.pcap` file.
* Packets can later be analysed using **Wireshark** or another tool.
* With `-w`, packets are **not displayed scrolling on screen**.
* Capture continues until interrupted with **Ctrl+C** unless a count is specified.

## 4. Read Packets from a File
Use:
```bash
tcpdump -r FILE
```

Example:
```bash
tcpdump -r data.pcap
```

Useful for:
* Learning protocol behaviour.
* Analysing previously captured traffic.
* Investigating packet captures containing network attacks.
* Applying filters to captured traffic.

## 5. Limit Number of Packets
Use:
```bash
tcpdump -c COUNT
```

Example:
```bash
tcpdump -i eth0 -c 50
```

Captures exactly **50 packets**, then stops.

Without `-c`, capture continues until interrupted with **Ctrl+C**.

## 6. Disable Address/Port Resolution
By default, tcpdump may resolve IP addresses to domain names.

### `-n`
```bash
tcpdump -n
```
* Prevents **IP address/DNS resolution**.

### `-nn`
```bash
tcpdump -nn
```
* Prevents **IP address resolution**
* Prevents **port/protocol number resolution**

Example:
```bash
tcpdump -i ens5 -c 5 -n
```
Output may show:
```text
10.10.117.2.22 > 10.11.81.126.53378
```

instead of resolving addresses/ports to names.

## 7. Verbose Output
Use:
```bash
tcpdump -v
```
Provides additional packet details.

More verbosity:
```bash
-vv
-vvv
```
* `-v` → verbose
* `-vv` → more verbose
* `-vvv` → even more verbose
Verbose output can include details such as **TTL, identification, total length, and IP options**.

##  Quick Revision
**Tcpdump workflow:**
```text
Interface → Capture → Save/Read → Filter/Display
```
Most important commands:
```bash
tcpdump -i eth0       # specific interface
tcpdump -i any        # all interfaces
tcpdump -w data.pcap  # save capture
tcpdump -r data.pcap  # read capture
tcpdump -c 50         # capture 50 packets
tcpdump -n            # no IP/DNS resolution
tcpdump -nn           # no IP + port resolution
tcpdump -v            # verbose
```
**Easy recall:**
`-i` = Interface | `-w` = Write | `-r` = Read | `-c` = Count | `-n` = No resolution | `-v` = Verbose

# Tcpdump — Packet Filtering
## 1. Why Filtering?
Network interfaces see a huge number of packets, so capturing everything is often impractical.

**Filtering** allows you to focus only on the traffic relevant to your investigation.

> **Goal:** Capture only what you are interested in inspecting.

## 2. Filtering by Host
### Any Traffic to/from a Host
```bash
tcpdump host IP
tcpdump host HOSTNAME
```

Example:
```bash
sudo tcpdump host example.com -w http.pcap
```
Captures packets **sent to or received from** `example.com`.

> Packet capture generally requires **root privileges or `sudo`**.

### Source Host
```bash
tcpdump src host IP
tcpdump src host HOSTNAME
```

Captures packets **from** the specified source.

### Destination Host
```bash
tcpdump dst host IP
tcpdump dst host HOSTNAME
```

Captures packets **to** the specified destination.

## 3. Filtering by Port
### Any Traffic on a Port
```bash
tcpdump port PORT_NUMBER
```

Example — DNS:

```bash
sudo tcpdump -i ens5 port 53 -n
```

Captures traffic using **port 53**.

### Source Port
```bash
tcpdump src port PORT_NUMBER
```

### Destination Port
```bash
tcpdump dst port PORT_NUMBER
```
Example:
```bash
tcpdump src port 53
tcpdump dst port 443
```

## 4. Filtering by Protocol
Specify the protocol directly:
```bash
tcpdump PROTOCOL
```

Examples:
```bash
tcpdump ip
tcpdump ip6
tcpdump tcp
tcpdump udp
tcpdump icmp
```

Example:
```bash
sudo tcpdump -i ens5 icmp -n
```
This captures **ICMP traffic**.

ICMP output may show:
* **Echo request/reply** → possible `ping`
* **Time exceeded** → may be related to `traceroute`

# 5. Logical Operators
Tcpdump supports three important logical operators.

### `and`
Both conditions must be true.

```bash
tcpdump host 1.1.1.1 and tcp
```
→ TCP traffic involving `1.1.1.1`.

### `or`
Either condition can be true.

```bash
tcpdump udp or icmp
```
→ UDP **or** ICMP traffic.

### `not`
Condition must **not** be true.
```bash
tcpdump not tcp
```

→ Everything except TCP traffic.

# 6. Important Examples

### SSH traffic

```bash
tcpdump -i any tcp port 22
```

* All interfaces
* TCP
* Port 22
* SSH traffic

### NTP traffic

```bash
tcpdump -i wlo1 udp port 123
```

* Wi-Fi interface
* UDP
* Port 123
* NTP traffic

### HTTPS traffic for a specific host

```bash
tcpdump -i eth0 host example.com and tcp port 443 -w https.pcap
```

Captures TCP port 443 traffic exchanged with `example.com`.

---

# 7. Reading and Filtering a PCAP

Use `-r` to read an existing capture:

```bash
tcpdump -r traffic.pcap
```

Example:

```bash
tcpdump -r traffic.pcap -c 5 -n
```

* Reads `traffic.pcap`
* Displays first **5 packets**
* `-n` prevents IP address resolution

### Filter a PCAP by Source Host
```bash
tcpdump -r traffic.pcap src host 192.168.124.1 -n
```

You can pipe the output to `wc`:
```bash
tcpdump -r traffic.pcap src host 192.168.124.1 -n | wc
```

The source example shows:
```text
910   17415  140616
```
The capture contained **910 matching packets**.

> Reading a PCAP file does **not** require `sudo` because you are not directly capturing network traffic.
