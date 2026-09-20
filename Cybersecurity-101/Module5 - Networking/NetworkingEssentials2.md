### ICMP (Internet Control Message Protocol)
* **ICMP** is mainly used for:
  * **Network diagnostics**
  * **Error reporting**
* Two important commands that use ICMP are:
  * `ping`
  * `traceroute` / `tracert`

### 1. Ping
* `ping` tests **connectivity** to a target system.
* It also measures **Round-Trip Time (RTT)** — the time taken for a request to reach the target and its reply to return.

#### How Ping Works
1. Sends an **ICMP Echo Request** — **Type 8**.
2. Target responds with an **ICMP Echo Reply** — **Type 0**.
3. RTT is calculated from the request/reply.
```text
ICMP Echo Request (Type 8)
          ↓
       Target
          ↓
ICMP Echo Reply (Type 0)
```

#### Example
```bash
ping 192.168.11.1 -c 4
```
* `-c 4` → sends **4 packets** and then stops.

Output provides:
* Packets transmitted/received
* **Packet loss**
* Minimum RTT
* Average RTT
* Maximum RTT
* Standard deviation (`mdev`)

**Important:** No reply does not always mean the target is offline. A **firewall** may block ICMP packets.

### 2. Traceroute
* `traceroute` discovers the **route/path** from your system to a target.
* On Windows, it is called **`tracert`**.
* It uses **TTL (Time-to-Live)** to identify routers along the path.

#### How TTL Works
* Each IP packet has a **TTL** value.
* Every router that forwards the packet **decreases TTL by 1**.
* When TTL reaches **0**, the router:

  1. Drops the packet.
  2. Sends an **ICMP Time Exceeded** message — **Type 11**.

This allows `traceroute` to identify each router/hop.

### Traceroute Output
Example:
```text
1  192.168.66.1
2  192.168.11.1
3  100.104.0.1
4  10.149.1.45
5  * * *
...
16  93.184.215.14
```
* Each numbered line represents a **hop/router**.
* `* * *` means the router did not respond with the expected ICMP message.
* Some routers may reveal **private or public IP addresses**.
* Public IPs may sometimes reveal information about the router's location/domain.
* ICMP responses may also be blocked by firewalls.

### Routing Protocols
Routing protocols allow routers to **exchange routing information** and determine suitable paths for forwarding data.

| Protocol  | Full Form                                  | Key Points                                                                                                                                                           |
| --------- | ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **OSPF**  | Open Shortest Path First                   | Routers share **network topology/link-state information** and calculate efficient paths. Each router can build a map of the network.                                 |
| **EIGRP** | Enhanced Interior Gateway Routing Protocol | **Cisco proprietary** protocol. Routers exchange reachable networks and route costs such as **bandwidth and delay** to choose efficient paths.                       |
| **BGP**   | Border Gateway Protocol                    | **Primary routing protocol of the Internet**. Exchanges routing information between different networks/organizations and establishes paths across multiple networks. |
| **RIP**   | Routing Information Protocol               | Simple protocol often used in **small networks**. Uses **hop count**; routers prefer routes requiring fewer hops.                                                    |

### NAT (Network Address Translation)
* **NAT** helps deal with the limited number of available **IPv4 addresses**.
* It allows **multiple devices with private IP addresses** to access the Internet using **one public IP address**.

### Why NAT Is Needed
IPv4 supports approximately **4 billion addresses**, but the number of Internet-connected devices has grown significantly.

Without NAT:
* Each device would require a public IP address.

With NAT:
* Many devices can **share a single public IP address**.

### How NAT Works
A **NAT-enabled router** maintains a translation table that maps:
**Internal IP + Port → External/Public IP + Port**

Example:
| Internal Network      | External/Internet |
| --------------------- | ----------------- |
| `192.168.0.129:15401` | `212.3.4.5:19273` |

* Laptop uses private IP `192.168.0.129` and TCP source port `15401`.
* NAT router translates it to public IP `212.3.4.5` and port `19273`.
* The web server therefore sees the connection as coming from the **public IP and translated port**.

### NAT Translation
```text
Laptop
192.168.0.129:15401
        ↓
   NAT Router
        ↓
212.3.4.5:19273
        ↓
   Web Server
```
The router performs this translation **seamlessly** and keeps track of ongoing connections using its NAT table.

