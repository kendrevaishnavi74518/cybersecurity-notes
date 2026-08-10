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