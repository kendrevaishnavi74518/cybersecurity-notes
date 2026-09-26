### TLS for SMTP, POP3, and IMAP
Adding **TLS** to SMTP, POP3, and IMAP works similarly to adding TLS to HTTP.

* **HTTP + TLS → HTTPS**
* **SMTP + TLS → SMTPS**
* **POP3 + TLS → POP3S**
* **IMAP + TLS → IMAPS**

TLS provides secure/encrypted communication while the underlying protocol remains the same.

### Insecure vs Secure Ports
| Protocol  | Default TCP Port |
| --------- | ---------------: |
| **HTTP**  |               80 |
| **SMTP**  |               25 |
| **POP3**  |              110 |
| **IMAP**  |              143 |
| **HTTPS** |              443 |
| **SMTPS** |        465 / 587 |
| **POP3S** |              995 |
| **IMAPS** |              993 |

#### Quick Recall
HTTP   → HTTPS   → 80 → 443
SMTP   → SMTPS   → 25 → 465/587
POP3   → POP3S   → 110 → 995
IMAP   → IMAPS   → 143 → 993

### SSH (Secure Shell)
* **SSH** provides secure remote login and administration.
* It was developed as a safer alternative to **TELNET**, which sends traffic in cleartext.
* **SSH server:** TCP **port 22**
* **TELNET server:** TCP **port 23**

### SSH History
| Version     | Year | Key Point                                                     |
| ----------- | ---: | ------------------------------------------------------------- |
| **SSH-1**   | 1995 | Developed by Tatu Ylönen and released as freeware             |
| **SSH-2**   | 1996 | More secure version                                           |
| **OpenSSH** | 1999 | Open-source SSH implementation released by OpenBSD developers |

Today, SSH clients are commonly based on **OpenSSH**.

### Benefits of OpenSSH
| Feature                   | Purpose                                                                                |
| ------------------------- | -------------------------------------------------------------------------------------- |
| **Secure Authentication** | Supports passwords, public-key authentication, and two-factor authentication           |
| **Confidentiality**       | End-to-end encryption protects against eavesdropping                                   |
| **Integrity**             | Cryptography protects data from being modified                                         |
| **Tunneling**             | Routes other protocols through a secure SSH tunnel, similar to a VPN                   |
| **X11 Forwarding**        | Allows graphical applications on a remote Unix-like system to be used over the network |

### Basic SSH Connection
```bash id="5kj4s2"
ssh username@hostname
```
If the remote username is the same as the local username:

```bash id="2x8y1m"
ssh hostname
```
You may be prompted for a password. With **public-key authentication**, authentication can occur without entering a password.

### X11 Forwarding
To run graphical applications on a remote Unix-like system:

```bash id="7v5n9c"
ssh 192.168.124.148 -X
```
* `-X` → enables **X11 forwarding**.
* Allows GUI applications running on the remote system to be displayed locally.
* The local system needs a suitable graphical environment.

### TELNET vs SSH
| Feature          | TELNET      | SSH                       |
| ---------------- | ----------- | ------------------------- |
| Security         | ❌ Cleartext | ✅ Encrypted               |
| Authentication   | Basic       | Password, public key, 2FA |
| Confidentiality  | ❌           | ✅                         |
| Integrity        | ❌           | ✅                         |
| Default TCP Port | **23**      | **22**                    |

### SFTP (SSH File Transfer Protocol)
* **SFTP** allows **secure file transfer**.
* It is part of the **SSH protocol suite**.
* Uses the same port as SSH: **TCP 22**.
* SFTP can be enabled through the **OpenSSH server configuration**.

### SFTP Commands
Connect to an SFTP server:
```bash id="n8m4y2"
sftp username@hostname
```
After logging in:

| Command        | Purpose         |
| -------------- | --------------- |
| `get filename` | Download a file |
| `put filename` | Upload a file   |

* SFTP commands are generally **Unix-like**.
* SFTP commands can differ from traditional FTP commands.

### SFTP vs FTPS
**Do not confuse SFTP with FTPS.**
| Feature              | SFTP                       | FTPS                          |
| -------------------- | -------------------------- | ----------------------------- |
| Full form            | SSH File Transfer Protocol | File Transfer Protocol Secure |
| Security             | **SSH**                    | **TLS**                       |
| Default port         | **22**                     | **990**                       |
| Based on             | SSH                        | FTP                           |
| Certificate required | No TLS certificate         | **TLS certificate required**  |
| Configuration        | OpenSSH                    | TLS + FTP configuration       |

### FTPS
* **FTPS** secures FTP using **TLS**, similar to HTTPS.
* Traditional FTP uses **TCP 21**.
* FTPS usually uses **TCP 990**.
* Requires a proper **TLS certificate**.
* Can be more difficult to configure through strict firewalls because FTP uses **separate control and data connections**.

