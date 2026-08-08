## What is Networking?

- First iteration of Internet was within the ARPANET project in late 1960s.
- 1989 - Internet was invented by **Tim Berners-Lee** as we know it as World Wide Web(WWW).
- Network can be of 2 types: Public & Private.
<br>

- IP Address:  Also known as Internet Protocol address, is used to identify a host on a network.
    - It is a set of numbers divided into 4 octets, value of each octet will summarize to be IP address of the device on a network.
    - It is calculated through a technique known as IP addressing & subnetting.
    - IP address can change from device to device, but the same IP address generally cannot be assigned to two devices on the same network at the same time.
    - IP Addresses follow a set of standards known as protocols. 
    - IP addresses are of 2 types: public & private IP address.
       1. Public address - Used to identify device on the internet. It is given by Internet Service Provider(ISP).
       2. Private address - Used to identify device amongst other devices.
    - IPv4 - USes a numbering system of 2^32 IP addresses(4.29 billion).
    - IPv6 - It is a new iteration of IP addressing, supports up to 2^128 IP address, it is more efficient due to newer methodologies.

## MAC Addresses
- Every device on a network has a Network Interface Card (NIC) that allows it to connect to the network.
- The NIC has a unique MAC(Media Access Control) address assigned by the manufacturer.
- It is a 12-character hexadecimal number split into two's & separated by a colon(:).
- The first 6 characters represent the company that made network interface, the last 6 is a unique number.
- It can be faked or spoofed, in a process called "spoofing". It occurs when a networked device pretends to identify as another using its MAC address.
- When this occurs, it can often break poorly implemented security designs that assume that devices talking on a network are trustworthy. 

## Ping(ICMP)
- Ping uses ICMP(Internet Control Message Protocol) packets, to determine performance of a connection between devices.
- The time taken for ICMP packets travelling between devices is measured by ping, using ICMP's echo packet and then ICMP's echo reply from the target device.
- Syntax: ping ip address or website URL
<br>

## Intro to LAN
- Topology refers to the design of the network.
    1. Star Topology - Here, device are individually connected via central networking device such as switch or hub. It is most commonly used due to its reliablitiy & scalability, even though its cost is expensive.
       - If the centralised hardware that connects devices fails, these devices will no longer be able to send or receive data.
    2. Bus Topology - It relies upon a single connection known as a backbone cable.
       - All data destined for each device travels along the same cable, making it slow & increasing chances of bottleneck.
       - The bottleneck also becomes difficult for troubleshooting as identifying device causing trouble is difficult with data travelling through the same route.
       - It is easy & cost-efficient.
       - There is a single point of failure along the backbone cable. 
       - If this cable were to break, devices can no longer receive or transmit data along the bus.
    3. Ring Topology - Also known as **token topology**.
       - Here, devices form a loop, meaning less caling required & less dependency on dedicated hardware.
       - It works by sending data across the loop until it reaches the destined device.
       - A device will only send received data from another device in this topology if it does not have any to send itself.
       - If the device happens to have data to send, it will send its own data first before sending data from another device.
       - Easy to troubleshoot,as data travels only in one direction.
       - It isn't an efficient way of data travelling across a network,as it may have to visit many multiple devices first before reaching the intended device.
       - It is less prone to bottlenecks,as large amounts of traffic are not travelling across the network at any one time. 
       - A fault such as cut cable, or broken device will result in the entire networking breaking.
<br>

## Switch
- Switches are dedicated devices within a network that are designed to aggregate multiple other devices such as computers, printers, or any other networking-capable device using ethernet.
- Usually found in larger networks such as businesses, schools, or similar-sized networks, where there are many devices to connect to the network. 
- Switches can connect a large number of devices by having ports of 4,8,16,24,32,and 64 for devices to plug into.
- Switches are much more efficient than hubs/repeaters.Switches keep track of what device is connected to which port. 
- When they receive a packet, instead of repeating that packet to every port like a hub,it just sends it to the intended target,reducing network traffic.
- Switches and Routers can be connected to one another,this increases the redundancy (the reliability) of a network by adding multiple paths for data to take.
- If one path goes down, another can be used,this may reduce the overall performance of a network because packets have to take longer to travel, there is no downtime.

## Routers
- A router's job is to connect networks and pass data between them.
- Routing is the label given to the process of data travelling across networks.Routing involves creating a path between networks so that this data can be successfully delivered.
- It is useful when devices are connected by many paths.

## Subnetting
- Subnetting is splitting up a network into smaller, miniature networks within itself.
- It is achieved by splitting up number of hosts that can fit within the network, represented by a number- subnet mask.
- Subnet mask is represented as a number of 4 bytes(32 bits), ranging from 0-255.
- Subnets use IP addresses in 3 different ways, identifying network address, host address & default gateway.
   - Network address - Identifies the start of actual network & used to identify network's existence.
   - Host address - Used to identify a device on the subnet(within a network).
   - Default gateway - Special address assigned to device on a network responsible for sending data to another network.
<br>

## ARP
- Stands for Address Resolution Protocol, it is responsible for allowing devices to identify themselves on a network.
- ARP allows device to associate its MAC address with IP address on the network.
- Each device on a network will keep a log of the MAC addresses associated with other devices. 
- When devices wish to communicate with another, they send a broadcast to the entire network searching for the specific device. 
- Devices use ARP to find the MAC address (physical identifier) of a device for communication.
## How does it work?
- Each device within a network has a ledger to store information on, which is called a cache. 
- In the context of ARP, this cache stores the identifiers of other devices on the network.
- ARP sends 2 types of messages: ARP request & ARP reply.
    - ARP Request – The device broadcasts: “Who has this IP address? What is your MAC address?”
   - ARP Reply – The device with that IP address responds with its MAC address.
- The requesting device stores the IP-to-MAC mapping in its ARP cache for future use.

## DHCP
- IP addresses can be assigned either manually,by entering them physically into a device,or automatically and most commonly by using a DHCP (Dynamic Host Configuration Protocol)server.
- When a device connects to a network,if it has not already been manually assigned an IP address,it sends out a request (DHCP Discover)to see if any DHCP servers are on the network. 
- The DHCP server then replies back with an IP address the device could use (DHCP Offer).
- The device then sends a reply confirming it wants the offered IP Address (DHCP Request). 
- The DHCP server sends a reply acknowledging this has been completed,and the device can start using the IP Address (DHCP ACK).



