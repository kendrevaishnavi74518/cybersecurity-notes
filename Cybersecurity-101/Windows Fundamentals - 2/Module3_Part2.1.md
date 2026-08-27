# System Configuration (MSConfig)
* **System Configuration (`MSConfig`)** is a Windows utility mainly used for **advanced troubleshooting and diagnosing startup problems**.
* It requires **local Administrator rights** to open.
* It can be launched from the **Start Menu** or by using `msconfig` in the Run dialog.

## MSConfig Tabs

### 1. General
Controls which devices and services Windows loads during startup.

Options:
* **Normal startup** – Loads all configured devices and services.
* **Diagnostic startup** – Loads only basic devices and services.
* **Selective startup** – Allows specific startup items to be selected.

### 2. Boot
* Used to configure various **operating system boot options**.

### 3. Services
* Lists all services configured on the system, whether **running or stopped**.
* A **service** is a special type of application that runs in the background.

### 4. Startup
* Used to view startup-related configuration.
* In modern Windows, **Task Manager (`taskmgr`)** is used to enable or disable startup applications.
* MSConfig is **not primarily a startup management tool**.

**Windows Server Note:**
* Windows Server may not show startup applications in Task Manager or MSConfig.
* User-level startup items can be checked using:
  `Win + R → shell:startup`
* The Startup folder contains shortcuts/executables configured to run automatically when a user logs in.

### 5. Tools

* Contains various Windows utilities for further system configuration and troubleshooting.
* Each tool has a description and a **Selected command**.
* Tools can be launched using:

  * **Launch** button
  * Run dialog
  * Command Prompt

# Advanced System Settings

* **Advanced System Settings** provides additional options for controlling **system performance and recovery**.
* Search for **View advanced system settings** to open the **System Properties** window.

## Page File

* Windows uses a **page file** as additional virtual memory when physical RAM becomes full.
* It helps reduce slowdowns and application crashes caused by insufficient RAM.
* Page file settings can be accessed through:
  **Advanced → Performance → Settings → Advanced**

Information available includes:
* Drive where the page file is stored
* Initial size
* Maximum size
* Whether Windows manages the size automatically

## Startup and Recovery

* Windows can create a **crash dump file** when a critical system error occurs, such as a **Blue Screen of Death (BSOD)**.
* Crash dumps help administrators and analysts determine what caused the crash.
* Settings can be accessed through:
  **Advanced → Startup and Recovery → Settings**

### Crash Dump Types

The **Write debugging information** option determines the type of crash dump created:
* **Automatic memory dump**
* **Kernel memory dump**
* **Small memory dump (256 KB)**
* **Complete memory dump**
* **None**

The selected option determines **how much information Windows saves when a system crash occurs**.

## User Account Control
The UAC settings can be changed or even turned off entirely (not recommended). You can move the slider to see how the setting will change the UAC settings and Microsoft's stance on the setting.

- This slider has four security levels, each of which controls how Windows alerts you when apps or users try to make changes at the system level. You can find the current level by looking at the position of the slider in the User Account Control settings window. They fall into four standard categories as explained below:

- Always notify: This is the highest security. Windows notifies you whenever any apps or you yourself try to make changes, and the desktop dims (Secure Desktop).
- Notify for apps: Windows notifies only when apps try to make changes, but not when you change Windows settings. This option is enabled by default.
- Notify without dimming: Same as above (Notify for apps), but this time the screen does not dim. 
- Never notify: Notifications are turned off. Windows won’t warn you about any changes made by you or any apps. 

# Computer Management (`compmgmt`)
**Computer Management** is a Windows administrative utility with three primary sections:
1. **System Tools**
2. **Storage**
3. **Services and Applications**

## 1. System Tools
### Task Scheduler
* **Task Scheduler** allows users to create and manage tasks that Windows performs automatically.
* Tasks can:
  * Run applications or scripts
  * Run at login or logout
  * Run at a scheduled time, such as every 5 minutes
  * Run once at a specific time
* **Task Scheduler Library** displays existing scheduled tasks and their triggers/actions.
* A basic task can be created using **Create Basic Task**.

### Event Viewer
* **Event Viewer** displays events that have occurred on the computer.
* Event logs act as an **audit trail** for:
  * Troubleshooting problems
  * Investigating system activity
  * Reviewing actions performed on the system
* It has three main panes:
  * **Left:** Event log hierarchy
  * **Middle:** Event details/summary
  * **Right:** Available actions
* Standard logs are available under **Windows Logs**.

### Shared Folders
* Displays folders and resources shared over the network.
* **Shares** shows available shared folders, including default administrative shares such as `C$` and `ADMIN$`.
* **Sessions** shows users currently connected to shared resources.
* **Open Files** shows files/folders currently being accessed by connected users.
* Permissions can be viewed through the resource's properties.

### Local Users and Groups
* Provides management of local **users and groups**.
* This is the same utility available through `lusrmgr.msc`.

### Performance Monitor (`perfmon`)
* **Performance Monitor** displays system performance data.
* Data can be viewed:
  * In real time
  * From previously recorded log files
* Useful for diagnosing performance problems on local or remote systems.

### Device Manager
* **Device Manager** allows users to view and configure hardware devices.
* Hardware devices can be managed or disabled using this utility.

## 2. Storage
### Disk Management
**Disk Management** is used for advanced storage configuration.
Common tasks include:
* Setting up a new drive
* Extending a partition
* Shrinking a partition
* Assigning or changing a drive letter, such as `E:`

**Note:** Windows Server may provide additional utilities that are not normally available in Windows client versions.

## 3. Services and Applications
### Services
* A **service** is a special type of application that runs in the background.
* The Services section displays services and their current status.
* Right-clicking a service and selecting **Properties** provides details such as:
  * Service name
  * Executable path
  * Startup type
  * Other configuration details

### Service Startup Types
* **Automatic** – Service starts automatically when Windows boots.
* **Manual** – Service starts when triggered by another process or user.
* **Disabled** – Service is prevented from running.

### WMI Control
* **WMI (Windows Management Instrumentation)** allows scripting languages such as **VBScript** and **PowerShell** to manage Windows systems locally or remotely.
* Microsoft also provided a command-line interface called **WMIC**.
* **WMIC is deprecated** in Windows 10 version 21H1, with **PowerShell** being the preferred replacement for WMI management.


