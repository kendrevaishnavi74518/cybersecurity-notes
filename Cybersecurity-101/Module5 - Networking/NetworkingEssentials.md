### DHCP (Dynamic Host Configuration Protocol)
DHCP automatically configures a device when it connects to a network, such as Wi-Fi.

### Required Network Configuration
A device needs:
* **IP address + subnet mask**
* **Router/Gateway**
* **DNS server**

Manual configuration is useful for servers because they generally stay on the same network. DHCP is especially useful for mobile devices.

### Advantages of DHCP
* Automatically configures network settings.
* Reduces manual configuration.
* Helps prevent **IP address conflicts** when two devices receive the same IP.

### DHCP Basics
* **Layer:** Application layer
* **Transport:** UDP
* **DHCP Server:** UDP **67**
* **DHCP Client:** UDP **68**
* Smartphones and laptops normally use DHCP by default.

### DORA Process
DHCP uses four steps, remembered as **DORA**:
| Step               | Message      | Description                              |
| ------------------ | ------------ | ---------------------------------------- |
| **1. Discover**    | DHCPDISCOVER | Client broadcasts to find a DHCP server. |
| **2. Offer**       | DHCPOFFER    | Server offers an available IP address.   |
| **3. Request**     | DHCPREQUEST  | Client requests/accepts the offered IP.  |
| **4. Acknowledge** | DHCPACK      | Server confirms the IP assignment.       |

### DHCP Packet Example
```text
0.0.0.0 → 255.255.255.255   DHCP Discover
192.168.66.1 → 192.168.66.133 DHCP Offer
0.0.0.0 → 255.255.255.255   DHCP Request
192.168.66.1 → 192.168.66.133 DHCP ACK
```
In this example, the client receives **`192.168.66.133`**.

### Why `0.0.0.0` and Broadcast Are Used
Initially, the client has:
* No IP configuration.
* Only a **MAC address**.

Therefore, during **Discover** and **Request**:

* Source IP: `0.0.0.0`
* Destination IP: `255.255.255.255`
* Destination MAC: `ff:ff:ff:ff:ff:ff`

The DHCP server then provides the client with the proposed IP and network configuration.

### What DHCP Provides
At the end of the DHCP process, the device receives:
* **Leased IP address** → identifies the device on the network.
* **Gateway** → routes traffic outside the local network.
* **DNS server** → resolves domain names.

### ARP (Address Resolution Protocol)
* **ARP** is used to find the **MAC address** of a device when its **IP address** is known.
* It is needed when two devices communicate on the **same Ethernet or WiFi network**.
* Common data link technologies:
  * **Ethernet — IEEE 802.3**
  * **WiFi — IEEE 802.11**

### Why ARP is Needed
A host may know the destination's **IP address**, but to create the Layer 2 frame it also needs the destination's **MAC address**.

**IP address (Layer 3) → ARP → MAC address (Layer 2)**

### MAC Address
* MAC address is a **48-bit** address.
* Usually represented in hexadecimal.

Example:
```text
7C:DF:A1:D3:8C:5C
44:DF:65:D8:FE:6C
```

### Ethernet Frame Header
An Ethernet frame carrying an IP packet contains:
| Field           | Purpose                                         |
| --------------- | ----------------------------------------------- |
| Destination MAC | MAC address of receiving device                 |
| Source MAC      | MAC address of sending device                   |
| Type            | Identifies the encapsulated protocol, e.g. IPv4 |

### ARP Request and Reply
Example:
* Host `192.168.66.89` wants to communicate with `192.168.66.1`.
* It does not know the target's MAC address.
* It broadcasts an **ARP Request**.
* The device with `192.168.66.1` responds with an **ARP Reply** containing its MAC address.

**ARP Request:**
```text
Who has 192.168.66.1?
Tell 192.168.66.89
```
**ARP Reply:**
```text
192.168.66.1 is at 44:df:65:d8:fe:6c
```

### ARP Broadcast
ARP Request is sent to:
```text
ff:ff:ff:ff:ff:ff
```
This is the **broadcast MAC address**, so all devices on the local network receive the request.

The target device then sends the ARP Reply directly back to the requester.

### Important: ARP Encapsulation
ARP is **not encapsulated inside UDP or IP**.
It is encapsulated **directly within an Ethernet frame**.
```text
Ethernet Frame
└── ARP Request / Reply
```

### ARP Layer
* ARP is often considered **Layer 2** because it deals with MAC addresses.
* Some consider it related to **Layer 3** because it supports IP communication.
* The most important concept:

> **ARP translates Layer 3 IP addressing into Layer 2 MAC addressing.**



