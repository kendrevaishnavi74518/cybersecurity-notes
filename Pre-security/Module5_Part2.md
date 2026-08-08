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
      - Uses checkpoints so that if data is lost, only the missing/newest data needs to be resent.
      - Each session is unique and separate, so data belongs to its specific session.
    6. Presentation - Translates and formats data so different applications can understand it.
     - Ensures data is presented in a standard format, even if different software is used.Handles data encryption and decryption.
     - Ex: HTTPS encryption.
    7. Application - The layer closest to the user. It provides network services and protocols that applications use to communicate over a network.
      - Examples include web browsers, email clients, and FileZilla, DNS(Domain Name System) translates domain names into IP addresses.
      - Applications may provide a GUI (Graphical User Interface) for users to interact with these services.
