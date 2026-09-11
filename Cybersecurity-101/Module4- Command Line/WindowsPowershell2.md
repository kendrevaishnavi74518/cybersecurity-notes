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
