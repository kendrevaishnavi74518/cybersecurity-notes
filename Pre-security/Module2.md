# Module 2

## Inside of a computer

```mermaid
graph LR
A[Press Power Button] --> B[Firmware Starts] --> C[POST] --> D[Select Boot Device] --> E[Start bootloader]
```
- Step 1: When we press the start button, a signal is sent to the PSU(Power Supply Unit) to allow power to flow.
- Step 2: The UEFI(Unified Extensible Firmware Interface) co-ordinates with all the components initializes & starts them, this is the first software that runs.
- Step 3: UEFI runs POST(Power-On Self Test) to check that required hardware is present, configured, and functioning. Errors trigger beeps or alerts.
- Step 4: UEFI follows a priority list to determine which device to boot from - typically an SSD or HDD with the OS installed.
- Step 5: The bootloader loads the OS into the RAM, the UEFI then hands over the controls to the OS, completing the sequence.

## Computer Types

There are 4 types of computers: Laptop, Desktop, Workstation & Server.
<br>

- Laptop: Has screen & keyboard. Pupose: Portable everyday computing.
- Desktop: Has screen & keyboard. Pupose: Fixed at one place, tasks ran smoothly longer, designed for consistency rather than mobility.
- Workstation: Has screen & keyboard. Pupose: Looks like desktop, but prioritizes accuracy & reliability, using specialized components to reduce errors during long or complex computations.
- Server: Doesn't have screen & keyboard. Purpose: Answers requests coming from users, runs continuously.
**Redundant power reduces a single failure point. Uptime improves when redundancy is combined with backups and monitoring.**

# Computers hidden in everyday objects

- Smartphone: Pocket-sized computer, optimized battery life & connections. Ex: iPhone, Android phone etc.
- Tablet: Large screen, uses touch sense instead of keyboard or mouse. Ex: iPad, drawing tablet.
- IoT device: Network connected device with single purpose. Ex: Thermostat, smart watch, fitness watch, smart doorbell, etc.
- Embedded computer: Computer built into another device.
Ex: Coffee maker controller, automatic door sensor,etc.
<br>

- IoT devices connect to a network to report data or receive commands. 
- Embedded computers might not connect to anything; they do their job inside the machine, often for years without anyone knowing they exist.
<br>

- **Mobility costs power.** 
- **Reliability costs money.** 
- The most critical computers are not always the fastest or flashiest. Sometimes, they are the silent chips that keep doors opening, planes flying, and coffee machines brewing.

## Client-Server Basics

- Networks such as **ARPANET, CYCLADES, NPL, and NSFNET** paved the way for the modern internet.
- Port: It is used to identify a specific service running on a system. When a client wants to access a service on a server, it must connect using the correct port.
**A single server can run multiple services at the same time, with each service identified by a different port.**
<br>

- DNS stands for Domain Name Service and works similarly to GPS, when you enter the name of, a website, DNS resolves it to server's location. These location coordinates are called an Internet Protocol (IP) address.
<br>

- Hypertext Transfer Protocol (Secure), abbreviated as HTTP(S), is a stateless client-server protocol used for the World Wide Web. This means that each request is processed independently, without the server retaining information about previous requests.
<br>

- HTTP (also called Request for Comments, or RFC documents), there are 9 core commands.
- GET: Used to retrieve a resource from the server.
- POST
- PUT
- DELETE
- PATCH
- HEAD
- OPTIONS
- CONNECT
- TRACE
<br>

- Scheme: Tells us which protocol was used: HTTP or HTTPS.
- Host: Tells us the name of the host we request resources from.
- Filename: Indicates which file we requested from the host. In our request, this is "/", which actually translates to "index.html".
- Address: Displays the IP address where the website is hosted.In our example, we are hosting the website on the same device. That's why the address 127.0.0.1 is shown.
- Status: This field indicates whether the request was successful.In our example, we received a "200 OK" status, which means that the request was successful.
<br>

- Response: When a request is sent, we will get a response from the server. The response is divided into two parts: the response header and the response body. The response header contains metadata about the response, while the response body contains the requested content.