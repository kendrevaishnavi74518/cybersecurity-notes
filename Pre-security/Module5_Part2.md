## OSI Model
- OSI stands for Open Systems Interconnections, it is an essential model used in networking.
- It provides a framework showing how all networked devices send, receive & interpret data.
- The OSI model provides a standard way for different devices and systems to communicate with each other,even if they have different designs or functions.
- It has 7 layers.
- Key term for pieces of information getting added to data: **Encapsulation.**
- OSI Model:
    1. Physical - Easiet layer to grasp, references the physical components of hardware, devices use electric signals to transfer data between each other in binary system(0 or 1). Ex: ethernet cables.
    2. Data Link - Focuses on physical addressing of transmission, receives a packet from network layer containing the IP address and adds the destination MAC address.
        - Inside every network-enabled computervis a Network Interface Card (NIC)which comes with a unique MAC address to identify it.
    3. Network - Routing simply determines the most optimal path in which these chunks of data should be sent.
        - Network Layer (Layer 3) determines the best path for data to reach its destination.
        - OSPF(Open shortest path first) and RIP(Routing information protocol) are routing protocols used at this layer.
        - The best route may depend on shortest path, reliability, and connection speed.
        - This layer uses IP addresses to deliver packets.
        - Routers are Layer 3 devices because they route packets using IP addresses.
    4. Transport - Plays vital role in transmitting data across network, can be difficult to grasp.
        - Follows 2 different protocols: TCP & UDP.
        1. TCP(Transmission Control Protocol) - Guarntees reliability & accuracy of data, reserves a constant connection,incorporates error checking,helps control flow of data so devices are not overwhelmed, can retransmit missing data to ensure complete delivery,significantly slower than UDP.
           - Ex: file sharing, web browsing, and email, where accurate and complete data is important.
        2. UDP(User Datagram Protocol) - Faster than TCP, doesn't guarntee reliability & accuracy of data, useful where small pieces are being sent, doesn't reserve a connection between devices,useful when speed is more important than reliability,common uses include video streaming, online gaming, and DNS.
    5. Session- Creates and maintains sessions/connections between devices,closes the session when the connection is no longer needed or is lost.
       - Uses checkpoints so that if data is lost, only the missing/Snewest data needs to be resent.
       - Each session is unique and separate, so data belongs to its specific session.
    6. Presentation - Translates and formats data so different applications can understand it.
       - Ensures data is presented in a standard format, even if different software is used.Handles data encryption and decryption.
       - Ex: HTTPS encryption.
    7. Application - The layer closest to the user. It provides network services and protocols that applications use to communicate over a network.
       - Examples include web browsers, email clients, and FileZilla, DNS(Domain Name System) translates domain names into IP addresses.
       - Applications may provide a GUI (Graphical User Interface) for users to interact with these services.

## Packet & Frames
- Packet is a piece of data from Layer 3, containing info such as header & payload.
- Frame is used at Layer 2, which encapsulates the packet & adds additional info such as MAC addresses.
- Packets are efficient way of communicating data, as data is exchanged in small pieces chances of bottleneck are low across a network.
- Some notable headers included in a packet - 
    - Time to Live(TTL) - Sets an expiry time for a packet so it doesn't remain on the network forever if it can't reach its destination.
    - Checksum - Provides integrity checking protocols for TCP/IP, if any data is changed, this value will be different from what was expected and therefore corrupt.
    - Source address - IP address of the device that the packet is being sent from so that data knows where to return to.
    - Destination Address - Device's IP address the packet is being sent to so that data knows where to travel next.
<br>

- **TCP/IP Protocol** - Consists of 4 layers, summarized version of OSI model.
    1. Application
    2. Transport
    3. Internet 
    4. Network Interface
- TCP is connection-based.
- TCP Packets contain various sections of information known as header, added from encapsulation. Some crucial one's are:
    | Header                     | Description                                                                   |
    | -------------------------- | ----------------------------------------------------------------------------- |
    | **Source Port**            | Port used by the **sender** to send data.                                     |
    | **Destination Port**       | Port where the **receiving application/service** is running.                  |
    | **Source IP**              | IP address of the **sender**.                                                 |
    | **Destination IP**         | IP address of the **receiver**.                                               |
    | **Sequence Number**        | Numbers data pieces so they can be **put in the correct order**.              |
    | **Acknowledgement Number** | Indicates the **next data/sequence number expected**.                         |
    | **Checksum**               | Checks whether the data was **corrupted during transmission**.                |
    | **Data**                   | The **actual data** being transmitted.                                        |
    | **Flag**                   | Controls how TCP handles the connection, especially during the **handshake**. |

## TCP Three-way handshake
- It is a process used to establish connection between 2 devices.
- Messages used in the process are:
   - SYN: Client initiates the process by sending the initial packet, it is used to start connection & synchronize the 2 devices together.
   - SYN/ACK: Sent by server to acknowledge the synchronization from client.
   - ACK: Can be used by either the client or server to acknowledge that a series of messages/packets have been successfully received.
   - DATA: Once a connection has been established,data is sent via the "DATA" message.
   - FIN: Used to close the connection properly after it is completed.
   - RST: Abruptly ends all communication, it is last resort & indicates there was problem during the process.
- Order of the process:
     1. SYN - Client: Here's my Initial Sequence Number(ISN) to SYNchronise with (0)
     2. SYN/ACK - Server: Here's my Initial Sequence Number (ISN) to SYNchronise with (5,000), and I ACKnowledge your initial number sequence (0)
     3. ACK - Client: I ACKnowledge your Initial Sequence Number (ISN) of (5,000), here is some data that is my ISN+1 (0 + 1)
- TCP will close a connection once a device has determined that the other device has successfully received all of the data.
- Because TCP reserves system resources on a device, it is best practice to close TCP connections as soon as possible.
- Process of closure:
   - Client sends Server a "FIN" packet. Because server received this, it will let client know that he received it and that it also wants to close the connection (using FIN). CLient has heard server loud and clear and will let server know that client acknowledges this.

## UDP/IP
- User Datagram Protocol(UDP)is another protocol that is used to communicate data between devices.
- UDP is a stateless protocol that doesn't require a constant connection between the two devices for data to be sent.
- UDP packets are much simpler than TCP packets and have fewer headers.
- Standard UDP headers are:
     - Time to Live(TTL) - Sets an expiry time for a packet so it doesn't remain on the network forever if it can't reach its destination. 
     - Source address - IP address of the device that the packet is being sent from so that data knows where to return to.
     - Destination Address - Device's IP address the packet is being sent to so that data knows where to travel next.
     - Source Port - Usually randomly chosen from available ports 0–65535.
     - Destination Port - Identifies the specific service/application receiving the data.
     - Data - Header where data being transmitted is sorted.
- No acknowledgement is sent during a connection, in UDP.

## Ports
- The standard rule for web data is port 80.
- Any port that is within 0 and 1024 (1,024) is known as a common port.
- Commonly used ports are: 
    - FTP (File Transfer Protocol) – Port 21: Used for transferring files.
   - SSH (Secure Shell) – Port 22: Used for secure remote login through a command-line interface.
   - HTTP (Hypertext Transfer Protocol) – Port 80: Used for accessing websites.
   - HTTPS (Hypertext Transfer Protocol Secure) – Port 443: Used for secure web browsing with encryption.
   - SMB (Server Message Block) – Port 445: Used for sharing files and printers over a network.
   - RDP (Remote Desktop Protocol) – Port 3389: Used for remote access through a graphical desktop interface.
- However, applications will presume that the standard is being followed, so you will have to provide a colon (:) along with the port number.

