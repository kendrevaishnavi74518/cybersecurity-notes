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
## HTTP
- Stands for Hypertext Transfer Protocol, developed by Tim Berners-Lee & team b/w 1989-1991.
- It is a set of rules used for communicating with web servers for transmitting webpage data.
## HTTPS
- Stands for  Hypertext Transfer Protocol Secure.
- Secure version of HTTP.
HTTPS data is encrypted so people can't see the data we are sending or receiving.
- Also gives assurance that we are on the correct web server & not something impersonating it.
## Requests & Responses
- (Image attached as URL field)
- URL: Uniform Resource Locator
   - Scheme: Instructs on ehat protocol to use for accessing resources such as HTTP,HTTPS,FTP.
   - User: Some services require authencation, can put a username & password in URL to log in.
   - Host: Domain name or IP address we wish to access.
   - Port: Port number we want to connect to,usually 80(HTTP), 443(HTTPS); can be hosted on any between 1-65535.
   - Query String: Extra bits of information that can be sent to the requested path.
   - Fragment: Reference to a location on the actual page requested,commonly used for pages with long content and can have a certain part of the page directly linked to it, so it is viewable to the user as soon as they access the page.
<br>

## Making Request
- (Img attached as HTTP request)
- Line 1 – GET: Requests the home page (/) using HTTP/1.1.
- Line 2 – Host: Specifies the website/domain being requested.
- Line 3 – User-Agent: Tells the server which browser and version is being used.
- Line 4 – Referer: Tells the server the previous webpage that led to this request.
- Line 5 – Blank line: Indicates that the HTTP request has ended.
<br>

**Response Format**
- (Img as HTTP Response)
- Line 1 – HTTP/1.1 200 OK: Shows the HTTP version and status code. 200 OK means the request was successful.
- Line 2 – Server: Shows the web server software and version.
- Line 3 – Date: Shows the server's date and time.
- Line 4 – Content-Type: Tells the client the type of content being sent, such as HTML, image, or PDF.
- Line 5 – Content-Length: Shows the size of the response data.
- Blank line: Indicates the end of the HTTP headers.
- Response Body: Contains the requested content, such as the webpage.
## HTTP Methods
- These methods are a way for the client to show their intended action when making an HTTP request.
    1. GET Request: Used for getting info from a web server.
    2. POST Request: Used for submitting data to web servers & potentially creating new records.
    3. PUT Request: Used for submitting data to web server to update info.
    4. DELETE Request: Used for deleting info/records from web server.
## HTTP Status Codes
1. Status Code Ranges
   - 100–199 → Informational: Request is being processed; more information may be needed.
   - 200–299 → Success: Request was successful.
   - 300–399 → Redirection: Request is redirected to another resource.
   - 400–499 → Client Error: There is a problem with the client's request.
   - 500–599 → Server Error: There is a problem on the server.
2. Important Status Codes
   - 200 – OK: Request completed successfully.
   - 201 – Created: A new resource was successfully created.
   - 301 – Moved Permanently: Resource has permanently moved to a new location.
   - 302 – Found: Resource is temporarily at another location.
   - 400 – Bad Request: Request is invalid or missing required information.
   - 401 – Unauthorized: Authentication is required.
   - 403 – Forbidden: Access is denied, even if authenticated.
   - 404 – Not Found: Requested page/resource doesn't exist.
   - 405 – Method Not Allowed: HTTP method isn't allowed for that resource.
   - 500 – Internal Server Error: Server encountered an unexpected error.
   - 503 – Service Unavailable: Server is unavailable, overloaded, or under maintenance.

## HTTP Headers
- Headers are additional information sent between the **client** and **web server** with an HTTP request or response.

## Common Request Headers
- **Host:** Specifies which website/domain you want from the server.
- **User-Agent:** Identifies the **browser and version** being used.
- **Content-Length:** Tells the server the **size of the data** being sent.
- **Accept-Encoding:** Tells the server which **compression methods** the browser supports.
- **Cookie:** Sends stored information back to the server.

## Common Response Headers
- **Set-Cookie:** Tells the browser to **store a cookie**.
- **Cache-Control:** Controls **how long the browser should cache** the response.
- **Content-Type:** Specifies the **type of data** being returned, such as HTML, CSS, image, or PDF.
- **Content-Encoding:** Specifies the **compression method** used for the response.

## HTTP Cookies
- A **cookie** is a small piece of data stored on your computer by a website.
- Cookies are created when a web server sends a **Set-Cookie** header.
- The browser sends the cookie back to the server with **future requests**.
- Because **HTTP is stateless**, cookies help websites remember information about users.
- Cookies can remember:
  - Login/authentication status
  - User preferences
  - Whether you've visited the website before
- Cookies are commonly used for **website authentication**.
- Authentication cookies usually contain a **token** rather than your actual password.

## Viewing Cookies
- You can view cookies using your browser's **Developer Tools**:
1. Open **Developer Tools**.
2. Go to the **Network** tab.
3. Select a request.
4. Check the **Cookies** section to see the cookies sent with the request.

