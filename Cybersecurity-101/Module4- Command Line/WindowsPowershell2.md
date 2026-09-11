# Navigating File System & Working with Files
## Important Cmdlets

| Cmdlet          | Purpose                     | CMD Equivalent |
| --------------- | --------------------------- | -------------- |
| `Get-ChildItem` | Lists files and directories | `dir`          |
| `Set-Location`  | Changes current directory   | `cd`           |
| `New-Item`      | Creates files/directories   | `mkdir`        |
| `Remove-Item`   | Removes files/directories   | `del`, `rmdir` |
| `Copy-Item`     | Copies files/directories    | `copy`         |
| `Move-Item`     | Moves files/directories     | `move`         |
| `Get-Content`   | Displays file contents      | `type`         |

### Key Syntax
```powershell
Get-ChildItem -Path "path"
Set-Location -Path "path"
New-Item -Path "path" -ItemType "File"
New-Item -Path "path" -ItemType "Directory"
Remove-Item -Path "path"
Copy-Item -Path "source" -Destination "destination"
Move-Item -Path "source" -Destination "destination"
Get-Content -Path "file.txt"
```

### Key Points
* `Get-ChildItem` lists the contents of the current directory if no path is specified.
* `New-Item` can create **both files and directories** using `-ItemType`.
* `Remove-Item` can remove **both files and directories**.
* `Copy-Item` and `Move-Item` work with **files and directories**.
* `Get-Content` reads and displays the contents of a file.

### Piping, Filtering & Sorting data
* **Piping (`|`)** sends the output of one command as input to another command.
* PowerShell pipes **objects**, not just text.
* Objects retain their **properties and methods**, allowing powerful data manipulation.

### Important Cmdlets

| Cmdlet          | Purpose                                       |
| --------------- | --------------------------------------------- |
| `Sort-Object`   | Sorts objects by a specified property         |
| `Where-Object`  | Filters objects based on conditions           |
| `Select-Object` | Selects specific properties or limits results |
| `Select-String` | Searches for text patterns inside files       |

### Examples

```powershell
Get-ChildItem | Sort-Object Length
```
Sorts files by size.

```powershell
Get-ChildItem | Where-Object -Property "Extension" -eq ".txt"
```
Lists only `.txt` files.

```powershell
Get-ChildItem | Select-Object Name,Length
```
Displays only the `Name` and `Length` properties.

```powershell
Get-ChildItem | Sort-Object Length -Descending | Select-Object -First 1
```
Displays the **largest file**.

```powershell
Select-String -Path ".\captain-hat.txt" -Pattern "hat"
```
Searches for a specific text pattern in a file.

## Comparison Operators

| Operator | Meaning                     |
| -------- | --------------------------- |
| `-eq`    | Equal to                    |
| `-ne`    | Not equal to                |
| `-gt`    | Greater than                |
| `-ge`    | Greater than or equal to    |
| `-lt`    | Less than                   |
| `-le`    | Less than or equal to       |
| `-like`  | Matches a specified pattern |

### Key Point
> **PowerShell piping enables multiple cmdlets to be combined, allowing objects to be sorted, filtered, selected, and searched efficiently.**

