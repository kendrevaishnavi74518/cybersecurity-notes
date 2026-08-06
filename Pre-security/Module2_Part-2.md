## Virtualisation Basics
<br>

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

