## Windows Fundamentals

### The Desktop(GUI)
Windows Desktop, the graphical user interface(GUI), is the screen that welcomes user once they log into a Windows machine.
- The login screen is user enters the valid credentials, username & password of pre-existing windows account on the system or Active Directory environment(if it is domain joined machine).

Windows GUI consists of several components that make navigation and system management easier:

Desktop
Start Menu
Search Box (Cortana)
Task View
Taskbar
Toolbars
Notification Area
1. Desktop
The Desktop provides quick access to shortcuts, programs, folders, and files.
- Items can be organized into folders or arranged as desired.
- Right-clicking the desktop opens a context menu for:
    - Changing icon size and arrangement
    - Copying/pasting items
    - Creating folders, shortcuts, and text documents

- Display Settings allows you to change:
   - Screen resolution & orientation
   - Multi-monitor configuration

- Personalize allows you to change:
   - Desktop wallpaper
   - Fonts
   - Themes
   - Color schemes

- Some display options may be disabled during a Remote Desktop session.

2. Start Menu
The Start Menu provides access to installed applications, files, settings, and utilities.It can be opened by clicking the Windows logo.

#### Main Sections

1. Account and System Options
  - User account settings
  - Documents and Pictures folders
  - Settings
  - Lock, sign out, restart, or shut down
  - Remote Desktop disconnect option

2. Applications List
   - Shows recently added applications.
   - Displays installed applications in alphabetical order.
   - Clicking a letter opens an alphabet grid for quick navigation.

3. Tiles
- Provides shortcuts to frequently used applications and utilities.
- Right-clicking a tile allows actions such as:
- Resize
- Unpin from Start
- View properties
- Applications can be added using Pin to Start.

3. Search Box (Cortana)
Used to quickly search for applications, files, settings, and other information on the system.
4. Task View
Allows users to view and switch between open applications and windows.
It also supports managing multiple virtual desktops.
5. Taskbar
- Located at the bottom of the Windows desktop by default.
- Displays currently open applications, folders, and files.
- Pinned applications remain on the taskbar even when closed.
- Hovering over an application icon displays a preview thumbnail and tooltip.
- Right-clicking the taskbar provides options to customize its components and settings.

6. Toolbars
Toolbars provide quick access to frequently used applications, folders, or commands.They can be enabled or disabled through the taskbar's context menu.

7. Notification Area
   - Usually located at the bottom-right corner of the screen.
   - Displays the date and time.
- May also contain icons for:
   - Volume
   - Network/Wi-Fi
   - Other system services
- Icons can be added or removed through Taskbar Settings → Notification Area.

Key Tip

Right-clicking a folder, file, application, or icon generally provides additional information and useful actions related to that item.

# Windows File System – NTFS

## NTFS (New Technology File System)

* **NTFS** is the primary file system used by modern versions of Windows.
* Older Windows file systems include:

  * **FAT16/FAT32** – File Allocation Table
  * **HPFS** – High Performance File System
* FAT is still commonly used in **USB drives and MicroSD cards**, but generally not for Windows system installations.

## Features of NTFS

NTFS is a **journaling file system**, meaning it keeps information in a log that helps automatically recover and repair the file system after a failure.

NTFS provides several advantages over older file systems:

* Supports **files larger than 4 GB**
* Allows specific **permissions** on files and folders
* Supports **file and folder compression**
* Supports **encryption** using **EFS (Encrypting File System)**

The file system of the Windows installation can usually be checked by right-clicking the **C: drive → Properties**.

## NTFS Permissions

NTFS allows administrators to **grant or deny access** to files and folders.

The main permissions are:

* **Full Control** – Complete access to the file/folder
* **Modify** – Allows modification and deletion
* **Read & Execute** – Read and run files/programs
* **List Folder Contents** – View contents of a folder
* **Read** – View files and folder contents
* **Write** – Create or modify files

### Viewing Permissions

1. Right-click the required file or folder.
2. Select **Properties**.
3. Open the **Security** tab.
4. Select a user, computer, or group to view its permissions.

## Alternate Data Streams (ADS)

* **ADS (Alternate Data Streams)** is a feature specific to **NTFS**.
* Every file has at least one data stream called **`$DATA`**.
* ADS allows a file to contain **additional streams of data**.
* Windows File Explorer normally does not display ADS.
* **PowerShell** and third-party tools can be used to view ADS.
* From a security perspective, **malware can use ADS to hide data**.
* ADS also has legitimate uses. For example, files downloaded from the Internet may contain information in ADS identifying their Internet origin.

### Key Points

* **NTFS** = Modern Windows file system.
* **Journaling** = Helps recover from file system failures.
* **NTFS permissions** = Control access to files and folders.
* **EFS** = Provides file encryption.
* **ADS** = Allows additional hidden data streams within NTFS files.
