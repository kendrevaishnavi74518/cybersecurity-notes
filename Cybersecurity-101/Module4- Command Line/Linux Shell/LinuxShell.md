# Basic Linux Commands
* **Bash (Bourne Again Shell)** is the default shell for many Linux distributions.

## Important Commands
| Command | Purpose                                      | Example                   |
| ------- | -------------------------------------------- | ------------------------- |
| `pwd`   | Displays the current working directory       | `pwd`                     |
| `cd`    | Changes the current directory                | `cd Desktop`              |
| `ls`    | Lists contents of a directory                | `ls`                      |
| `cat`   | Displays file contents                       | `cat filename.txt`        |
| `grep`  | Searches for a word or pattern inside a file | `grep "THM" filename.txt` |

# Linux Shells

* Linux supports **multiple shells**, each with different features.
* Check the current shell:
```bash
echo $SHELL
```
* List available shells:
```bash
cat /etc/shells
```
* Switch to another shell:
```bash
zsh
```
* Permanently change the default shell:
```bash
chsh -s /usr/bin/zsh
```

### 1. Bash – Bourne Again Shell
* Default shell for most Linux distributions.
* Widely used and supports **scripting**.
* Provides **Tab completion** and **command history**.
* Previous commands can be accessed using **↑/↓ arrows** or `history`.

### 2. Fish – Friendly Interactive Shell
* Focuses on **user-friendliness**.
* Simple syntax suitable for beginners.
* Provides **auto spell correction**.
* Has built-in **syntax highlighting**.
* Supports customization, scripting, tab completion and history.

### 3. Zsh – Z Shell
* Modern shell with advanced features.
* Provides **advanced tab completion** and scripting.
* Supports **auto spell correction**.
* Highly customizable.
* Supports command history and plugins.

## Quick Comparison
| Feature             | Bash      | Fish     | Zsh                 |
| ------------------- | --------- | -------- | ------------------- |
| Scripting           | Extensive | Limited  | Excellent           |
| Tab Completion      | Basic     | Advanced | Advanced/extendable |
| Customization       | Basic     | Good     | Advanced            |
| User Friendly       | Moderate  | High     | High                |
| Syntax Highlighting | No        | Built-in | Via plugins         |

### Key Point
> **Bash is widely used, Fish focuses on ease of use, and Zsh provides advanced customization and features.**

## Shell Scripting & Components
* A **shell script** is a file containing multiple commands executed automatically.
* It helps **automate repetitive tasks**, save time, and reduce errors.
* Bash scripts normally use the **`.sh`** extension.

## Shebang
* The first line specifies the interpreter:
```bash
#!/bin/bash
```

## Variables
* Variables store values that can be reused in a script.
* `read` takes user input and stores it in a variable.
* `$variable` accesses the stored value.

```bash
echo "What's your name?"
read name
echo "Welcome, $name"
```

## Execute a Script

Give execution permission:
```bash
chmod +x script.sh
```

Run the script:
```bash
./script.sh
```
* `./` tells the shell to execute the script from the **current directory**.

## Loops
* Loops repeat a set of commands multiple times.
```bash
for i in {1..10};
do
    echo $i
done
```
* `do` → starts the loop body.
* `done` → ends the loop.

## Conditional Statements
* `if-else` executes code based on whether a condition is true or false.
```bash
if [ "$name" = "Stewart" ]; then
    echo "Authorized"
else
    echo "Not authorized"
fi
```
* `if` → starts the condition.
* `else` → executes when the condition is false.
* `fi` → ends the condition.

## Comments
* Comments explain code and **do not affect execution**.
* In Bash, comments begin with `#`.
```bash
# This is a comment
```

