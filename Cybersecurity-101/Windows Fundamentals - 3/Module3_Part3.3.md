## Device Security
Security that comes built into the device.

## Core Isolation
Virtulalization based security is running to protect the core parts of the device.
 
- Memory Integrity: Prevents attacks from isnserting malicious code into high security processes. 
>*Warning*: **Unless you are 100% confident in what you are doing, it is recommended that you leave the default settings.**
#### Security Processor
Security processor, called the trusted platform module (TPM), is providing additional encryption for your device.

- Trusted Platform Module (TPM) technology is designed to provide hardware-based, security-related functions. A TPM chip is a secure crypto-processor that is designed to carry out cryptographic operations. The chip includes multiple physical security mechanisms to make it tamper-resistant, and malicious software is unable to tamper with the security functions of the TPM.

## BitLocker
BitLocker Drive Encryption is a data protection feature that integrates with the operating system and addresses the threats of data theft or exposure from lost, stolen, or inappropriately decommissioned computers.

- BitLocker offers best protection on devices with TPM installed.
-  BitLocker provides the most protection when used with a Trusted Platform Module (TPM) version 1.2 or later. 
- TPM is a hardware component installed in many newer computers by the computer manufacturers. 
- It works with BitLocker to help protect user data and to ensure that a computer has not been tampered with while the system was offline.

# Volume Shadow Copy Service (VSS)
**Volume Shadow Copy Service (VSS)** is a Windows service that creates a **consistent point-in-time copy (snapshot)** of data for backup and recovery purposes.

## Shadow Copies
* Shadow Copies are stored in the **System Volume Information** folder on drives where system protection is enabled.
* VSS allows Windows to maintain restore points and recover system data.

## System Protection
When **System Protection** is enabled, users can perform the following tasks through **Advanced System Settings**:

* **Create a restore point**
* **Perform a system restore**
* **Configure restore settings**
* **Delete restore points**

## Security Importance
* VSS can help recover from **system failures and ransomware attacks**.
* Malware and ransomware may attempt to **delete Shadow Copies/restore points** to prevent recovery.
* If Shadow Copies are deleted and no **offline or off-site backup** exists, recovery from a ransomware attack can become much more difficult.

