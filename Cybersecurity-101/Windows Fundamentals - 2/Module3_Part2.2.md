# System Information (`msinfo32`)
**System Information (`msinfo32`)** is a Windows tool that collects and displays detailed information about the computer's **hardware, system components, and software environment**. It is useful for **diagnosing computer issues**.

## System Summary
The **System Summary** provides general technical specifications, such as:
* Processor brand and model
* System components
* Operating system information
* Other basic system details

Information is organized into three main sections:
1. **Hardware Resources**
2. **Components**
3. **Software Environment**

## 1. Hardware Resources
* Displays detailed information about hardware resources used by the system.
* Includes technical information useful mainly for administrators and advanced users.

## 2. Components
* Provides information about specific **hardware devices** installed on the computer.
* Examples include:
  * **Display**
  * **Input**
  * Other hardware components

## 3. Software Environment
* Displays information about software included with Windows and installed applications.
* Also contains information such as:
  * **Environment Variables**
  * **Network Connections**
  * Other software-related configuration details

## Environment Variables
* **Environment variables** store information about the operating system environment.
* They are used by Windows and applications to locate resources and determine system settings.
* Examples of information stored include:
  * Operating system path
  * Number of processors
  * Location of temporary folders
  * Windows installation directory

### Example
`WINDIR` contains the location of the Windows installation directory.
Environment variables can be accessed through:
**Control Panel → System and Security → System → Advanced system settings → Environment Variables**
or
**Settings → System → About → Advanced system settings → Environment Variables**

## Search Feature
* `msinfo32` includes a **search bar** at the bottom.
* It can be used to quickly find specific information.
* For example:
  **Components → Search → `IP address`**