## What is PowerShell
PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework.
* It combines a command-line interface and a scripting language built on the .NET framework. 
* Unlike older text-based command-line tools, PowerShell is object-oriented, which means it can handle complex data types and interact with system components more effectively. 
* Initially exclusive to Windows, PowerShell has lately expanded to support macOS and Linux, making it a versatile option for IT professionals across different operating systems.

### Brief History of PowerShell
* **PowerShell** was developed by Microsoft to overcome the limitations of traditional Windows command-line tools such as `cmd.exe` and batch files.
* In the early 2000s, complex enterprise environments required better **automation, scripting, and system administration**.
* **Jeffrey Snover** introduced an **object-oriented approach** to Windows administration, inspired by the differences between Windows and Unix.
* Unlike Unix tools that mainly process **text**, PowerShell works with **structured objects** and integrates closely with the **.NET framework** and Windows APIs.
* PowerShell was first released in **2006**.
* In **2016**, Microsoft released **PowerShell Core**, an **open-source and cross-platform** version supporting:
  * Windows
  * macOS
  * Linux

### The Power in PowerShell

#### Objects
An **object** represents an item containing:
* **Properties** – characteristics/data of the object.
* **Methods** – actions/functions that the object can perform.

**Example:** A car object may have properties such as `Color`, `Model`, and `FuelLevel`, and methods such as `Drive()` and `Refuel()`.
In PowerShell, objects can represent:
* Files and their properties
* User accounts
* Processes
* System information

### Objects vs Text
| Traditional Command Shell   | PowerShell                          |
| --------------------------- | ----------------------------------- |
| Primarily processes text    | Processes objects                   |
| Output is plain text        | Output contains structured data     |
| Often requires text parsing | Properties can be directly accessed |
| Limited data manipulation   | Powerful and flexible manipulation  |

### Cmdlets
* PowerShell commands are called **cmdlets**.
* Cmdlets return **objects** rather than plain text.
* Since objects retain their **properties and methods**, they can be easily passed to other commands and manipulated without manually parsing text.

### Key Point
> **The main power of PowerShell comes from its object-oriented approach, which makes Windows administration, automation, and data manipulation more powerful and flexible.**

## Launching PowerShell
* PowerShell can be launched through:
  * Start Menu
  * `Win + R` → `powershell`
  * File Explorer address bar
  * Task Manager → Run new task
  * Command Prompt → type `powershell`
* The `PS` prompt indicates that PowerShell is running.

## Verb-Noun Syntax
* PowerShell commands are called **cmdlets**.
* Cmdlets follow the **Verb-Noun** naming convention.
* **Verb** = action, **Noun** = object.
* Examples:

  * `Get-Content` → retrieves file content.
  * `Set-Location` → changes the current directory.

## Important Cmdlets
| Cmdlet           | Purpose                                        |
| ---------------- | ---------------------------------------------- |
| `Get-Command`    | Lists available commands                       |
| `Get-Help`       | Provides help, syntax and examples for cmdlets |
| `Get-Alias`      | Lists PowerShell command aliases               |
| `Find-Module`    | Searches for modules in online repositories    |
| `Install-Module` | Installs a PowerShell module                   |

### Useful Examples
```powershell
Get-Command -CommandType "Function"
Get-Help Get-Date
Get-Help Get-Date -examples
Get-Alias
```

## Aliases
* **Aliases** are shortcuts/alternative names for cmdlets.
* Examples:
  * `dir` → `Get-ChildItem`
  * `cd` → `Set-Location`
  * `cat` → `Get-Content`
  * `clear` → `Clear-Host`

## Modules
* **Modules** are collections of PowerShell cmdlets.
* `Find-Module` searches online repositories such as **PowerShell Gallery**.
* `Install-Module` downloads and installs a module.

### Key Point
> **PowerShell uses object-based cmdlets with a consistent Verb-Noun syntax, making system administration and automation easier.**

