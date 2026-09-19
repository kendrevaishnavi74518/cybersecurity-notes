## UDP and TCP
## UDP – User Datagram Protocol
* **UDP** is a **connectionless** transport-layer protocol (**Layer 4**).
* It allows communication with a specific **process** using **port numbers**.
* No connection needs to be established before sending data.
* It does **not provide delivery confirmation**, so delivery is not guaranteed.
* UDP generally provides **better speed** because it does not use delivery acknowledgements.

### Port Numbers
* Port numbers identify the sending/receiving process.
* Range: **1–65535**
* **Port 0 is reserved**.

## TCP – Transmission Control Protocol
* **TCP** is a **connection-oriented** transport-layer protocol (**Layer 4**).
* It establishes a connection before data transmission.
* Provides **reliable data delivery** using:
  * Sequence numbers
  * Acknowledgements
* Sequence numbers help identify **lost or duplicated packets**.

### TCP Three-Way Handshake
| Step | Packet      | Purpose                                 |
| ---- | ----------- | --------------------------------------- |
| 1    | **SYN**     | Client requests a connection            |
| 2    | **SYN-ACK** | Server acknowledges and responds        |
| 3    | **ACK**     | Client acknowledges the server response |

**Flow:**
`Client → SYN → Server`
`Client ← SYN-ACK ← Server`
`Client → ACK → Server`

### UDP vs TCP
| Feature         | UDP                   | TCP                 |
| --------------- | --------------------- | ------------------- |
| Connection      | Connectionless        | Connection-oriented |
| Reliability     | No delivery guarantee | Reliable delivery   |
| Acknowledgement | No                    | Yes                 |
| Speed           | Faster                | Generally slower    |
| Layer           | Layer 4               | Layer 4             |
| Port Range      | 1–65535               | 1–65535             |

## Encapsulation
* **Encapsulation** is the process where each network layer adds a **header** (and sometimes a **trailer**) to the data received from the layer above.
* This allows each layer to perform its specific function independently.

## Encapsulation Process
| Layer                | Data Unit                  | What is Added               |
| -------------------- | -------------------------- | --------------------------- |
| **Application**      | Application Data           | Original user data          |
| **Transport**        | TCP Segment / UDP Datagram | TCP/UDP header              |
| **Network/Internet** | IP Packet                  | IP header                   |
| **Data Link**        | Frame                      | Link-layer header + trailer |

* At the **receiver**, the process is reversed and the headers/trailers are removed until the original application data is extracted.

## Life of a Packet
1. User enters a search query in a browser.
2. Browser creates an **HTTPS/HTTP request**.
3. **TCP** establishes a connection using the **three-way handshake**.
4. TCP segments are passed to the **IP layer**.
5. IP adds **source and destination IP addresses** and creates an IP packet.
6. The **link layer** adds its header/trailer and sends the frame to the router.
7. Routers remove the link-layer information, inspect the destination IP, and **forward the packet**.
8. The process is reversed at the destination network until the application receives the data.

### TELNET (Teletype Network)
* **TELNET** is a network protocol used for **remote terminal connections**.
* The `telnet` client allows you to:
  * Connect to a remote system.
  * Communicate with it.
  * Issue text commands.
* It can connect to **any server listening on a TCP port**.

### Services Demonstrated
| Service      | Default TCP Port | Function                      |
| ------------ | ---------------: | ----------------------------- |
| **Echo**     |                7 | Echoes everything sent to it  |
| **Daytime**  |               13 | Returns current date and time |
| **HTTP/Web** |               80 | Serves web pages              |

### 1. Echo Server — Port 7
```bash
telnet MACHINE_IP 7
```
* Anything sent to the server is returned exactly as received.
* Exit Telnet using **`Ctrl + ]`**, then:
```text
telnet> quit
```

### 2. Daytime Server — Port 13
```bash
telnet MACHINE_IP 13
```
* Returns the **current date and time**.
* The connection closes after sending the response.

### 3. HTTP Server — Port 80
```bash
telnet MACHINE_IP 80
```
After connecting, send:
```http
GET / HTTP/1.1
Host: telnet.thm
```

Press **Enter twice** to send a blank line and complete the request.
Example response:
```http
HTTP/1.1 200 OK
Content-Type: text/html
```

