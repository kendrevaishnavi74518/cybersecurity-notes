## How websites work
2 major components that make up a website:
   1. Front End(Client Side) - the way browser renders a website.
   2. Back End(Server Side) - server that processes the request & returns a response.
## HTML
Website are primarily created using:
   - HTML, to build websites & define their structure.
   - CSS, to add styling to websites.
   - JavaScript, implement complex features on pages using interactivity.

- HTML stands HyperText Markup Language, Elements(tags) are the building blocks of a website & tells browser how to display content.

**Basic Structure of HTML:** (Img as HTML structure)
   - <!DOCTYPE html> defines that page is HTML5 document. This ensures consistency across different browsers & tells browser to interpret webpage using HTML5.
   - <html> root element of HTML page, all other elements come after this.
   - <head> contains info about the page(page title)
   - <body> contents of the webpage, only content within this tag is shown in the browser.
   - <h1> large heading
   - <p> defines paragraph
   - Rhere are tags for buttons (<button>), images (<img>), lists, and much more. 

- Tags can contain attributes such as the class attribute which can be used to style an element (e.g. make the tag a different color)
- An element can have multiple attributes each with its own unique purpose, e.g., <p attribute1="value1" attribute2="value2">.
- Elements can also have an id attribute (<p id="example">), which is unique to the element. 
- Unlike the class attribute, where multiple elements can use the same class, an element must have different id's to identify them uniquely. 
- Element id's are used for styling and to identify it by JavaScript.

## JavaScript
- It is one of the most popular coding language, it allows pages to become interactive.
- HTML creates the website structure & content, JS is used to control functionality of the page.
- Without JS the page would always be static.
- JS can dynamically update the page in real-time, giving functionality to change the style of a button when a particular event on the page occurs (such as when a user clicks a button) or to display moving animations.
- **JavaScript** can be added to HTML using <script> tags or loaded from an external **.js** file using the **src** attribute.
- JavaScript can **find and modify HTML elements** using methods such as document.getElementById().
- **Events** such as *onclick* and *onhover* can trigger JavaScript when an action occurs.
- JavaScript can be used to **change webpage content dynamically**. Ex: document.getElementById("demo").innerHTML = "Hack the Planet";

## Sensitive Data Exposure
**Sensitive Data Exposure** occurs when a website accidentally exposes sensitive information to users, often through its **HTML or JavaScript source code**.

- Developers may accidentally leave **login credentials, hidden links, or other sensitive information** in the source code.
- Attackers can find this information by using **View Page Source** or browser developer tools.
- Exposed credentials or links can be used to gain **unauthorized access** to other parts of the application.
- **HTML comments** can also accidentally contain sensitive information.

## Security Tip
- When testing a web application, always check the **page source code** for exposed credentials, hidden links, comments, or other sensitive information.

## HTML Injection
**HTML Injection** is a vulnerability that occurs when a website displays **user input without properly sanitising it**.
- If user input is not filtered, an attacker can inject **HTML or JavaScript code** into the webpage.
- The browser may interpret the injected code as actual HTML or JavaScript.
- This can allow an attacker to **change the appearance or functionality** of the webpage.
- **Input sanitisation** means filtering or removing potentially harmful input before using it.
- The main rule is: **Never trust user input.**

## Example
If a website displays:
Hello, [user input]

## Putting it all together
- When user requests a website, the computer needs to know server's IP address, it needs to talk to, for this it uses DNS.
- Computer then talks to the web server using a special set of commands called the HTTP protocol; the webserver then returns HTML, JavaScript, CSS, Images, etc., which the browser then uses to correctly format and display the website.

## Load Balancers
A **Load Balancer** distributes incoming traffic across multiple servers to handle **high traffic** and provide **high availability**.

- Receives the user's request first and forwards it to one of the available servers.
- Uses algorithms to decide which server should handle the request.
- **Round-robin:** Sends requests to each server in turn.
- **Weighted:** Sends requests based on server workload/capacity.
- Performs **health checks** to ensure servers are working.
- If a server fails, the load balancer **stops sending traffic to it** until it recovers.
-  **Load Balancer = Distributes traffic + Provides failover**

## CDN (Content Delivery Network)
A **CDN** stores static website files such as **JavaScript, CSS, images, and videos** on servers around the world.

- Sends files from a server **closest to the user**.
- Reduces traffic and improves **website speed**.
- **CDN = Delivers content from a nearby server**

## Databases

A **database** stores and retrieves information used by websites and applications.

- Web servers communicate with databases to **store and retrieve data**.
- Databases can range from simple files to large clusters of servers.
- Common databases include **MySQL, MSSQL, MongoDB, and PostgreSQL**.

## WAF (Web Application Firewall)
A **WAF** sits between the user and the web server and helps protect the website from **malicious requests and attacks**.

- Analyses incoming web requests for common attacks.
- Can identify suspicious or automated requests.
- Uses **rate limiting** to restrict excessive requests.
- Blocks requests that appear to be malicious.

## What is a Web Server?
- A **web server** is software that listens for incoming requests and uses **HTTP** to deliver web content to clients.
- Common web server software:
   - **Apache**
   - **Nginx**
   - **IIS**
   - **NodeJS**
- A web server stores website files in a **root directory** and sends the requested files to the client.

## Virtual Hosts
- **Virtual Hosts** allow one web server to host **multiple websites with different domain names**.

- The server checks the **Host header** in the HTTP request.
- It matches the hostname with its virtual host configuration.
- If a match is found, the correct website is served.
- If no match is found, the **default website** is served.
- Each website can have a different **root directory**.

## Static Content
- **Static content** does not change based on the request.
Examples:
   - Images
   - CSS
   - JavaScript
   - Fixed HTML pages

The web server sends these files **directly to the client**.

## Dynamic Content

- **Dynamic content** can change depending on the request or user input.
Examples:
   - Search results
   - Blog pages showing new posts
   - User-specific content
- Dynamic content is generated by the **backend** using programming/scripting languages.

## Frontend
- The **frontend** is everything the user can see and interact with in the browser.
Examples:
- HTML
- CSS
- JavaScript
- Images

## Backend
- The **backend** works behind the scenes to process requests and generate responses.
- It can:
   - Process user input
   - Interact with databases
   - Call external services
   - Generate dynamic content

Common backend languages:
- **PHP**
- **Python**
- **Ruby**
- **NodeJS**
- **Perl**

