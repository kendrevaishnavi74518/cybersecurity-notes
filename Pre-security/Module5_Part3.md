## Port Forwarding
- Port forwarding is an essential component in connecting apps & services to Internet.
- Without it, apps & services like web servers are only available to devices within same direct network.
- Intranet = A private network accessible only to authorized users within the network.
- Router is used to configure port forwarding.
<br>

## Firewall
- It is adevice within a network that monitors network traffic using a set of predefined security rules.
- It operates at layer 3 & 4 of OSI model. 
- An admin can configure a firewall to permit or deny traffic from entering or exiting a network.
- Primary 2 categories of firewall are:
    1. Stateful - This type uses entire information from a connection, rather than inspecting individual packet.
       - It determines behavior of a device based upon entire connection.
       - It consumes many resources in comparison to stateless, as decision making is dynamic.
        - If a connection from a host is bad, it will block the entire device.
    2. Stateless - It uses a static set of rules to determine whether or not individual packets are acceptable or not.
       - Though it uses fewer resources, it is said to be dumber as it is  only effective as he rules that are defined within them.If a rule is not exactly matched, it is effectively useless.
       - It is great when receiving large amount of traffic from set of hosts(DDoS attack)
## VPN Basics
- VPN is the short for Virtual Private Network, it allows devices on separate network to communicate securely by creating a dedicated path between each other(tunnel).
- Devices connected within this tunnel form their own private network.
- Key benefits of VPN include:
     - Connects different locations: Allows offices in different locations to access shared resources.
     - Provides privacy: Encrypts traffic so others cannot easily read or sniff it, especially on public Wi-Fi.
     - Provides some anonymity: Hides your traffic from some intermediaries, but the VPN provider may still be able to log your activity.
- TryHackMe uses a VPN to securely connect users to vulnerable machines without exposing them directly to the Internet.
- VPN Technologies
    1. PPP (Point-to-Point Protocol): Provides authentication and encryption but is non-routable by itself.
    2. PPTP (Point-to-Point Tunneling Protocol): Allows PPP data to travel across networks; easy to set up but has weak security.
    3. IPSec (Internet Protocol Security): Secures data using the IP framework and provides strong encryption.
## LAN Networking Devices
1. Routers
   - A router connects different networks and forwards data between them.
   - Routers operate at Layer 3 (Network Layer) of the OSI model.
   - Routing determines the best path for data based on factors like:
     - Shortest path
     - Reliability
     - Connection speed (copper/fibre)
  - Routers can be configured for features such as firewalling and port forwarding.
  - Router = Connects networks + routes packets using IP addresses.
2. Switch
   -  A switch connects multiple devices within a network.
   - Layer 2 switches forward frames using MAC addresses.
   - Layer 3 switches can also route packets using IP addresses and perform some router functions.
   - Layer 2 Switch = MAC address → Frames
   - Layer 3 Switch = MAC + IP → Frames + Routing
3. VLAN
   - VLAN (Virtual Local Area Network) divides a physical network into separate virtual networks.
   - Devices in different VLANs can be isolated from each other even when connected to the same switch.
   - VLANs improve security and network management.
   - VLAN = Virtually separates devices into different networks.
   - Example: Sales and Accounting can both access the Internet but can be prevented from communicating directly with each other.