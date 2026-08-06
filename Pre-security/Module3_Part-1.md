## OS Introduction

- An operating system (OS) is the core software that coordinates everything happening on a computer. 
```mermaid
graph TD
A[User] -> B[Applications]
B[Applications] -> C[Operating System]
C[Operating System] -> D[Hardware]
```
## System Privilege Layers

1. Kernel space: Locked-down core of OS, kernel manages hardware,memory, CPU & processes. **Has unrestricted access to the system's hardware components, CPU, memory, storage,etc.
2. User space: All std applications run here, these are delibrately prevented from accessing hardware directly. When they want to perform any action, they must make a system call & the kernel does it on their behalf.

## OS Duties

1. Process Management - Creates, schedules, prioritizes & terminates processes. It decides how much time each process gets, makes multi-tasking easy. Ex: opening multiple apps without the laptop getting frozen.

2. Memory Management - Allocates RAM to processes, reclaims RAM when process ends, protects app's memory from processes, uses virtual memory to keep system stable when RAM is low.

3. File System Management - Organizes files, directories, handles naming, paths, file permissions, metadata.

4. User Management - Handles user accounts, authentication, permissions.

5. Device Management - Loads drivers & provides UI. Ex: plugging in new mouse,speakers or printers etc.

## OS Security

- OS, at a basic level handles:
   - Authentication: Verifies user through password or biometrics.
   - Isolation: Prevents processes from using app's memory.
   - Permissions: Controls what each user & app is allowed to r,w or e.
   - System Protection: Protects sytem from unauthorized changes.

## OS Interfaces

Interactions with OS are divided into 2 parts:
1. Graphical User Interface(GUI): The visual part of OS, icons,windows, that lets user interact by clicking or tapping on the screen.

2. Command-Line Interface(CLI): Text-based interface, where user enters commands to control system with precision & speed.

## Real World Operating Systems

1. Desktop

- Windows: The most widely used operating system on personal computers
Windows 10 (end-of-life), Windows 11
- macOS: Apple's desktop OS, known for its polished GUI and integration with other Apple devices
Sonoma (14), Sequoia (15), Tahoe (26)
- Linux: Not a single OS but a family of open-source operating systems called distributions
Ubuntu, Debian, Fedora

2. Server

- Windows: Used in large networks, data centers, and corporate environments
Server 2016, 2019, 2022, 2025
- Linux: The vast majority of web servers, trusted for its reliability and open-source nature
Ubuntu Server, Debian, CentOS, Red Hat
- Unix: Large enterprises, finance, telecom, government
IBM AIX, Oracle Solaris

3. Mobile

- Android: The most widely used mobile OS, which runs on phones, tablets, and smart devices
Android 14 - 16, Manufacturer versions
- iOS: Apple's mobile OS running on iPhones, iPads, and other devices
iOS 17, 18, 26

4. Embedded and IoT Devices

- Embedded Linux: Specialized OS built into devices with dedicated functions
OpenWrt, Ubuntu Core, Yocto Project
- Real-Time OS: Designed for apps where tasks need guaranteed response times (aircraft controls)
FreeRTOS, VxWorks, QNX

5. Virtual and Cloud

- Cloud/VM: Massive data centers that host websites, apps, and streaming services
Ubuntu LTS, Amazon Linux, Rocky Linux
- Container-optimized: Lightweight alternatives to VMs that package just the app and its dependencies
Alpine Linux, Bottlerocket AWS, Flatcar Linux
<br>

- Different devices have different requirements, so they need different operating systems. Each OS is designed for specific goals such as ease of use, security, performance, stability, or power efficiency.
