## Intro
- `ping` won’t give any information if the target system’s firewall blocks ICMP traffic. Moreover, `arp-scan` only works if your device is connected to the same network, i.e., over Ethernet or WiFi. 
- Nmap is an open-source network scanner that was first published in 1997.

### Host Discovery
* Nmap uses multiple ways to specify its targets:
   1. IP range using - : If you want to scan all the IP addresses from 192.168.0.1 to 192.168.0.10, you can write 192.168.0.1-10
   2. IP subnet using /: If you want to scan a subnet, you can express it as 192.168.0.1/24, and this would be equivalent to 192.168.0.0-255
   3. Hostname: You can also specify your target by hostname, for example, example.thm
- To discover the online hosts on a network. Nmap offers the `-sn` option, i.e., ping scan.

#### Scanning Local Network

- The term “local” to refer to the network we are directly connected to, such as an Ethernet or WiFi network.
- **COMMAND: nmap -sn <target_network_ip>**
-  Because we are scanning the local network, where we are connected via Ethernet or WiFi, we can look up the MAC addresses of the devices.
- When scanning a directly connected network, Nmap starts by sending ARP requests. When a device responds to 
- `-sn` aims to discover live hosts without attempting to discover the services running on them. This scan might be helpful if you want to discover the devices on a network without causing much noise.

#### Scanning Remote Network
- All our traffic to the target systems must go through one or more routers. Unlike scanning a local network, we cannot send an ARP request to the target.
- **COMMAND: nmap -sn <target_network_ip>**
- Nmap offers a list scan with the option `-sL`. This scan only lists the targets to scan without actually scanning them. 
- For example, nmap -sL 192.168.0.1/24 will list the 256 targets that will be scanned. This option helps confirm the targets before running the actual scan.

### Port Scanning
By design, TCP has 65,535 ports, and the same applies to UDP.
### 1. Scanning TCP Ports
- The easiest and most basic way to know whether a TCP port is open would be to attempt to telnet to the port.
- In other words, you attempt to complete the TCP three-way handshake with every target port; however, only open TCP ports would respond appropriately and allow a TCP connection to be established. 
#### Connect Scan
- The connect scan can be triggered using `-sT`. It tries to complete the TCP three-way handshake with every target TCP port. If the TCP port turns out to be open and Nmap connects successfully, Nmap will tear down the established connection.
#### SYN Scan (Stealth)
- Unlike the connect scan, which tries to connect to the target TCP port, i.e., complete a three-way handshake, the SYN scan only executes the first step: it sends a TCP SYN packet. 
- Consequently, the TCP three-way handshake is never completed. The advantage is that this is expected to lead to fewer logs as the connection is never established, and hence, it is considered a relatively stealthy scan. `-sS` flag is used here.

### 2. Scanning UDP Ports
- Although most services use TCP for communication, many use UDP. Examples include DNS, DHCP, NTP (Network Time Protocol), SNMP (Simple Network Management Protocol), and VoIP (Voice over IP). 
-  UDP does not require establishing a connection and tearing it down afterwards. Furthermore, it is very suitable for real-time communication, such as live broadcasts. 
- Nmap offers the option -sU to scan for UDP services. Because UDP is simpler than TCP, we expect the traffic to di

#### Limiting the Target Ports
Nmap scans the most common 1,000 ports by default. However, this might not be what you are looking for. 
   1. -F is for Fast mode, which scans the 100 most common ports (instead of the default 1000).
   2. -p[range] allows you to specify a range of ports to scan. For example, -p10-1024 scans from port 10 to port 1024. Note that -p- scans all the ports and is equivalent to -p1-65535 and is the best option if you want to be as thorough as possible.
- Tip: The most common services use a port number between 1 and 1024 for either UDP or TCP. These ports are also known as well-known ports. Use -p1-1023 to scan for the well-known ports.

To check active web server from browser: http://MACHINE_IP:PORT_NO.

### OS Detection
- We can nable OS detection by adding the -O option. As the name implies, the OS detection option triggers Nmap to rely on various indicators to make an educated guess about the target OS.
- COMMAND: nmap -sS -O <target_machine_ip>

### Service & Version Detection
- To know what services are listening on them. `-sV` enables version detection. This is very convenient for gathering more information about your target with fewer keystrokes.
 - -A = -O + -sV, i.e, it enables OS detection, version scanning & traceroute.

 ### Forcing the Scan
 - When we run our port scan, such as using -sS, there is a possibility that the target host does not reply during the host discovery phase (e.g. a host doesn’t reply to ICMP requests).
 -  Consequently, Nmap will mark this host as down and won’t launch a port scan against it. 
 - We can ask Nmap to treat all hosts as online and port scan every host, including those that didn’t respond during the host discovery phase. This choice can be triggered by adding the `-Pn` option.(Scans hosts that appear to be down)

### Timing
- Nmap gives you six timing templates, and the names say it all: paranoid (0), sneaky (1), polite (2), normal (3), aggressive (4), and insane (5). You can pick the timing template by its name or number.
- The number of parallel probes can be controlled with --min-parallelism <numprobes> and --max-parallelism <numprobes>. 
- These options can be used to set a minimum and maximum on the number of TCP and UDP port probes active simultaneously for a host group. 
- By default, nmap will automatically control the number of parallel probes. 
- If the network is performing poorly, i.e., dropping packets, the number of parallel probes might fall to one; furthermore, if the network performs flawlessly, the number of parallel probes can reach several hundred.
<br>

A similar helpful option is the --min-rate <number> and --max-rate <number>. As the names indicate, they can control the minimum and maximum rates at which nmap sends packets. 
The rate is provided as the number of packets per second. The specified rate applies to the whole scan and not to a single host.
- --host-timeout <time>. This option specifies the maximum time you are willing to wait, and it is suitable for slow hosts or hosts with slow network connections.
---
#### Verbosity & Debugging
- To see the additional information while a scan takes place we add `-v` to enable verbose output.
- We can increase the verbosity level by adding another “v” such as `-vv` or even `-vvvv`. 
- You can also specify the verbosity level directly, for example, -v2 and -v4. You can even increase the verbosity level by pressing “v” after the scan already started.
- `-d` is for debugging-level output.  Similarly, you can increase the debugging level by adding one or more “d” or by specifying the debugging level directly. The maximum level is -d9.

#### Saving Scan Report
In many cases, we would need to save the scan results. Nmap gives us various formats. The three most useful are normal (human-friendly) output, XML output, and grepable output, in reference to the grep command. You can select the scan report format as follows:
-oN <filename> - Normal output
-oX <filename> - XML output
-oG <filename> - grep-able output (useful for grep and awk)
-oA <basename> - Output in all major formats

##### Conclusion
- It is best to run Nmap with sudo privileges so that we can make use of all its features.
-  You get a minimal portion of Nmap’s power when running it as a local user. For instance, Nmap would automatically use SYN scan (-sS) if you are running it with sudo privileges and will default to connect scan (-sT) if run as a local user. The reason is that crafting certain packets, such as sending a TCP SYN packet, requires root privileges.
