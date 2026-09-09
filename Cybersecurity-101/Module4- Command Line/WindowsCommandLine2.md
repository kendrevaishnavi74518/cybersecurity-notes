## File & Disk MAnagement
s

## Working with Directories

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
