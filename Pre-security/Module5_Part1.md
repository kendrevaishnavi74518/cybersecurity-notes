## What is Networking?

- Firs iteration of Internet was within the ARPANET project in late 1960s.
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



