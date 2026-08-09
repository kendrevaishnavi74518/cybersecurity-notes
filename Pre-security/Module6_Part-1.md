## How the Web Works? - DNS
- DNS stands for Domain Name System.
- It converts the numeric IP address to human-readable language.
## Domain Hierarchy
- TLD(Top-Level Domain): It is the most righthand part of a domain name.
     - There are 2 types of TLD: gTLD(Generic Top Level) & ccTLD(Country Code Top Level).
     - gTLD was meant to tell the user domain name's purpose, for ex: a .com would be for commercial purposes,.org for an organisation,.edu for education & .gov for government.
     - ccTLD was usedd for geographical purposes.
- Second Level Domain: When registering a domain name,the second-level domain is limited to 63 characters + the TLD and can only use a-z 0-9 and hyphens (cannot start or end with hyphens or have consecutive hyphens).
- Subdomain: A subdomain sits on the left-hand side of the Second-Level Domain using a period to separate it.
     - A subdomain name has the same creation restrictions as a Second-Level Domain.
     - We can use multiple subdomains split with periods to create longer names. 
     - But the length must be kept to 253 characters or less. 
     - There is no limit to the number of subdomains wecan create for our domain name.
## Record Types
- A Record: These records resolve to IPv4 addresses, ex: 104.26.10.229
- AAAA Record: Records resolve to IPv6 addresses, ex: 2606:4700:20::681a:be5 
- CNAME Record: These records points one domain name to another domain name.
- MX Record: These records resolve to address of the servers that handle email for the domain.
   - These also come with a priority flag.
   - This tells the client in which order to try the servers,this is perfect for if the main server goes down and email needs to be sent to a backup server.
- TXT Record: These are fields where any text-based data can be stored.TXT records are strings of text.
   - TXT records have multiple uses, but common one's are:
      - Email verification: Specifies which servers are allowed to send emails for the domain, helping prevent spam and spoofing.
      - Domain ownership verification: Proves ownership when using third-party services.
## DNS Request
- Process:
     - Local Cache: Your computer first checks its local DNS cache for the IP address.
     - Recursive DNS Server: If the address isn't found, your computer sends the request to a Recursive DNS Server,usually provided by your ISP.
     - Recursive Cache: The Recursive DNS Server checks its own cache. If it has the answer, it sends it back immediately.
     - Root DNS Server: If the answer isn't cached, the Recursive DNS Server contacts a Root DNS Server, acts as the backbone of internet.
     - TLD Server: The Root Server directs the request to the appropriate TLD (Top-Level Domain) Server, such as .com.
     - Authoritative DNS Server: The TLD Server directs the request to the domain's Authoritative DNS Server, which stores the actual DNS records.
     - IP Address: The Authoritative Server returns the requested IP address.
     - Response: The Recursive DNS Server caches the answer and sends the IP address back to your computer.
     - TTL: The cached record is stored for a specific time based on its TTL (Time To Live).