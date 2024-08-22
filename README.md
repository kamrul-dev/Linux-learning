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
