# Windows Command Prompt – Introduction

## GUI vs CLI
A **GUI (Graphical User Interface)** is generally easier for beginners because it is intuitive and allows users to perform tasks through menus and buttons.

A **CLI (Command-Line Interface)** has a learning curve, but once mastered, it can be **faster and more efficient** for performing repetitive and administrative tasks.

### Advantages of CLI
* **Lower Resource Usage** – Uses fewer system resources than graphics-intensive GUIs, making it suitable for older hardware and resource-limited systems.
* **Automation** – Commands can be combined into **batch files or scripts** to automate repetitive tasks.
* **Remote Management** – CLI tools such as **SSH** allow administrators to manage remote systems efficiently, even over slow networks.

# Basic System Information
## Windows Path
* Windows uses the **Path environment variable** to determine where it searches for executable commands.
* Use the following command to view environment variables, including the Path:
```cmd
set
```
* The line beginning with **`Path=`** shows the directories where Windows searches for commands.

## `ver`
* The `ver` command displays the **Windows operating system version**.
```cmd
ver
```
Example:
```text
Microsoft Windows [Version 10.0.17763.1821]
```

## `systeminfo`
* The `systeminfo` command displays detailed information about the computer system.
* It can provide information about:
  * Operating system
  * System configuration
  * Processor
  * Memory
  * Host name
  * OS version and build
```cmd
systeminfo
```

## Paging Long Output
If a command produces a large amount of output, use the **pipe (`|`)** with `more` to display it page by page.
```cmd
driverquery | more
```
* Press **Spacebar** to view the next page.
* Press **Ctrl + C** to exit.

## Useful Commands
| Command               | Purpose                                          |
| --------------------- | ------------------------------------------------ |
| `set`                 | Displays environment variables, including `Path` |
| `ver`                 | Displays Windows version                         |
| `systeminfo`          | Displays detailed system information             |
| `help`                | Provides help for commands                       |
| `cls`                 | Clears the Command Prompt screen                 |
| `driverquery`         | Displays installed device drivers                |
| `driverquery \| more` | Displays driver information page by page         |





