## Virtualisation Basics

- Virtualisation was created to solve the problem of every software or website needing its own physical server, making computer systems expensive & inefficient.
<br>

- Before the concept of virtualization, the rule of thumb in IT was: “One server = one application.”
- One job per box approach: If a company wanted to run a website, database, email service,etc. they would need separate physical server for each service.
- Causing problems like: high cost, low utilization(many servers stayed at 5-20% usage, wasting CPU memory & storage resources), slow deployment, hard to scale.
<br>

## Hypervisor
- Hypervisor: It is a virtualization layer, that acts as a referee between lab machines & allow each virtual computer to behave independently, like a physical computer.
- Each virtual computer, known as a **Lab Machine (VM)**, acts as an independent system with its own operating system, apps, and settings, even though they all share the same physical hardware underneath. 
- **It is completely isolated from other VMs, i.e. if one breaks, others still continue to work.**
<br>

- It is a special piece of software that:
    - Divides a physical computer into multiple virtual ones.
    - Gives each lab machine its own share of CPU, memory, and storage.
    - Keeps everything isolated and safe.
    - Manages the lifecycle of lab machines (start, stop, pause, clone, delete).
<br>

**Types of Hypervisors**
<br>

- Type 1 hypervisors run directly on the physical hardware, making them fast, efficient, and ideal for servers and professional environments.
- Type 2 hypervisors run within an existing operating system, making them easier to install and ideal for learning, testing, or small setups.
<br>

- Container: A container is a lightweight, isolated environment that runs one application along with everything it needs (libraries, tools, and dependencies). 
- Instead of having its own operating system, it shares the host operating system's kernel, making it fast and resource-efficient.
<br>

- The easiest way to deploy containers in a VM is using Docker. **Docker** is an open-source software platform that simplifies the process of building, deploying, and running applications using containerization.
<br>

- In summary, VMs provide the “full apartment” with maximum separation and flexibility, while containers offer lightweight “rooms” ideal for scalable, fast-deploying applications.

**Conclusion:**
   - Virtualization: Enables a single physical computer to act like multiple separate computers.
   - Hypervisor: The “manager” software that makes and runs the virtual computers.
   - Lab Machine (VM): A whole virtual computer inside the real one, with its own system.
   - Container: A small, isolated box for one app that shares the same system as the host.
   - Container Images: A pre-packed recipe/template used to create containers.
   - Network Ports: Special numbered entry points that apps use to talk over the network.
 <br>

- Key benefits of virtualization are:
     - Cost savings
     - Better resource usage
     - Safe testing for cyber security
     - Faster deployment
     - Flexibility, Portability & Scalability
     - Centralized Management

<br>

## Cloud Computing Fundamentals
- The cloud is built on top of technologies like virtualization and containers. These enable running many applications efficiently on shared infrastructure and quickly creating or changing environments when needed.
- Benefits and characteristics of cloud computing:
     - Scalability: Easily scale up or down as your application's needs change.
     - On-demand self-service: Create or remove servers and storage instantly, without waiting for hardware.
     - Pay only for what you use: You are charged based on usage, not upfront costs.
     - Security: Cloud providers protect the infrastructure with strong security measures.
     - High availability: Applications keep running even if part of the system fails.
     - Global access: Our application can be accessed by users anywhere in the world.
<br>

- The cloud enables IT resources to be flexible, cost-effective, and easier to manage.
<br>

## Types of Cloud:
1. Deployment Types -
     1. Public cloud: Most commonly used. It is used by startups, websites, and global apps because it is affordable, easy to scale, and requires no infrastructure management. Public cloud services are preferable for nearly every use case.
     2. Private Cloud: Used by banks, healthcare, and government organizations because it offers greater control, customization, and compliance for sensitive data.
     3. Hybrid Cloud: Used by companies like e-commerce platforms that need to keep sensitive data private while still scaling publicly during high demand. 
<br>

2. Cloud Service Models -
     1. Infrastructure as a Service (IaaS): Allows to rent basic computing resources such as virtual servers, storage, and networking. Here user is responsible for managing the operating system and application, while the provider manages the physical hardware.
     2. Platform as a Service (PaaS): The cloud provider manages the infrastructure and the operating system. User focus on building, deploying, and running the application without worrying about servers.
     3. Software as a Service (SaaS): Allows to use a complete application over the internet. The provider manages everything, and we access the software through a browser or app, for example, Gmail or Zoom. 

## Major Cloud Vendors
- Well-known cloud providers include:
     1. Microsoft Azure: A strong competitor, especially in enterprise and hybrid cloud environments.
     2. Google Cloud Platform (GCP): Known for powerful data analytics, AI, and machine learning tools.
     3. Alibaba Cloud: A major player in Asia, offering competitive cloud services globally.
     4. IBM Cloud: Focuses on hybrid cloud and AI-driven solutions for businesses.
     5. Oracle Cloud: Focuses on enterprise applications and databases.
<br>

- Each of these vendors offers a range of services, but **AWS remains the most popular due to its vast infrastructure and support for businesses of all sizes.**

## How Companies Are Using the Cloud
1. __Netflix__ runs its entire platform on AWS so it can scale globally, stay online during peak demand, and stream content reliably to millions of users at once.
2. __Spotify__ uses the cloud to handle millions of songs and users, scaling quickly when new music or features are released.
3. **Instagram** relies on the cloud to store massive amounts of photos and videos and deliver them fast to users around the world.
<br>

- These companies use the cloud because it lets them scale easily, reduce costs, stay reliable, and focus on improving their products instead of managing hardware.

## Basic Cloud Terminology
- EC2 (Virtual Computer / Server): EC2 represents a virtual computer in the cloud. Just like a real computer, it has a CPU and memory (RAM) and can run applications. Whenever we add an EC2 instance, we are adding a computer to your environment.
- Instance Type (for example: t2, t3, m5): Instance types describe how powerful the virtual computer is. Some have more CPU and RAM and are therefore more expensive. We choose it based on our needs, keeping in mind that:
- Bigger instances = more power + higher cost
- Minor instances = less power + lower cost



