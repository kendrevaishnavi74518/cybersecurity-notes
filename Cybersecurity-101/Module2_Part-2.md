## Automation
Crontab is one of the processes that is started during boot,which is responsible for facilitating & managing cron jobs. A crontab is simply a special file with formatting recognised by cron process to execute each line step-by-step.
- It requires 6 specific values:
   - MIN - What minute to execute at
   - HOUR - What hour to execute at
   - DOM - What day of month to execute at
   - MON - What month of year to execute at
   - DOW - What day of week to execute at
   - CMD - Command to be executed
- Crontabs can be edited by using crontab -e, where we select an editor.
- If we do not wish to provide a value for that specific field, i.e. we don't care what month, day, or year it is executed -- only that it is executed every 12 hours, we simply just place an asterisk(*).

### Packages & Software Repos
Developers submit software to an "apt" repository, if approved it gets released worldwide. Two of the most redeeming features of Linux shine to light here: User accessibility and the merit of open source tools.

- When using the ls command on a Ubuntu 20.04 Linux machine, these files serve as the gateway/registry. 

- OS vendors will maintain their own repositories, you can also add community repositories to your list! This allows you to extend the capabilities of your OS.Additional repositories can be added by using the add-apt-repositorycommand or by listing another provider.

### MAnaging Repos
We use apt command to install software onto Ubuntu system.The apt command is a part of the package management software also named apt. Apt contains a whole suite of tools that allows us to manage the packages and sources of our software, and to install or remove software at the same time.
- One method of adding repositories is to use the add-apt-repository. We can install software through the use of package installers such as dpkg, the benefits of apt means that whenever we update our system -- the repository that contains the pieces of software that we add also gets checked for updates.
- When adding software, the integrity of what we download is guaranteed by the use of what is called GPG (Gnu Privacy Guard) keys.These keys are essentially a safety check from the developers.If the keys do not match up to what your system trusts and what the developers used, then the software will not be downloaded.
Add GPG key
     ↓
Add repository
     ↓
sudo apt update
     ↓
sudo apt install <package>
     ↓
sudo apt remove <package>   (when needed)
     ↓
Remove repository            (when no longer needed)

## Logs
Located in the /var/log directory, these files and folders contain logging information for applications and services running on your system. The Operating System  (OS) has become pretty good at automatically managing these logs in a process that is known as "rotating".
- There are 2 types of log files: access & error log
- There are,logs that store information about how the OS is running itself and actions that are performed by users, such as authentication attempts.