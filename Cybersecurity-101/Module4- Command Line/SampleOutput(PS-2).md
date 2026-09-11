# PowerShell System & Network Information

## 1. `Get-ComputerInfo`

* Retrieves detailed **OS, hardware, BIOS, and system configuration** information.

```powershell
Get-ComputerInfo
```

**Sample Output:**

```text
WindowsBuildLabEx     : 20348.859.amd64fre
WindowsEditionId      : ServerDatacenter
WindowsInstallationType : Server Core
WindowsProductName    : Windows Server 2022 Datacenter
WindowsCurrentVersion : 6.3
```

---

## 2. `Get-LocalUser`

* Lists **local user accounts**, including username, account status and description.

```powershell
Get-LocalUser
```

**Sample Output:**

```text
Name                  Enabled  Description
----                  -------  -----------
Administrator         True     Built-in account for administering
captain               True     The beloved captain
DefaultAccount        False    A user account managed by the system
Guest                 False    Built-in account for guest access
WDAGUtilityAccount    False    Account used by Windows Defender
```

---

## 3. `Get-NetIPConfiguration`

* Displays network configuration such as **IP address, DNS server, default gateway and network interface**.

```powershell
Get-NetIPConfiguration
```

**Sample Output:**

```text
InterfaceAlias       : Ethernet
InterfaceIndex       : 5
IPv4Address          : 10.10.178.209
IPv4DefaultGateway   : 10.10.0.1
DNSServer            : 10.0.0.2
```

---

## 4. `Get-NetIPAddress`

* Displays details of **all IP addresses** configured on the system.

```powershell
Get-NetIPAddress
```

**Sample Output:**

```text
IPAddress       : 10.10.178.209
InterfaceAlias  : Ethernet
AddressFamily   : IPv4
PrefixLength    : 24
AddressState    : Preferred

IPAddress       : 127.0.0.1
InterfaceAlias  : Loopback Pseudo-Interface 1
AddressFamily   : IPv4
```

## Quick Revision

| Cmdlet                   | Main Use              |
| ------------------------ | --------------------- |
| `Get-ComputerInfo`       | System information    |
| `Get-LocalUser`          | Local users           |
| `Get-NetIPConfiguration` | Network configuration |
| `Get-NetIPAddress`       | IP address details    |
