# PowerShell Advanced System Monitoring
## Important Cmdlets

| Cmdlet                 | Purpose                                       |
| ---------------------- | --------------------------------------------- |
| `Get-Process`          | Shows running processes, CPU and memory usage |
| `Get-Service`          | Shows services and their status               |
| `Get-NetTCPConnection` | Shows active TCP connections                  |
| `Get-FileHash`         | Generates a file hash to verify integrity     |
| `Get-Item -Stream *`   | Displays NTFS Alternate Data Streams (ADS)    |

### 1. `Get-Process`
* Displays currently running processes with details such as **PID, CPU and memory usage**.

```powershell
Get-Process
```

**Sample Output:**

```text
Handles  CPU(s)  Id    ProcessName
-------  ------  --    -----------
67       0.06    2340  AggregatorHost
78       0.02     516  cmd
309      0.52    1524  amazon-ssm-agent
```

### 2. `Get-Service`
* Displays installed services and whether they are **Running, Stopped, or Paused**.

```powershell
Get-Service
```

**Sample Output:**

```text
Status   Name            DisplayName
------   ----            -----------
Stopped  AmazonEC2Launch Amazon EC2Launch
Running  AmazonSSMAgent  Amazon SSM Agent
Running  BFE             Base Filtering Engine
```

### 3. `Get-NetTCPConnection`
* Displays active TCP connections, including **local/remote addresses, ports, connection state and owning process**.
* Useful for **incident response and malware analysis**.

```powershell
Get-NetTCPConnection
```

**Sample Output:**

```text
LocalAddress   LocalPort  RemoteAddress   RemotePort  State
------------   ---------  -------------   ----------  -----
0.0.0.0        3389       0.0.0.0         0           Listen
10.10.178.209  22         10.14.87.60     53523       Established
```

### 4. `Get-FileHash`
* Generates a **SHA256 hash** of a file.
* Useful for checking **file integrity and detecting tampering**.

```powershell
Get-FileHash -Path .\ship-flag.txt
```

**Sample Output:**

```text
Algorithm  Hash                Path
---------  ----                ----
SHA256     54D2EC3C12BF3D...   C:\...\ship-flag.txt
```

### 5. `Get-Item -Stream *`
* Displays **NTFS Alternate Data Streams (ADS)** attached to a file.
* `:$DATA` is the default data stream; other named streams are ADS.

```powershell
Get-Item -Path "C:\House\house_log.txt" -Stream *
```

**Sample Output:**

```text
Stream       Length
------       ------
:$DATA       13
housinginfo  21
```
### Key Point
> These cmdlets are useful for **real-time system monitoring, troubleshooting, incident response, and threat hunting**.

## Scripting
* **Scripting** is writing a series of commands in a text file (script) to **automate tasks**.
* It saves time, reduces errors, and simplifies repetitive or complex tasks.
* PowerShell scripting is important across **cybersecurity roles**.

## Uses in Cybersecurity
* **Blue Team:** Automates log analysis, anomaly detection, IOC extraction, malware analysis, and intrusion detection.
* **Red Team:** Automates system enumeration, remote commands, and attack simulation.
* **System Administrators:** Automates configuration management, integrity checks, security policies, and system monitoring.

## `Invoke-Command`
* Executes commands or scripts on **local or remote computers**.
* Useful for **remote management and automation** across multiple systems.

### Examples
**Run a script on a remote computer:**
```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```
**Run a command on a remote computer:**
```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
```
* `-ComputerName` → specifies the remote computer.
* `-FilePath` → specifies the script to execute.
* `-Credential` → specifies the account used.
* `-ScriptBlock { ... }` → specifies commands to execute remotely.

### Key Point
> **PowerShell scripting automates tasks, while `Invoke-Command` enables command and script execution on remote systems.**
