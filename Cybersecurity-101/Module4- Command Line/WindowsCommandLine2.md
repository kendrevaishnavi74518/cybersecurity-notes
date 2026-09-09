## File & Disk Management

#### Working with Directories

### `cd`
* Displays the **current directory** when used without parameters.
* Used to move to another directory.
```cmd
cd
cd target_directory
```

* `cd ..` moves **one level up**.
```cmd
cd ..
```

### `dir`
* Displays files and subdirectories in the current directory.

```cmd
dir
```

Useful options:

* `dir /a` → Displays **hidden and system files**.
* `dir /s` → Displays files in the current directory **and all subdirectories**.

### `tree`

* Displays directories and subdirectories in a **tree-like visual structure**.

```cmd
tree
```

### `mkdir`

* Creates a new directory.
* `mkdir` = **Make Directory**

```cmd
mkdir directory_name
```

### `rmdir`

* Deletes a directory.
* `rmdir` = **Remove Directory**

```cmd
rmdir directory_name
```

## Working with Files

### `type`

* Displays the contents of a text file directly in the Command Prompt.

```cmd
type file.txt
```

### `more`

* Displays a long text file **page by page**.
* Press **Spacebar** for the next page.
* Press **Enter** to move one line.

```cmd
more file.txt
```

### `copy`

* Copies a file from one location to another.

```cmd
copy source.txt destination.txt
```

### `move`

* Moves a file from one location to another.

```cmd
move file.txt ..
```

### `del` / `erase`

* Deletes a file.

```cmd
del file.txt
```

or

```cmd
erase file.txt
```

## Wildcard `*`

* The `*` wildcard can represent **multiple files**.
* It is useful for performing an operation on all files matching a pattern.

Example:

```cmd
copy *.md C:\Markdown
```

This copies **all `.md` files** to `C:\Markdown`.

### Quick Command Reference

| Command         | Purpose                           |
| --------------- | --------------------------------- |
| `cd`            | Show/change current directory     |
| `cd ..`         | Move up one directory             |
| `dir`           | List files and directories        |
| `dir /a`        | Show hidden/system files          |
| `dir /s`        | List files in subdirectories      |
| `tree`          | Display directory structure       |
| `mkdir`         | Create a directory                |
| `rmdir`         | Delete a directory                |
| `type`          | Display file contents             |
| `more`          | View long text files page by page |
| `copy`          | Copy files                        |
| `move`          | Move files                        |
| `del` / `erase` | Delete files                      |
| `*`             | Wildcard for multiple files       |

### Task & Process Management
* The `tasklist` command displays all **currently running processes** on a Windows system.
* It provides information such as:

  * Process name
  * **PID (Process ID)**
  * Session name
  * Session number
  * Memory usage

```cmd
tasklist
```
Since the output can be very long, filters can be used.

## Filtering Processes
Use `tasklist /?` to view available filters and command options.

To find a specific process by its image name:
```cmd
tasklist /FI "imagename eq sshd.exe"
```

* `/FI` → Applies a filter.
* `imagename eq` → Filters where the image name equals the specified process.
* `sshd.exe` → Process being searched for.

## `taskkill`
* The `taskkill` command is used to **terminate a running process**.
* A process can be terminated using its **PID**.
```cmd
taskkill /PID 4567
```
Here, `4567` is the PID of the process to terminate.

### Extra Commands
1. chkdsk: checks the file system and disk volumes for errors and bad sectors.
2. driverquery: displays a list of installed device drivers.
3. sfc /scannow: scans system files for corruption and repairs them if possible.
-  It is equally important to know that /? can be used with most commands to display a help page.