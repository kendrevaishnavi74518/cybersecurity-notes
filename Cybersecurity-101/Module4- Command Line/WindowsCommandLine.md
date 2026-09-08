# Windows Command Prompt – Introduction

## GUI vs CLI
A **GUI (Graphical User Interface)** is generally easier for beginners because it is intuitive and allows users to perform tasks through menus and buttons.

A **CLI (Command-Line Interface)** has a learning curve, but once mastered, it can be **faster and more efficient** for performing repetitive and administrative tasks.

### Advantages of CLI
* **Lower Resource Usage** – Uses fewer system resources than graphics-intensive GUIs, making it suitable for older hardware and resource-limited systems.
* **Automation** – Commands can be combined into **batch files or scripts** to automate repetitive tasks.
* **Remote Management** – CLI tools such as **SSH** allow administrators to manage remote systems efficiently, even over slow networks.

# Basic System Information
## Windows Path
* Windows uses the **Path environment variable** to determine where it searches for executable commands.
* Use the following command to view environment variables, including the Path:
```cmd
set
```
* The line beginning with **`Path=`** shows the directories where Windows searches for commands.

## `ver`
* The `ver` command displays the **Windows operating system version**.
```cmd
ver
```
Example:
```text
Microsoft Windows [Version 10.0.17763.1821]
```

## `systeminfo`
* The `systeminfo` command displays detailed information about the computer system.
* It can provide information about:
  * Operating system
  * System configuration
  * Processor
  * Memory
  * Host name
  * OS version and build
```cmd
systeminfo
```

## Paging Long Output
If a command produces a large amount of output, use the **pipe (`|`)** with `more` to display it page by page.
```cmd
driverquery | more
```
* Press **Spacebar** to view the next page.
* Press **Ctrl + C** to exit.

## Useful Commands
| Command               | Purpose                                          |
| --------------------- | ------------------------------------------------ |
| `set`                 | Displays environment variables, including `Path` |
| `ver`                 | Displays Windows version                         |
| `systeminfo`          | Displays detailed system information             |
| `help`                | Provides help for commands                       |
| `cls`                 | Clears the Command Prompt screen                 |
| `driverquery`         | Displays installed device drivers                |
| `driverquery \| more` | Displays driver information page by page         |

# Network Configuration & Troubleshooting
Command Prompt provides several commands for checking **network configuration, connectivity, DNS, routes, and active connections**.

## 1. `ipconfig`
* Displays the computer's basic **network configuration**.
* Common information includes:
  * IPv4 address
  * IPv6 address
  * Subnet mask
  * Default gateway
```cmd
ipconfig
```

### `ipconfig /all`
* Displays **detailed network configuration**, including:
  * MAC/Physical address
  * DHCP status
  * DHCP server
  * DNS servers
  * IP addresses
  * Default gateway
  * DHCP lease information
```cmd
ipconfig /all
```

## 2. `ping`
* Tests whether a target system can be **reached over the network**.
* Sends **ICMP packets** to the target and waits for replies.
* The output provides packet loss and round-trip time.

```cmd
ping example.com
```
Useful information:
* Packets sent/received
* Packet loss
* Minimum, maximum, and average response time

## 3. `tracert`

* `tracert` stands for **Trace Route**.
* Displays the network path taken to reach a destination.
* Shows the routers/hops traversed between the source and target.
* A `*` indicates that a response was not received from that hop.
```cmd
tracert example.com
```

## 4. `nslookup`
* Used to perform **DNS lookups**.
* Resolves a hostname/domain name to its IP address.
* By default, it uses the system's configured DNS server.
* A specific DNS server can also be specified.

```cmd
nslookup example.com
```
Using a specific DNS server:
```cmd
nslookup example.com 1.1.1.1
```

## 5. `netstat`
* Displays **current network connections and listening ports**.
* A basic command shows established connections.
```cmd
netstat
```

### Useful Options
| Option | Purpose                                                |
| ------ | ------------------------------------------------------ |
| `-a`   | Displays all connections and listening ports           |
| `-b`   | Shows the program associated with each connection/port |
| `-o`   | Displays the Process ID (PID)                          |
| `-n`   | Displays addresses and ports numerically               |
| `-h`   | Displays the help page                                 |

### Combined Command
```cmd
netstat -abon
```
This combines:
* `-a` → All connections and listening ports
* `-b` → Associated executable/program
* `-o` → Process ID
* `-n` → Numerical addresses and ports
For example, `sshd.exe` may be shown listening on **port 22**, with its associated **PID**.






