### HTTP and HTTPS
* **HTTP** = Hypertext Transfer Protocol
* **HTTPS** = Hypertext Transfer Protocol Secure
* Used by web browsers to communicate with **web servers**.
* HTTP/HTTPS rely on **TCP**.

### Common HTTP Methods
| Method     | Purpose                                                            |
| ---------- | ------------------------------------------------------------------ |
| **GET**    | Retrieves data from a server, such as HTML files or images.        |
| **POST**   | Submits new data, such as forms or file uploads.                   |
| **PUT**    | Creates a new resource or updates/overwrites existing information. |
| **DELETE** | Deletes a specified resource or file.                              |

### Common Ports
| Protocol  | Default TCP Port |
| --------- | ---------------: |
| **HTTP**  |           **80** |
| **HTTPS** |          **443** |

### HTTP Communication
When a browser requests a webpage, many details are exchanged between the **client and server**, even though they are not displayed to the user.

Examples of information exchanged include:
* Web server version
* When the page was last modified
* Requested page/data
* Server response information

Tools such as **Wireshark** can be used to inspect this communication.

### Using Telnet to Talk HTTP
You can manually communicate with an HTTP server using Telnet:
```bash
telnet 10.49.172.236 80
```

Then send:
```http
GET / HTTP/1.1
Host: anything
```

Press **Enter twice** to send the request.

To request a specific file:
```http
GET /file.html HTTP/1.1
Host: anything
```

Depending on the web server, this may also work:
```http
GET /file.html
```

### Why This Is Useful
Using Telnet to manually send HTTP requests is useful for **troubleshooting**, because you are directly communicating with the web server using the HTTP protocol.

### FTP (File Transfer Protocol)
* **FTP** is designed specifically for **transferring files**.
* It can be more efficient for file transfer than HTTP under similar conditions.
* FTP uses **TCP**.
* **FTP control connection:** TCP **port 21**
* File/data transfers occur over a **separate connection**.

### Common FTP Commands
| Command  | Purpose                              |
| -------- | ------------------------------------ |
| **USER** | Enter username                       |
| **PASS** | Enter password                       |
| **RETR** | Download/retrieve a file from server |
| **STOR** | Upload/store a file on server        |
| **LIST** | Request directory/file listing       |

### FTP Communication
The FTP client and server exchange different commands and responses.
Example:
```text
Client: ls
   ↓
Server receives: LIST
   ↓
Server: Directory listing
```

### Important Point: Separate Connections
FTP uses separate connections for:
* **Control/commands** — TCP port 21
* **Data transfer** — separate connection

Therefore, the **directory listing** and the **downloaded file** are transferred over separate connections.


