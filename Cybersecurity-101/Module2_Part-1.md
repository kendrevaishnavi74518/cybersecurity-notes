## Linux Fundamentals
1. whoami - tells who you are on the system.
2. echo - output some specific text is given
3. ls - lists contents in current folder.
4. cd - changes directory, move into folder
5. cat - shows contents of a file.
6. pwd - prints current directory.
7. find - searches files using their names.
    - Syntax: find -name filename
8. grep - searches inside file for text.

## Shell Operators
1. & - Runs commands, but does not wait for it to finish before you can do anything else.
    - Runs in the backgorund, and is helpful for commands that might take a while to complete, or ones that you want to keep running.
2. && - Runs both commands,but waits for 1st command to finish, before the next.
3. (>) - Used to redirect to output, overwrites anything that exists in the file.
4. (>>) - Does same but, adds output to bottom of file instead of overwriting.
