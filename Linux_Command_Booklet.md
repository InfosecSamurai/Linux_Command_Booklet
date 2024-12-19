# The Ultimate Linux Command Booklet

This booklet provides a comprehensive overview of essential and advanced Linux commands, structured for easy reference.

## Table of Contents
1. [File Operations](#file-operations)
    - [Creating Files](#creating-files)
    - [Displaying Files](#displaying-files)
    - [File Comparison](#file-comparison)
    - [Creating Symbolic Links](#creating-symbolic-links)
    - [Finding Duplicate Files](#finding-duplicate-files)
2. [Directory Operations](#directory-operations)
3. [Viewing System Information](#viewing-system-information)
4. [File Permissions](#file-permissions)
5. [Searching for Files and Text](#searching-for-files-and-text)
6. [Process Management](#process-management)
7. [Networking Commands](#networking-commands)
8. [Package Management Commands](#package-management-commands)
9. [Disk Usage Commands](#disk-usage-commands)
10. [User Management](#user-management)
11. [System Monitoring Tools](#system-monitoring-tools)
12. [Text Processing Commands](#text-processing-commands)
13. [Archiving and Compression](#archiving-and-compression)
14. [System Shutdown and Restart](#system-shutdown-and-restart)
15. [Miscellaneous Commands](#miscellaneous-commands)
16. [Custom Commands](#custom-commands)

---

## File Operations

### Creating Files

- **Touch**: Create an empty file.
    ```bash
    touch filename.txt
    ```

- **Echo**: Create a file with content.
    ```bash
    echo "Hello, World!" > filename.txt
    ```

- **Nano/Vim**: Create and edit files in the terminal.
    ```bash
    nano filename.txt
    vim filename.txt
    ```

### Displaying Files

- **Cat**: Display the content of a file.
    ```bash
    cat filename.txt
    ```

- **Less**: View the content of a file one page at a time.
    ```bash
    less filename.txt
    ```

- **More**: View the content of a file one screen at a time.
    ```bash
    more filename.txt
    ```

- **Head**: Display the first ten lines of a file.
    ```bash
    head filename.txt
    ```

- **Tail**: Display the last ten lines of a file.
    ```bash
    tail filename.txt
    ```

### File Comparison

- **Diff**: Compare two files line by line.
    ```bash
    diff file1.txt file2.txt
    ```

- **Meld**: A visual diff and merge tool (requires installation).
    ```bash
    meld file1.txt file2.txt
    ```

### Creating Symbolic Links

- **Ln -s**: Create a symbolic link.
    ```bash
    ln -s target_file link_name
    ```

### Finding Duplicate Files

- **Fdupes**: Find and delete duplicate files.
    ```bash
    fdupes -r /path/to/directory
    ```

---

## Directory Operations

### Creating Directories

- **Mkdir**: Create a new directory.
    ```bash
    mkdir new_directory
    ```

### Displaying Directories

- **Ls**: List directory contents.
    ```bash
    ls -l
    ```

- **Tree**: Display directory structure in a tree-like format (requires installation).
    ```bash
    tree /path/to/directory
    ```

### Navigating Directories

- **Cd**: Change directory.
    ```bash
    cd /path/to/directory
    ```

### Removing Directories

- **Rmdir**: Remove an empty directory.
    ```bash
    rmdir directory_name
    ```

- **Rm -r**: Remove a directory and its contents.
    ```bash
    rm -r directory_name
    ```

- **Chmod -R**: Change permissions recursively.
    ```bash
    chmod -R 755 directory_name
    ```

- **Chown -R**: Change ownership recursively.
    ```bash
    chown -R user:group directory_name
    ```

---

## Viewing System Information

### System Information

- **Uname**: Display system information.
    ```bash
    uname -a
    ```

- **Lshw**: Display detailed information on the hardware configuration (requires sudo).
    ```bash
    sudo lshw
    ```

- **Lscpu**: Display detailed CPU architecture information.
    ```bash
    lscpu
    ```

### System Load and Usage

- **Top**: Display active processes.
    ```bash
    top
    ```

- **Htop**: Interactive process viewer (requires installation).
    ```bash
    htop
    ```

- **Vmstat**: Report virtual memory statistics.
    ```bash
    vmstat 5
    ```

### Memory and Disk Usage

- **Free**: Show memory usage.
    ```bash
    free -h
    ```

- **Df**: Display disk space usage.
    ```bash
    df -h
    ```

---

## File Permissions

### Changing Permissions and Ownership

- **Chmod**: Change file permissions.
    ```bash
    chmod 755 filename
    ```

- **Chown**: Change file owner and group.
    ```bash
    chown user:group filename
    ```

### Understanding Permissions

- **Getting Permission Information**: View permissions of files.
    ```bash
    ls -l filename
    ```

- **Umask**: Set default file permissions for new files.
    ```bash
    umask 022
    ```

---

## Searching for Files and Text

### Finding Files

- **Find**: Search for files in a directory hierarchy.
    ```bash
    find /path -name "filename"
    ```

- **Locate**: Find files by name (must be updated regularly using `updatedb`).
    ```bash
    locate filename
    ```

### Searching for Text

- **Grep**: Search for text within files.
    ```bash
    grep "search_term" filename
    ```

- **Grep with Regex**: Use regular expressions to search text.
    ```bash
    grep -E "regex_pattern" filename
    ```

### Finding Files with Different Criteria

- **Find by Type**: Find files of a specific type (e.g., directories).
    ```bash
    find /path -type d -name "directory_name"
    ```

- **Find by Size**: Find files based on size.
    ```bash
    find /path -size +100M
    ```

---

## Process Management

### Managing Processes

- **Ps**: Display information about running processes.
    ```bash
    ps aux
    ```

- **Kill**: Terminate a process.
    ```bash
    kill PID
    ```

- **Killall**: Kill processes by name.
    ```bash
    killall process_name
    ```

### Managing Background Processes

- **Jobs**: List active jobs in the current shell.
    ```bash
    jobs
    ```

- **Fg**: Bring a job to the foreground.
    ```bash
    fg %1  # Replace 1 with job number
    ```

- **Bg**: Run a job in the background.
    ```bash
    bg %1  # Replace 1 with job number
    ```

---

## Networking Commands

### Networking Basics

- **Ping**: Check connectivity to a network host.
    ```bash
    ping example.com
    ```

- **Ifconfig**: Display network configuration (deprecated; use `ip a`).
    ```bash
    ifconfig
    ```

- **Ip**: Show or manipulate routing, devices, and tunnels.
    ```bash
    ip addr show  # Display IP addresses
    ```

### Network Connections

- **Netstat**: Display network connections.
    ```bash
    netstat -tuln
    ```

- **Tracert**: Trace route to a network host.
    ```bash
    traceroute example.com
    ```

### Downloading Files

- **Curl**: Download files or make network requests.
    ```bash
    curl -O http://example.com/file.txt
    ```

- **Wget**: Non-interactive network downloader (requires installation).
    ```bash
    wget http://example.com/file.txt
    ```

---

## Package Management Commands

### Debian/Ubuntu

- **Apt-get**: Install a package.
    ```bash
    sudo apt-get install package_name
    ```

- **Apt-cache**: Search for packages.
    ```bash
    apt-cache search package_name
    ```

### RedHat/CentOS

- **Yum**: Install a package.
    ```bash
    sudo yum install package_name
    ```

- **Dnf**: Next-generation package manager for RPM (replacement for yum).
    ```bash
    sudo dnf install package_name
    ```

---

## Disk Usage Commands

### Checking Disk Usage

- **Df**: Report file system disk space usage.
    ```bash
    df -h
    ```

- **Df -i**: Report inode usage.
    ```bash
    df -i
    ```

- **Du**: Estimate file and directory space usage.
    ```bash
    du -sh directory_name
    ```

### Disk Partitioning

- **Parted**: Command-line utility for managing disk partitions.
    ```bash
    sudo parted /dev/sda
    ```

---

## User Management

### Adding and Managing Users

- **Adduser**: Add a new user.
    ```bash
    sudo adduser username
    ```

- **Usermod**: Modify a user account.
    ```bash
    sudo usermod -aG groupname username
    ```

### Changing User Passwords

- **Passwd**: Change a user's password.
    ```bash
    sudo passwd username
    ```

### Displaying User Information

- **Whoami**: Display the current user.
    ```bash
    whoami
    ```

---

## System Monitoring Tools

### Monitoring System Resources

- **Glances**: Cross-platform system monitoring tool (requires installation).
    ```bash
    glances
    ```

### Log Monitoring

- **Tail -f**: Monitor logs in real-time.
    ```bash
    tail -f /var/log/syslog
    ```

---

## Text Processing Commands

### Text Manipulation

- **Cut**: Remove sections from each line of files.
    ```bash
    cut -d ':' -f 1 /etc/passwd
    ```

- **Sort**: Sort lines of text files.
    ```bash
    sort file.txt
    ```

- **Uniq**: Report or omit repeated lines.
    ```bash
    uniq -c sorted_file.txt
    ```

- **Awk**: A powerful programming language for pattern scanning.
    ```bash
    awk '{print $1}' file.txt
    ```

---

## Archiving and Compression

### Creating Archives

- **Tar**: Archive files.
    ```bash
    tar -cvf archive.tar /path/to/directory/
    ```

- **Zip**: Zip files and directories (requires installation).
    ```bash
    zip -r archive.zip directory_name
    ```

### Extracting Archives

- **Tar Extract**: Extract tar files.
    ```bash
    tar -xvf archive.tar
    ```

- **Unzip**: Extract zip files.
    ```bash
    unzip archive.zip
    ```

---

## System Shutdown and Restart

- **Shutdown**: Shut down the system.
    ```bash
    sudo shutdown -h now
    ```

- **Reboot**: Restart the system.
    ```bash
    sudo reboot
    ```

- **Halt**: Stop the system without powering it off.
    ```bash
    sudo halt
    ```

---

## Miscellaneous Commands

### Environment Variables

- **Printenv**: Print all environment variables.
    ```bash
    printenv
    ```

- **Export**: Set an environment variable.
    ```bash
    export VARIABLE_NAME=value
    ```

### File Redirecting and Pipes

- **Redirection**: Redirect output to a file.
    ```bash
    command > output.txt   # Overwrite
    command >> output.txt  # Append
    ```

- **Pipes**: Use the output of one command as the input of another.
    ```bash
    command1 | command2
    ```

### System Information

- **Hostname**: Display or set the system's hostname.
    ```bash
    hostname
    ```

- **Date**: Display or set the system date and time.
    ```bash
    date
    ```

---

## Custom Commands

### Combining Commands

- **Using Semicolons**: Run multiple commands in sequence.
    ```bash
    cd /path/to/directory; ls -l; echo "Done"
    ```

- **Using Pipes**: Combine commands for filtering output.
    ```bash
    ps aux | grep bash | awk '{print $2}'
    ```

- **Chaining Commands with `&&`**: Only run the next command if the previous one succeeds.
    ```bash
    mkdir new_dir && cd new_dir
    ```

- **Using Subshells**: Execute commands in a subshell to capture output.
    ```bash
    result=$(ls)
    echo "Files: $result"
    ```

---

## Conclusion
This extended cheat sheet aims to provide an exhaustive reference for Linux commands. If you're looking for more advanced usage, always refer to the man pages (e.g., `man command_name`) for details on options and capabilities.
