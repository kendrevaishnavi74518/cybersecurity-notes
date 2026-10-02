# Tcpdump – Advanced Packet Filtering
In real-world network analysis, a capture can contain **thousands or even millions of packets**. Basic filters are useful, but sometimes we need to describe the exact packets we want to investigate.

Tcpdump provides more advanced filtering techniques that allow us to filter packets based on:
* Packet length
* Specific bytes in protocol headers
* Binary operations
* TCP flags

# 1. Filtering by Packet Length
Tcpdump allows packets to be filtered according to their length.

### `greater LENGTH`
Filters packets whose length is **greater than or equal to** the specified length.
```bash
tcpdump greater LENGTH
```

### `less LENGTH`
Filters packets whose length is **less than or equal to** the specified length.
```bash
tcpdump less LENGTH
```

These filters are useful when the size of packets is relevant to the investigation.

# 2. Binary Operations
Before filtering individual bits and header fields, it is important to understand **binary operations**.

A binary operation works with **bits**, which have only two possible values:

```text
0 or 1
```
## AND (`&`)
The AND operation returns `1` **only when both inputs are 1**.
| Input 1 | Input 2 | Input 1 `&` Input 2 |
| ------: | ------: | ------------------: |
|       0 |       0 |                   0 |
|       0 |       1 |                   0 |
|       1 |       0 |                   0 |
|       1 |       1 |                   1 |

AND is useful when we want to check whether a particular bit is set.

## OR (`|`)

The OR operation returns `1` when **at least one of the inputs is 1**.
| Input 1 | Input 2 | Input 1 `|` Input 2 |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

OR is useful when checking whether **one of several bits** is set.

## NOT (`!`)
The NOT operation reverses the input:
* `1` becomes `0`
* `0` becomes `1`

# 3. Filtering Header Bytes
Tcpdump can examine the contents of individual bytes in protocol headers.
This can be used with protocols such as:

* ARP
* Ethernet
* ICMP
* IPv4
* IPv6
* TCP
* UDP

The general syntax provided by `pcap-filter` is:
```text
proto[expr:size]
```
### Meaning of Each Part

| Part    | Meaning                    |
| ------- | -------------------------- |
| `proto` | Protocol being examined    |
| `expr`  | Byte offset                |
| `size`  | Number of bytes to examine |

### `proto`
Specifies the protocol.

Examples:
```text
arp
ether
icmp
ip
ip6
tcp
udp
```

### `expr`
Specifies the **byte offset**.

The first byte has an offset of:
```text
0
```
The next byte is:
```text
1
```
and so on.

### `size`
Specifies how many bytes should be examined.
It can be:
* 1 byte
* 2 bytes
* 4 bytes

The `size` value is **optional** and defaults to **1 byte**.

# 4. Examples of Header Byte Filtering

The following examples come from the `pcap-filter` concept and demonstrate what can be achieved by examining individual bits.

They can look complicated at first, so the important thing is to understand the general idea.

## Example 1: Ethernet Multicast
```bash
ether[0] & 1 != 0
```
This filter:
1. Looks at the **first byte** of the Ethernet header.
2. Uses the binary value `1`:
```text
0000 0001
```
3. Performs a bitwise AND (`&`).
4. Checks whether the result is **not equal to 0**.

The purpose of this filter is to identify packets sent to a **multicast Ethernet address**.

A multicast Ethernet address identifies a group of devices that are intended to receive the same data.

## Example 2: IP Packets with Options
```bash
ip[0] & 0xf != 5
```
Here:

* `ip[0]` → first byte of the IP header.
* `0xf` → hexadecimal `F`, represented as:
```text
0000 1111
```
The filter performs a bitwise AND and checks whether the result is not equal to decimal `5`:
```text
0000 0101
```

The purpose of this filter is to identify **IP packets containing options**.

> These examples demonstrate the power of byte-level filtering. Understanding every detail of these two examples is not required for the TCP flag filtering discussed next.

# 5. Filtering TCP Packets Using TCP Flags
TCP packets contain several **flags** that indicate the state or purpose of the TCP communication.

Tcpdump allows us to examine these flags using:
```text
tcp[tcpflags]
```
The TCP flags covered in this section are:

| Flag       | Meaning           |
| ---------- | ----------------- |
| `tcp-syn`  | SYN — Synchronize |
| `tcp-ack`  | ACK — Acknowledge |
| `tcp-fin`  | FIN — Finish      |
| `tcp-rst`  | RST — Reset       |
| `tcp-push` | PUSH              |

These flags can be used with binary operations to create precise filters.

# 6. TCP Flag Filters
## Only SYN Flag Set
```bash
tcpdump "tcp[tcpflags] == tcp-syn"
```

This captures TCP packets where:
* The **SYN flag is set**
* All other TCP flags are **unset**

In other words, the packet must contain **only the SYN flag** from the flags being considered.

## SYN Flag Is Set
```bash
tcpdump "tcp[tcpflags] & tcp-syn != 0"
```

This uses the **AND (`&`) operation**.

It captures TCP packets where the **SYN flag is set**, even if other TCP flags are also set.

## SYN or ACK Flag Is Set
```bash
tcpdump "tcp[tcpflags] & (tcp-syn|tcp-ack) != 0"
```

This combines:
* OR (`|`) between `tcp-syn` and `tcp-ack`
* AND (`&`) with the TCP flags field

It captures TCP packets where **at least one of the following is set**:
* SYN
* ACK

# 7. Understanding the TCP Flag Filters

The important idea is that TCP flags are individual **bits** within the TCP flags field.

Binary operations allow us to check whether particular bits are set.

### `==`

```bash
tcp[tcpflags] == tcp-syn
```

Checks for an exact flag combination.

### `&`

```bash
tcp[tcpflags] & tcp-syn
```

Checks whether the SYN bit is present.

### `|`

```bash
tcp-syn|tcp-ack
```

Combines the SYN and ACK conditions.

Therefore, by combining `&`, `|`, and comparisons, we can build filters for very specific TCP traffic.

# 8. Important TCP Flag Filters

| Filter                                    | Meaning                                    |
| ----------------------------------------- | ------------------------------------------ |
| `tcp[tcpflags] == tcp-syn`                | Only SYN flag is set                       |
| `tcp[tcpflags] & tcp-syn != 0`            | SYN flag is set, regardless of other flags |
| `tcp[tcpflags] & (tcp-syn\|tcp-ack) != 0` | SYN or ACK flag is set                     |

### Most Important Commands
```bash
tcpdump "tcp[tcpflags] == tcp-syn"
```
**Only SYN packets**
```bash
tcpdump "tcp[tcpflags] & tcp-syn != 0"
```
**Packets with SYN set**
```bash
tcpdump "tcp[tcpflags] & (tcp-syn|tcp-ack) != 0"
```
**Packets with SYN or ACK set**
