## TLS
* Transport Layer Security (TLS) is added to existing protocols to protect communication confidentiality, integrity, and authenticity. Consequently, HTTP, POP3, SMTP, and IMAP become HTTPS, POP3S, SMTPS, and IMAPS, where the appended “S” stands for Secure. We will examine these protocols and the benefits we reaped from TLS.
* Similarly, it is deemed insecure to remotely access a system using the TELNET protocol; Secure Shell (SSH) was created to provide a secure way to access remote systems. Furthermore, SSH is an extensible protocol that offers added security features for other protocols.

### TLS (Transport Layer Security)
* Earlier, attackers could capture network packets and read **cleartext chats, emails, and passwords**.
* A network card in **promiscuous mode** can capture packets that are not specifically destined for that device.
* TLS was developed to protect communication over insecure networks.

### SSL → TLS History
| Version     | Year | Key Point                           |
| ----------- | ---: | ----------------------------------- |
| **SSL 2.0** | 1995 | First public SSL version            |
| **TLS 1.0** | 1999 | Developed by IETF; upgraded SSL 3.0 |
| **TLS 1.3** | 2018 | Major protocol overhaul             |

### What TLS Provides
TLS is a **cryptographic protocol** operating at the **transport layer** of the OSI model.

It provides:

* **Confidentiality** → Others cannot read the exchanged data.
* **Integrity** → Others cannot modify the exchanged data without detection.

```text
Client  ←── Encrypted & protected communication ──→  Server
```

TLS makes applications such as:
* Online banking
* Online shopping
* Messaging
* Email

safer to use over insecure networks.

### Protocols Using TLS
TLS can be added to existing protocols to provide secure communication:

| Original Protocol | TLS-secured Version    |
| ----------------- | ---------------------- |
| HTTP              | **HTTPS**              |
| DNS               | **DoT (DNS over TLS)** |
| MQTT              | **MQTTS**              |
| SIP               | **SIPS**               |
| SMTP              | **SMTPS**              |
| POP3              | **POP3S**              |
| IMAP              | **IMAPS**              |

The **S** generally indicates that SSL/TLS is being used.

### TLS Certificates
A server (or client) that needs to identify itself generally obtains a **signed TLS certificate**.

Basic process:

```text
Server Administrator
       ↓
Creates CSR
(Certificate Signing Request)
       ↓
Submits CSR to CA
       ↓
Certificate Authority verifies it
       ↓
CA issues signed certificate
       ↓
Server uses certificate for identification
```

### Certificate Authority (CA)
* A **CA (Certificate Authority)** signs and issues digital certificates.
* The receiving host can verify the certificate's signature.
* The certificates of trusted CAs need to be installed on the host/browser.
* Browsers come with a list of **trusted certificate authorities**.

### Let's Encrypt
* Generally, obtaining a signed certificate may involve an annual fee.
* **Let's Encrypt** provides certificates **for free**.

### Self-Signed Certificate
* A **self-signed certificate** is created and signed by the same entity using it.
* It does **not prove the server's authenticity** because no trusted third party (CA) has verified it.

### HTTP
* **HTTP** uses **TCP port 80** by default.
* HTTP traffic is sent in **cleartext**, so an attacker who can capture the traffic may read the exchanged data.

### HTTP Request Process
After resolving the domain name to an IP address:
1. **TCP three-way handshake** is established.
2. Client and server communicate using **HTTP**.

Example HTTP request:
```http
GET / HTTP/1.1
```
The TCP connection is later terminated.
```text
DNS Resolution
     ↓
TCP 3-Way Handshake
     ↓
HTTP Communication
     ↓
TCP Connection Termination
```

### HTTPS — HTTP Over TLS
* **HTTPS** = Hypertext Transfer Protocol Secure.
* HTTPS is essentially **HTTP running over TLS**.
* TLS encrypts the application data, preventing others from reading the exchanged HTTP contents.

After resolving the domain name:
1. **TCP three-way handshake**
2. **TLS session establishment**
3. **HTTP communication over TLS**
```text
DNS Resolution
     ↓
TCP 3-Way Handshake
     ↓
TLS Session Establishment
     ↓
Encrypted HTTP/Application Data
     ↓
TCP Connection Termination
```

### HTTP vs HTTPS
| Feature            | HTTP              | HTTPS     |
| ------------------ | ----------------- | --------- |
| Default TCP port   | **80**            | **443**   |
| Encryption         | ❌ No              | ✅ TLS     |
| Traffic visibility | Cleartext         | Encrypted |
| TCP handshake      | ✅                 | ✅         |
| HTTP protocol      | Directly over TCP | Over TLS  |

### Wireshark Observation
With HTTPS, Wireshark shows **"Application Data"** after TLS is established.

The contents cannot normally be read because they are **encrypted**.

Without the required decryption key:
```text
Client → TLS-encrypted data → Server
```

Following the stream produces unreadable/encrypted data rather than the original HTTP request.

### Decrypting HTTPS Traffic
If the required encryption/decryption information is provided to Wireshark:
* TCP handshake remains unchanged.
* TLS negotiation remains unchanged.
* Wireshark can decrypt the application data.
* The underlying HTTP requests/responses, such as `GET`, become visible again.

