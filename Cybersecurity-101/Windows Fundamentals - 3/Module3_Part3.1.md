# Windows Update
**Windows Update** is a Microsoft service that provides updates for the Windows operating system and other Microsoft products, such as **Microsoft Defender**.

## Purpose of Windows Update
Windows Updates provide:
* **Security updates** – Fix security vulnerabilities.
* **Feature enhancements** – Add or improve features.
* **Patches** – Fix bugs and system issues.
* Updates for other Microsoft products.

## Patch Tuesday
* Major Windows security updates are typically released on the **second Tuesday of every month**.
* This is known as **Patch Tuesday**.
* Critical or urgent security updates **do not have to wait** until Patch Tuesday; Microsoft can release them immediately when necessary.

## Accessing Windows Update
Windows Update can be accessed through:

**Settings → Windows Update**

It can also be opened using the Run dialog or Command Prompt with:
```cmd
control /name Microsoft.WindowsUpdate
```
## Windows Update and Security
* Windows updates are important for keeping systems **secure and up to date**.
* Users may postpone updates temporarily, but updates should not be ignored indefinitely.
* Some updates require a **system restart** to complete installation.
* Windows provides options to **schedule the required restart**.

## Windows Security
Windows Security is the home to manage the tools that protect the device & data.

- Windows Security provides several protection areas that help secure a Windows system.

- Protection Areas
   1. Virus & Threat Protection - Protects the system against viruses, malware, and other threats.
   2. Firewall & Network Protection - Helps protect the computer from unauthorized network connections.
   3. App & Browser Control - Provides security controls for applications and web browsing.
   4. Device Security - Provides security features that protect the device and its hardware.

### Security Status Icons
Windows Security uses different colors to indicate the system's security status:

🟢 Green – Device is sufficiently protected; no recommended action is required.


🟡 Yellow – A security recommendation needs to be reviewed.


🔴 Red – A warning indicates that immediate attention is required.

#### Opening Windows Security
* Click Open Windows Security to access the security dashboard.
* The appearance may vary depending on the Windows edition.

# Virus & Threat Protection
**Virus & Threat Protection** is a Windows Security feature that protects the system against viruses, malware, and other security threats.

- It is divided into two main sections:
    - 1. **Current Threats**
    - 2. **Virus & Threat Protection Settings**

## 1. Current Threats

### Scan Options
* **Quick Scan** – Checks commonly targeted folders and locations where threats are usually found.
* **Full Scan** – Checks all files and running programs on the hard drive. It can take a long time to complete.
* **Custom Scan** – Allows the user to select specific files or locations to scan.

### Threat History
* **Last Scan** – Shows information about the most recent Windows Defender Antivirus scan.
* **Quarantined Threats** – Threats that have been isolated and prevented from running on the device.
* **Allowed Threats** – Items identified as threats but manually allowed by the user.

> **Warning:** Only allow an identified threat if you are completely certain that the item is safe.

## 2. Virus & Threat Protection Settings

### Manage Settings
* **Real-time Protection** – Continuously detects and blocks malware from installing or running.
* **Cloud-delivered Protection** – Provides faster and improved protection using the latest threat information from the cloud.
* **Automatic Sample Submission** – Sends sample files to Microsoft to help identify potential threats.
* **Controlled Folder Access** – Protects important files and folders from unauthorized changes by malicious or unknown applications. Only trusted/approved applications can modify protected folders.
* **Exclusions** – Allows specific files or folders to be excluded from antivirus scanning, which can help reduce false positives.
* **Notifications** – Provides important notifications about the security and health of the device.

> **Warning:** Excluded files or folders are not scanned by Defender and could contain threats. Exclusions should only be used when necessary and when the item is known to be safe.

## Virus & Threat Protection Updates
* **Check for Updates** allows users to manually update Microsoft Defender Antivirus security definitions.
* Keeping security definitions updated helps Defender detect the latest threats.

## Ransomware Protection
* **Controlled Folder Access** is an important ransomware protection feature.
* It prevents unauthorized applications from modifying protected files and folders.
* Controlled Folder Access requires **Real-time Protection** to be enabled.

## On-Demand Scanning
* A specific file or folder can be scanned manually.
* **Right-click the file/folder → Scan with Microsoft Defender**.

