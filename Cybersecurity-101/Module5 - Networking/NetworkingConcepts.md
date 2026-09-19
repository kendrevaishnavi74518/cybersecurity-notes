## OSI Model
* The OSI (Open Systems Interconnection) model is a conceptual model developed by the International Organization for Standardization (ISO) that describes how communications should occur in a computer network.
* The OSI model is composed of seven layers:
   1. Physical Layer
   2. Data Link Layer
   3. Network Layer
   4. Transport Layer
   5. Session Layer
   6. Presentation Layer
   7. Application Layer

# OSI Model

| Layer | Name         | Main Function                                  | Examples                      |
| ----- | ------------ | ---------------------------------------------- | ----------------------------- |
| **7** | Application  | Provides services/interfaces to applications   | HTTP, FTP, DNS, SMTP, IMAP    |
| **6** | Presentation | Data encoding, encryption & compression        | Unicode, MIME, JPEG, PNG      |
| **5** | Session      | Establishes, maintains & synchronises sessions | NFS, RPC                      |
| **4** | Transport    | End-to-end communication & data segmentation   | TCP, UDP                      |
| **3** | Network      | Logical addressing & routing                   | IP, ICMP, IPSec               |
| **2** | Data Link    | Reliable transfer between adjacent nodes       | Ethernet (802.3), Wi-Fi (802.11)               |
| **1** | Physical     | Transmits data through physical media/signals  | Electrical, Optical, Wireless signals |


## TCP/IP Model
* TCP/IP stands for Transmission Control Protocol/Internet Protocol and was developed in the 1970s by the Department of Defense (DoD). One of the strengths of this model is that it allows a network to continue to function as parts of it are out of service, for instance, due to a military attack. This capability is possible in part due to the design of the routing protocols to adapt as the network topology changes.

| TCP/IP Layer    | Corresponding OSI Layers | Main Function                                      | Examples                          |
| --------------- | ------------------------ | -------------------------------------------------- | --------------------------------- |
| **Application** | Layers 5, 6, 7           | Application services, data presentation & sessions | HTTP, HTTPS, FTP, SMTP, IMAP, SSH |
| **Transport**   | Layer 4                  | End-to-end communication                           | TCP, UDP                          |
| **Internet**    | Layer 3                  | Logical addressing & routing                       | IP, ICMP, IPSec                   |
| **Link**        | Layer 2                  | Data transfer over local network                   | Ethernet, Wi-Fi                   |

* The **TCP/IP model traditionally has 4 layers**.
* Some modern textbooks use a **5-layer model** by adding the **Physical Layer**:
  1. Application
  2. Transport
  3. Network
  4. Link
  5. Physical

# IP Addresses 
* An **IP address** uniquely identifies a device (host) on a network.
* **IPv4** is the most commonly used IP version.
* IPv4 is **32 bits**, divided into **4 octets**.
* Each octet is **8 bits** and ranges from **0–255**.
* Maximum possible IPv4 addresses: approximately **2³² (4.3 billion)**.

### Network & Broadcast Address
* **Network address:** identifies the network.
* **Broadcast address:** targets all hosts on the network.
* Example:

  * `192.168.1.0` → Network address
  * `192.168.1.255` → Broadcast address

## Checking IP Configuration
### Windows
```cmd
ipconfig
```

### Linux
```bash
ifconfig
ip address show
# or
ip a s
```

Example:
```text
IP Address  : 192.168.66.89
Subnet Mask : 255.255.255.0
Broadcast   : 192.168.66.255
```

## CIDR / Subnet Mask
* `255.255.255.0` can be written as **`/24`**.
* `/24` means the first **24 bits** identify the network.
* Example: `192.168.66.89/24`

  * Network: `192.168.66.0`
  * Usable host range: `192.168.66.1 – 192.168.66.254`
  * Broadcast: `192.168.66.255`

## Private IP Address Ranges
| Range                           | CIDR         |
| ------------------------------- | ------------ |
| `10.0.0.0 – 10.255.255.255`     | `10/8`       |
| `172.16.0.0 – 172.31.255.255`   | `172.16/12`  |
| `192.168.0.0 – 192.168.255.255` | `192.168/16` |

* **Public IP:** Used for communication over the Internet.
* **Private IP:** Used within private/local networks.
* Private IPs generally require **NAT** through a router to access the Internet.

## Routing
* A **router** forwards data packets between networks.
* Routers operate at **Layer 3 (Network Layer)**.
* A packet may pass through **multiple routers** before reaching its destination.
* Routers inspect the **destination IP address** and choose an appropriate path.


