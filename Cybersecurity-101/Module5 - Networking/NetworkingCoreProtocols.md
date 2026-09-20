### DNS (Domain Name System)
* **DNS** maps **domain names to IP addresses**, so users don't need to memorize IP addresses.
* **Layer:** Application Layer (**OSI Layer 7**)
* **UDP port:** **53** (default)
* **TCP port:** **53** (default fallback)

### Important DNS Records
| Record    | Purpose                                                | Example                         |
| --------- | ------------------------------------------------------ | ------------------------------- |
| **A**     | Maps hostname → **IPv4 address**                       | `example.com → 172.17.2.172`    |
| **AAAA**  | Maps hostname → **IPv6 address**                       | `example.com → IPv6 address`    |
| **CNAME** | Maps one domain name → **another domain name**         | `www.example.com → example.com` |
| **MX**    | Specifies the **mail server** responsible for a domain | `example.com → mail server`     |

### How DNS Is Used
**Website:**

```text
example.com
     ↓
DNS query for A record
     ↓
IPv4 address
     ↓
Browser connects to server
```

**Email:**

```text
test@example.com
       ↓
DNS query for MX record
       ↓
Mail server for example.com
```

### `nslookup`
`nslookup` can be used to look up the IP address of a domain.
```bash
nslookup www.example.com
```

Example result:
```text
Name:    www.example.com
Address: 93.184.215.14
Name:    www.example.com
Address: 2606:2800:21f:cb07:6820:80da:af6b:8b2c
```

* `93.184.215.14` → **IPv4 (A record)**
* `2606:2800:21f:cb07:6820:80da:af6b:8b2c` → **IPv6 (AAAA record)**

### DNS Query Process
A typical lookup can involve separate queries for **A** and **AAAA** records:
```text
Client → DNS Server: A www.example.com
DNS Server → Client: 93.184.215.14

Client → DNS Server: AAAA www.example.com
DNS Server → Client: IPv6 address
```

### WHOIS
* When you **register a domain**, you get the authority to manage its DNS records, such as:
  * **A**
  * **AAAA** - IPv6
  * **MX** - Mail servers
* A domain can generally be registered for **one or more years** by paying the required annual fee.

### WHOIS Records
* **WHOIS** provides information about the entity that registered a domain.
* WHOIS is **not an acronym**; it is pronounced **“who is.”**
* Registrant information may include:
  * Name
  * Address
  * Phone number
  * Email address
* WHOIS records can also show:
  * **Creation date**
  * **Last updated date**
  * **Expiration date**
  * Registrar information

### Privacy Protection
* Registrants can use **domain privacy services** to hide their personal contact information from publicly available WHOIS records.
* With privacy protection enabled, the WHOIS record may show the privacy service's details instead of the actual registrant's information.

### `whois` Command
On Linux, the `whois` command can be used to query WHOIS information:

```bash
whois example.com
```
Example fields:
```text
Domain Name: [REDACTED].COM
Registrar: GoDaddy.com, LLC
Updated Date: 2017-07-05
Creation Date: 1993-04-02
Expiration Date: 2026-10-20
Registrant Name: Registration Private
Registrant Organization: Domains By Proxy, LLC
```

