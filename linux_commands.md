# Linux Commands A Primer

A Primer for commonly used Linux commands.

- `man [command]`: Displays the manual page for the specified command.
- `info [command]`: Some Distro favor this command over `man`. Displays detailed information about a command, including its options and usage.
- `[command] --help`: Displays a brief help message for a command, including its options.

## File Blobs and Directories

In Linux, files and directories are organized in a hierarchical structure known as the filesystem. The top-level directory is called the root directory, denoted by a forward slash (`/`). All other files and directories are contained within this root directory. Directories can contain files as well as other directories (subdirectories). Each file and directory has associated metadata, including permissions, ownership, and timestamps.

### File Command

The `file` command is used to determine the type of a file. It examines the file's content and provides information about its format. For example:
- `file myfile.txt`: This command will output something like "ASCII text" if `myfile.txt` is a plain text file.
- `file image.png`: This command will output something like "PNG image data" if `image.png` is a PNG image file.    
- `file script.sh`: This command will output something like "Bourne-Again shell script" if `script.sh` is a shell script.
- `file binary.exe`: This command will output something like "ELF 64-bit LSB executable" if `binary.exe` is a compiled executable file.

### Stat Command

The `stat` command is used to display detailed information about a file or directory, including its size, permissions, ownership, and timestamps. For example:
- `stat myfile.txt`: This command will display information such as file size, access permissions, owner, group, and timestamps for `myfile.txt`.
- `stat /home/user`: This command will display similar information for the `/home/user` directory.

Example:
```bash
$ stat foo.txt
  File: foo.txt
  Size: 0               Blocks: 0          IO Block: 4096   regular empty file
Device: 43h/67d Inode: 33495522229276840  Links: 1
Access: (0777/-rwxrwxrwx)  Uid: ( 1000/    pete)   Gid: ( 1000/    pete)
Access: 2025-11-19 16:22:09.251326900 +0900
Modify: 2025-11-19 16:22:09.251326900 +0900
Change: 2025-11-19 16:22:09.251326900 +0900
 Birth: -
```

## Basic Commands

- `ls`: Lists files and directories in the current directory.
- `ls -al`: Lists all files and directories with detailed information, including hidden files.
- `cd [directory]`: Changes the current directory to the specified directory.
- `pwd`: Prints the current working directory.
- `cp [source] [destination]`: Copies files or directories from source to destination.
- `mv [source] [destination]`: Moves or renames files or directories.
- `rm [file]`: Removes (deletes) the specified file.
- `rm -r [directory]`: Removes a directory and its contents recursively.
- `mkdir [directory]`: Creates a new directory.
- `rmdir [directory]`: Removes an empty directory.
- `touch [file]`: Creates a new empty file or updates the timestamp of an existing file.
- `chmod [permissions] [file]`: Changes the permissions of a file or directory using octal notation.
- `chmod +x [file]`: Changes the permissions of a file to executable.
- `chown [user]:[group] [file]`: Changes the ownership of a file or directory.

## File Viewing and Editing

- `cat [file]`: Displays the contents of a file.
- `less [file]`: Views the contents of a file one page at a time.
- `more [file]`: Similar to `less`, but with fewer features.
- `head [file]`: Displays the first 10 lines of a file.
- `tail [file]`: Displays the last 10 lines of a file.
- `nano [file]`: Opens a file in the nano text editor.
- `vim [file]`: Opens a file in the [vim](vim_usage.md) text editor.
- `grep [pattern] [file]`: Searches for a pattern in a file and displays matching lines.
- `find [directory] -iname [filename]`: Searches for files by case insensitive name in a specified directory.

## System Information

- `top`: Displays real-time system information, including running processes and resource usage.
- `htop`: An enhanced version of `top` with a more user-friendly interface (may need to be installed).
- `df -h`: Displays disk space usage in a human-readable format.
- `du -h [directory]`: Displays the disk usage of a directory and its contents in a human-readable format.
- `free -h`: Displays memory usage in a human-readable format.
- `uname -a`: Displays detailed information about the system and kernel.
- `uptime`: Displays how long the system has been running along with load averages.
- `ps -aux`: Displays a list of all running processes.
- `ps -afew`: Displays a detailed list of all running processes.
- `kill [PID]`: Terminates a process with the specified Process ID (PID).

## LS Commands

- `lscpu` : Displays detailed information about the CPU architecture.
- `lsblk` : Lists information about all available or the specified block devices.
- `lsusb` : Lists all USB devices connected to the system.


## SUDO Command

The `sudo` command stands for "superuser do" and allows a permitted user to execute a command as the superuser or another user, as specified by the security policy. It is commonly used to perform administrative tasks that require elevated privileges.

- `sudo [command]`: Executes a command with superuser (root) privileges. You may be prompted to enter your password.
- `sudo lshw`: Displays detailed information about the hardware configuration of the system.
- `sudo fdisk -l`: Lists all disk partitions and their details (requires superuser privileges).

## Networking

- `ping [hostname or IP]`: Sends ICMP echo requests to test network connectivity.
- `ifconfig`: Displays network interface configuration (may need to be installed).
- `ip addr`: Displays IP address and network interface information.
- `netstat -tuan`: Displays active network connections and listening ports.
- `ssh [user]@[hostname or IP]`: Connects to a remote machine via SSH.
- `scp [source] [user]@[hostname or IP]:[destination]`: Securely copies files between local and remote machines.
- `wget [URL]`: Downloads files from the web.
- `curl [URL]`: Transfers data from or to a server using various protocols. 

## Package Management (Debian/Ubuntu)

- `sudo apt update`: Updates the package index.
- `sudo apt upgrade`: Upgrades all installed packages to their latest versions.
- `sudo apt install [package]`: Installs a new package.
- `sudo apt remove [package]`: Removes an installed package.
- `sudo apt autoremove`: Removes unused packages that were automatically installed to satisfy dependencies.

## File Permissions

- `ls -l`: Lists files and directories with detailed information, including permissions.

### Understanding File Permissions

File permissions in Linux are represented by a string of 10 characters, such as `-rwxr-xr--`. The first character indicates the file type (e.g., `-` for a regular file, `d` for a directory). The next nine characters are divided into three groups of three, representing the permissions for the owner, group, and others, respectively. Each group consists of three characters: read (`r`), write (`w`), and execute (`x`). A dash (`-`) indicates that the permission is not granted.

### Changing File Permissions

File permissions can be changed using the `chmod` command. Permissions can be set using symbolic notation (e.g., `u`, `g`, `o`, `a` for user, group, others, all) or octal notation (e.g., `7` for read, write, execute; `6` for read, write; `5` for read, execute; etc.). For example:
- `chmod u+x file.txt`: Adds execute permission for the owner of the file.
- `chmod 755 file.txt`: Sets permissions to read, write, and execute for the owner, and read and execute for group and others.

### Changing File Ownership

File ownership can be changed using the `chown` command. You can specify the new owner and group for a file or directory. For example:
- `chown user:group file.txt`: Changes the owner to `user` and the group to `group`.
- `chown user file.txt`: Changes only the owner to `user`, keeping the group unchanged.

## Becoming the Root User

To perform administrative tasks that require elevated privileges, you can switch to the root user using the `su` command or execute commands with `sudo`.

- `sudo su -`: Switches to the root user account. You will be prompted to enter the root password.
- `exit`: Exits the root user session and returns to the previous user.

## More to come soon
