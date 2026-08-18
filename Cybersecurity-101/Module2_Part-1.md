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

## SSH
Secure Shell or SSH is a protocol between devices in an encrypted form. Using cryptography, any input we send in human readable format is encrypted for travelling over a network, where it is unencrypted once it reaches remote machine.
- It allows us to remotely execute commands on another device remotely. Any data sent between the devices is encrypted when sent over a network such as Internet.

## Filesystem Interaction
1. touch - creates file
2. mkdir - creates folder
3. cp - copy a file or folder
    - Syntax: cp source destination  
4. mv - move a file or folder
5. rm - removes a file or folder
    - rm -R directoryname - to remove directory recursively.
6. file - determines type of file.

## Permisssion Commands
1. ls -lh: Gives vertical list
2. su: Used for switching between users
3. -l or --login: Used to establish a new session on system.

### File Permissions
r = read, w = write, x = execute
- Each permission has numeric value r = 4, w = 2, x = 1
- To calculate numeric values, add all values to together.
- rwxrwxrwx: 1st 3 = owner, next 3 = group, last 3 = others
- chmod 777 - Gives all permissions
- chmod 600 - Only owner can read & write
- Syntax: chmod permissions_no filename

### Common Directories
1. /etc - One of the most imp root directories on the system. The etc folder(short for etcetera) is commonplace location to store system files used by OS.
    - **passwd** & **shadow** files, special for Linux as they show how system stores passwords for each user in encrypted formatting, **sha512**.
2. /var - Short for variable, it is one of the main root folders found on Linux install. It stores data that is frequently accessed or written by services & apps are written here(/var/log),or other data that is not necessarily associated with a specific user (i.e databases).
3. /root - Actually home for the "root" system user.
4. /tmp - Unique folder found in Linux install, short for "temporary", it is volatile & is used to store data that is needed to be accessed once or twice. Once computer is restarted,contents of this folder are cleared out.