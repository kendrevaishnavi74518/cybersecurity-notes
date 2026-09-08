#  Firewall & Network Protection


A **firewall** is a security mechanism that controls **network traffic entering and leaving a computer through network ports**.

* It acts like a **security guard** that checks traffic attempting to enter or exit the system.
* It can allow or block network connections based on configured rules.
* **Windows Defender Firewall** helps protect the system from unauthorized network access.

## Windows Firewall Profiles

Windows Firewall provides **three firewall profiles**:

### 1. Domain

* Used when the computer is connected to a network where it can **authenticate with a domain controller**.
* Commonly used in organizational or enterprise networks.

### 2. Private

* A **user-assigned profile** intended for trusted networks.
* Examples include **home or private networks**.

### 3. Public

* Used for **untrusted public networks**.
* Examples include:

  * Public Wi-Fi
  * Coffee shops
  * Airports
  * Other public locations
* It is the **default firewall profile**.

## Firewall Options

When a firewall profile is selected, you can configure options such as:

* **Turn the firewall On/Off**
* **Block all incoming connections**

> **Warning:** Unless you fully understand the consequences, it is recommended to keep **Windows Defender Firewall enabled**.

## Allow an App Through Firewall

* Windows allows specific applications to communicate through the firewall.
* Applications can be permitted on:

  * **Private networks**
  * **Public networks**
* The firewall settings show which applications currently have network access.
* The **Details** option may provide additional information about an application.

## Advanced Settings

* **Advanced Settings** provides detailed firewall configuration options.
* It is intended primarily for **advanced users**.
* Administrators can configure detailed firewall rules and network security settings.

## Command to Open Windows Firewall

Use:

```cmd
WF.msc
```
# App & Browser Control

**App & Browser Control** contains security features that protect Windows users from malicious or potentially unsafe applications, files, and websites.

## Microsoft Defender SmartScreen

**Microsoft Defender SmartScreen** helps protect against:

* **Phishing websites**
* **Malware websites and applications**
* **Potentially malicious downloads**
* Unrecognized applications and files downloaded from the Internet

### SmartScreen Settings

SmartScreen can be configured to:

* **Warn** – Alerts the user about potentially unsafe content.
* **Block** – Prevents the potentially unsafe content from running or being accessed.
* **Off** – Disables SmartScreen protection.

### Check Apps and Files

* SmartScreen checks **unrecognized applications and files downloaded from the web**.
* It helps prevent potentially dangerous files from being executed.

## Exploit Protection

* **Exploit Protection** is built into Windows 10 and Windows Server 2019.
* It provides protection against **exploitation techniques and attacks** targeting applications and the operating system.

> **Warning:** Unless you are completely confident about the changes, it is recommended to keep the **default security settings enabled**.

