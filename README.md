# Linux-learning
# Ubuntu Linux Commands

## Basic File and Directory Commands
- `ls`: Lists files and directories in the current directory.
- `cd [directory]`: Changes the current directory to the specified one.
- `pwd`: Prints the current working directory path.
- `mkdir [directory]`: Creates a new directory.
- `rmdir [directory]`: Removes an empty directory.
- `rm [file]`: Deletes a file.
- `rm -r [directory]`: Deletes a directory and its contents recursively.
- `cp [source] [destination]`: Copies files or directories.
- `mv [source] [destination]`: Moves or renames files or directories.
- `touch [file]`: Creates an empty file or updates the timestamp of an existing file.
- `cat [file]`: Displays the content of a file.
- `nano [file]`: Opens a file in the Nano text editor.
- `vim [file]`: Opens a file in the Vim text editor.
- `find [directory] -name [filename]`: Searches for files in a directory hierarchy.

## System Information Commands
- `uname -a`: Displays detailed information about the system.
- `df -h`: Shows disk space usage.
- `du -h [directory]`: Displays disk usage of a directory and its contents.
- `free -h`: Displays memory and swap usage.
- `top`: Displays real-time system processes and resource usage.
- `htop`: Enhanced version of `top` (requires installation).
- `ps aux`: Displays all running processes.
- `lscpu`: Shows CPU architecture information.
- `lsblk`: Lists information about all available block devices (disks).
- `uptime`: Shows how long the system has been running.

## File Permissions and Ownership
- `chmod [permissions] [file]`: Changes file permissions.
  - Example: `chmod 755 [file]` sets read, write, and execute permissions for the owner, and read and execute permissions for others.
- `chown [owner]:[group] [file]`: Changes the owner and group of a file or directory.
  - Example: `chown user:group [file]`
- `chgrp [group] [file]`: Changes the group ownership of a file or directory.

## Networking Commands
- `ifconfig`: Displays or configures network interface parameters (use `ip` in newer systems).
- `ip a`: Displays all network interfaces and their IP addresses.
- `ping [hostname]`: Sends ICMP echo requests to check network connectivity.
- `netstat -tuln`: Lists open ports and active network connections.
- `curl [URL]`: Transfers data from or to a server.
- `wget [URL]`: Downloads files from the web.
- `ssh [user]@[hostname]`: Connects to a remote server via SSH.
- `scp [source] [destination]`: Copies files between hosts over SSH.

## Package Management Commands
- `apt-get update`: Updates the package lists for upgrades.
- `apt-get upgrade`: Upgrades all installed packages to their latest version.
- `apt-get install [package]`: Installs a package.
- `apt-get remove [package]`: Removes a package.
- `apt-get autoremove`: Removes unnecessary packages that were automatically installed.
- `dpkg -i [package.deb]`: Installs a `.deb` package.
- `apt-cache search [package]`: Searches for a package in the repository.

## User Management Commands
- `adduser [username]`: Adds a new user to the system.
- `passwd [username]`: Changes the password for a user.
- `deluser [username]`: Removes a user from the system.
- `usermod -aG [group] [username]`: Adds a user to a group.
- `whoami`: Displays the current logged-in user.
- `groups [username]`: Shows the groups to which a user belongs.

## Process Management Commands
- `kill [PID]`: Terminates a process by its process ID.
- `killall [process_name]`: Terminates all processes with the specified name.
- `bg [job]`: Resumes a suspended job in the background.
- `fg [job]`: Brings a background job to the foreground.
- `jobs`: Lists all background jobs.

## File Compression Commands
- `tar -cvf [archive.tar] [directory]`: Creates a tar archive.
- `tar -xvf [archive.tar]`: Extracts a tar archive.
- `tar -czvf [archive.tar.gz] [directory]`: Creates a compressed tar.gz archive.
- `tar -xzvf [archive.tar.gz]`: Extracts a tar.gz archive.
- `zip [archive.zip] [file]`: Compresses files into a zip archive.
- `unzip [archive.zip]`: Extracts a zip archive.

## Disk Management Commands
- `fdisk -l`: Lists all partitions on all disks.
- `mkfs.ext4 /dev/[partition]`: Formats a partition with the ext4 filesystem.
- `mount /dev/[partition] /mnt`: Mounts a partition to a directory.
- `umount /mnt`: Unmounts a partition from a directory.

## Search and Filter Commands
- `grep [pattern] [file]`: Searches for a specific pattern in a file.
- `grep -r [pattern] [directory]`: Recursively searches for a pattern in a directory.
- `awk '{print $1}' [file]`: Extracts specific columns from a file.
- `sed 's/[pattern]/[replacement]/g' [file]`: Replaces patterns in a file.

## System Management Commands
- `shutdown -h now`: Shuts down the system immediately.
- `reboot`: Reboots the system.
- `systemctl start [service]`: Starts a system service.
- `systemctl stop [service]`: Stops a system service.
- `systemctl restart [service]`: Restarts a system service.
- `systemctl status [service]`: Checks the status of a service.
- `systemctl enable [service]`: Enables a service to start at boot.
- `systemctl disable [service]`: Disables a service from starting at boot.

## Text Manipulation Commands
- `cat [file]`: Concatenates and displays the content of files.
- `head -n [number] [file]`: Displays the first `n` lines of a file.
- `tail -n [number] [file]`: Displays the last `n` lines of a file.
- `sort [file]`: Sorts the contents of a file.
- `uniq [file]`: Filters out repeated lines in a file.
- `wc -l [file]`: Counts the number of lines in a file.

## Advanced Commands
- `crontab -e`: Edits the cron jobs for the current user.
- `alias [name]='[command]'`: Creates an alias for a command.
- `chmod +x [script.sh]`: Makes a shell script executable.
- `./[script.sh]`: Runs an executable script.

==========================================================================
# Ubuntu User Management Guide

This guide provides a detailed overview of user management in Ubuntu, including commands and explanations for creating, modifying, and managing users and groups.

## 1. Creating a New User

To create a new user in Ubuntu, use the `adduser` command. This will prompt you to set a password and enter additional information for the new user.

```bash
sudo adduser <username>
```

Example:
```bash
sudo adduser johndoe
```

This command creates a new user named `johndoe` and sets up a home directory at `/home/johndoe`.

## 2. Assigning a User to a Group

To add a user to a specific group, use the `usermod` command with the `-aG` option. This allows the user to retain membership in other groups while being added to the new group.

```bash
sudo usermod -aG <groupname> <username>
```

Example:
```bash
sudo usermod -aG sudo johndoe
```

This adds `johndoe` to the `sudo` group, granting administrative privileges.

## 3. Setting or Changing a User's Password

To set or change a user's password, use the `passwd` command.

```bash
sudo passwd <username>
```

Example:
```bash
sudo passwd johndoe
```

This sets or changes the password for the user `johndoe`.

## 4. Deleting a User

To delete a user from the system, use the `deluser` command. By default, this does not remove the user's home directory.

```bash
sudo deluser <username>
```

Example:
```bash
sudo deluser johndoe
```

To delete a user and their home directory:

```bash
sudo deluser --remove-home <username>
```

Example:
```bash
sudo deluser --remove-home johndoe
```

## 5. Viewing User Information

To view a user's ID (UID), group ID (GID), and groups they belong to, use the `id` command.

```bash
id <username>
```

Example:
```bash
id johndoe
```

To list all users on the system, use:

```bash
cat /etc/passwd
```

## 6. Switching Between Users

To switch to another user account, use the `su` (substitute user) command.

```bash
su - <username>
```

Example:
```bash
su - johndoe
```

To execute a single command as another user:

```bash
sudo -u <username> <command>
```

Example:
```bash
sudo -u johndoe ls /home/johndoe
```

## 7. Locking and Unlocking a User Account

To lock a user account, preventing them from logging in, use the following command:

```bash
sudo usermod -L <username>
```

Example:
```bash
sudo usermod -L johndoe
```

To unlock a user account:

```bash
sudo usermod -U <username>
```

Example:
```bash
sudo usermod -U johndoe
```

## 8. Adding and Managing Groups

To create a new group, use the `addgroup` command:

```bash
sudo addgroup <groupname>
```

Example:
```bash
sudo addgroup developers
```

To delete a group:

```bash
sudo delgroup <groupname>
```

Example:
```bash
sudo delgroup developers
```

To list the groups a user belongs to:

```bash
groups <username>
```

Example:
```bash
groups johndoe
```

## 9. Setting User Expiry Date

To set an account expiry date for a user:

```bash
sudo chage -E <YYYY-MM-DD> <username>
```

Example:
```bash
sudo chage -E 2024-12-31 johndoe
```

To view account expiry information:

```bash
sudo chage -l <username>
```

Example:
```bash
sudo chage -l johndoe
```

## 10. Changing a User’s Shell

To change the default shell for a user:

```bash
sudo chsh -s <shell> <username>
```

Example:
```bash
sudo chsh -s /bin/zsh johndoe
```

This sets Zsh as the default shell for `johndoe`.

## 11. Temporary User Privileges (sudo)

To run a command as the root user:

```bash
sudo <command>
```

Example:
```bash
sudo apt update
```

To grant a user sudo privileges:

```bash
sudo usermod -aG sudo <username>
```

Example:
```bash
sudo usermod -aG sudo johndoe
```

## 12. Monitoring User Activity

To see who is currently logged into the system:

```bash
who
```

To see the last login times for users:

```bash
last <username>
```

To monitor real-time login attempts:

```bash
tail -f /var/log/auth.log
```

---

This guide covers essential commands and tasks for managing users in Ubuntu. Proper user management is critical for system security and efficient administration.













