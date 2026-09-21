### POP3 (Post Office Protocol Version 3)
* **POP3** allows a mail client to **retrieve/download emails** from a mail server.
* **SMTP** → sends/transfers email.
* **POP3** → retrieves email.
* **POP3 default port:** TCP **110**

### Common POP3 Commands
| Command                     | Purpose                                 |
| --------------------------- | --------------------------------------- |
| **USER** `<username>`       | Identifies the user                     |
| **PASS** `<password>`       | Provides the user's password            |
| **STAT**                    | Shows number of messages and total size |
| **LIST**                    | Lists messages and their sizes          |
| **RETR** `<message_number>` | Retrieves a specific email              |
| **DELE** `<message_number>` | Marks a message for deletion            |
| **QUIT**                    | Ends the session and applies changes    |

### SMTP vs POP3
| Protocol | Purpose        | Default TCP Port |
| -------- | -------------- | ---------------: |
| **SMTP** | Send email     |           **25** |
| **POP3** | Retrieve email |          **110** |

### Security Concern
The POP3 session shown uses **unencrypted communication**.

Therefore, someone capturing the network traffic could potentially:
* Read the POP3 commands.
* Read the email contents.
* **Capture the username and password**.
* This can be observed using **Wireshark**.

**Key line:** **SMTP sends email → POP3 retrieves email → TCP 110 → unencrypted POP3 traffic can expose credentials and messages.**

### IMAP (Internet Message Access Protocol)
* **IMAP** allows email messages to be **synchronized across multiple devices**.
* Useful when checking the same mailbox from:
  * Desktop
  * Laptop
  * Smartphone
* Unlike POP3, IMAP generally **keeps emails on the server** and synchronizes their state across clients.

### POP3 vs IMAP
| Feature                 | POP3                                | IMAP                                         |
| ----------------------- | ----------------------------------- | -------------------------------------------- |
| Main purpose            | Retrieve/download emails            | Synchronize emails                           |
| Server storage          | Email may be downloaded and deleted | Emails generally remain on server            |
| Multiple devices        | Less suitable                       | **Well suited**                              |
| Message synchronization | Limited                             | **Read, moved, deleted states synchronized** |
| Default TCP port        | **110**                             | **143**                                      |

### Common IMAP Commands
| Command                               | Purpose                            |
| ------------------------------------- | ---------------------------------- |
| **LOGIN** `<username> <password>`     | Authenticates the user             |
| **SELECT** `<mailbox>`                | Selects a mailbox/folder           |
| **FETCH** `<mail_number> <data_item>` | Retrieves email data               |
| **MOVE** `<sequence_set> <mailbox>`   | Moves messages to another mailbox  |
| **COPY** `<sequence_set> <data_item>` | Copies messages to another mailbox |
| **LOGOUT**                            | Ends the session                   |

### Important: IMAP Tags
In the example, commands are preceded by identifiers such as:
```text
A LOGIN
B SELECT
C FETCH
D LOGOUT
```
These tags allow the client to **match server responses with the corresponding commands**.

### Default Port Numbers
| Protocol   | Transport | Default Port |
| ---------- | --------- | -----------: |
| **TELNET** | TCP       |       **23** |
| **DNS**    | UDP / TCP |       **53** |
| **HTTP**   | TCP       |       **80** |
| **HTTPS**  | TCP       |      **443** |
| **FTP**    | TCP       |       **21** |
| **SMTP**   | TCP       |       **25** |
| **POP3**   | TCP       |      **110** |
| **IMAP**   | TCP       |      **143** |

### Easy Recall
**21 FTP → 23 TELNET → 25 SMTP → 53 DNS → 80 HTTP → 110 POP3 → 143 IMAP → 443 HTTPS**
