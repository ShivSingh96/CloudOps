https://app--wander-wise-ai-ecab249e.base44.app

# Linux for DevOps & Cloud Engineers - Course Outline

## Table of Contents

### I. Beginner Level
1. **Linux Fundamentals**
   - History and Philosophy of Linux
   - Common Distributions (Ubuntu, CentOS, RHEL, Debian)
   - Installation and Virtual Machines

2. **Command Line Basics**
   - Terminal Navigation
   - Basic Commands (ls, cd, pwd, mkdir, rm)
   - File Manipulation (cp, mv, touch)
   - Command History and Tab Completion

3. **File System**
   - Directory Structure (/etc, /var, /home, etc.)
   - File Types and Permissions (chmod, chown)
   - Finding Files (find, locate)
   - Working with Archives (tar, gzip)

4. **Text Processing**
   - Text Editors (vim, nano)
   - File Viewing (cat, less, more)
   - Text Manipulation (grep, sed, awk basics)

5. **Package Management**
   - APT (Debian/Ubuntu)
   - YUM/DNF (RHEL/CentOS)
   - Installing, Updating, Removing Packages

### II. Intermediate Level
1. **Shell Scripting**
   - Bash Scripting Fundamentals
   - Variables and Data Types
   - Control Structures (if, for, while)
   - Functions and Error Handling

2. **User Management**
   - Creating and Managing Users
   - Groups and Permissions
   - Sudo and Privilege Escalation
   - PAM Modules

3. **Process Management**
   - Viewing Processes (ps, top)
   - Job Control (fg, bg, &)
   - Process Priorities (nice)
   - Signals and Killing Processes

4. **System Administration**
   - System Monitoring (htop, iostat, vmstat)
   - Log Management (journalctl, logrotate)
   - Systemd Service Management
   - Scheduling Tasks (cron, systemd timers)

5. **Networking**
   - Network Configuration
   - SSH and Remote Access
   - Firewalls (iptables, firewalld, ufw)
   - DNS Configuration

### III. Advanced Level
1. **Advanced Networking**
   - Network Namespaces
   - Network Troubleshooting (tcpdump, wireshark)
   - Load Balancing
   - VPN Setup

2. **Security Hardening**
   - SELinux/AppArmor
   - Cryptography and Certificates
   - Intrusion Detection
   - Security Scanning and Auditing

3. **Containers and Orchestration**
   - Container Basics on Linux
   - Docker and Podman
   - Kubernetes on Linux
   - Container Security

4. **Infrastructure as Code**
   - Configuration Management (Ansible)
   - Infrastructure Provisioning
   - GitOps Workflows
   - CI/CD Pipeline Integration

5. **Performance Tuning**
   - Kernel Parameter Optimization
   - Resource Limiting (cgroups)
   - I/O Scheduling and Optimization
   - Memory Management

6. **High Availability**
   - Clustering Concepts
   - Load Balancing
   - Automated Failover
   - Distributed Storage

7. **Troubleshooting**
   - Debugging Tools
   - Performance Analysis
   - Crash Analysis
   - Disaster Recovery

8. **Custom Linux**
   - Building Custom Images
   - Kernel Compilation
   - Initramfs Customization
   - Linux From Scratch Concepts

Each section includes hands-on labs and real-world DevOps scenarios to reinforce learning.
# Linux for DevOps & Cloud Engineers - Beginner Level

## Learning Path Overview
This beginner section provides fundamental Linux knowledge essential for DevOps and Cloud Engineers. Each module includes theory, practical examples, and hands-on exercises.

---

## Module 1: Linux Fundamentals

### Learning Objectives
- Understand Linux history and philosophy
- Identify major distributions and their use cases
- Install Linux in various environments

### 1.1 History and Philosophy of Linux
- **Unix Origins**: Birth of UNIX at Bell Labs in 1969
- **GNU Project**: Richard Stallman's free software movement
- **Linux Kernel**: Created by Linus Torvalds in 1991
- **Open Source Model**: Collaborative development and sharing

### 1.2 Common Distributions
- **Ubuntu**: User-friendly, great for beginners
  - Example use case: Development workstations, cloud instances
- **CentOS/RHEL**: Enterprise-focused, stable
  - Example use case: Production servers requiring long-term support
- **Debian**: Highly stable, community-driven
  - Example use case: Infrastructure requiring minimal changes
- **Alpine**: Minimalist, security-focused
  - Example use case: Container base images

### 1.3 Installation Methods
- **Virtual Machine Setup**
  ```bash
  # Using VirtualBox from command line
  VBoxManage createvm --name "UbuntuVM" --ostype Ubuntu_64 --register
  ```
- **Cloud Instances**
  ```bash
  # AWS CLI example to launch EC2 instance
  aws ec2 run-instances --image-id ami-0123456789abcdef0 --instance-type t2.micro
  ```
- **Dual Boot Considerations**
- **WSL for Windows Users**
  ```bash
  # Install WSL2 in PowerShell (Administrator)
  wsl --install
  ```

### Practice Exercise
Set up a Linux virtual machine using VirtualBox or install WSL2 on Windows.

---

## Module 2: Command Line Basics

### Learning Objectives
- Navigate the Linux file system confidently
- Execute basic commands for system interaction
- Understand command structure and options

### 2.1 Terminal Navigation
- **Basic Navigation**
  ```bash
  pwd                 # Print working directory
  ls                  # List files and directories
  ls -la              # List all files with details
  cd /path/to/dir     # Change directory
  cd ..               # Move up one level
  cd ~                # Go to home directory
  ```

### 2.2 Essential Commands
- **File Information**
  ```bash
  file document.txt   # Determine file type
  stat document.txt   # Display file status
  ```
- **Getting Help**
  ```bash
  man ls              # Display manual for ls command
  whatis ls           # Brief description of ls
  ls --help           # Show help for ls command
  ```
- **Command History**
  ```bash
  history             # View command history
  !!                  # Execute last command
  !ssh                # Execute last command starting with "ssh"
  Ctrl+R              # Search command history
  ```

### 2.3 Command Structure
- **Anatomy of a Command**
  ```bash
  command -options arguments
  ls -la /home/user
  ```

### Practice Exercise
Create a directory structure for a project with the following commands:
```bash
mkdir -p ~/projects/my-app/{src,docs,tests}
cd ~/projects/my-app
touch README.md
ls -la
echo "# My Application" > README.md
cat README.md
```

---

## Module 3: File System

### Learning Objectives
- Understand Linux directory structure
- Manage file permissions effectively
- Search and locate files efficiently

### 3.1 Directory Structure
- **Key Directories and Purpose**
  ```
  /bin    - Essential command binaries
  /etc    - System configuration files
  /home   - User home directories
  /var    - Variable data files (logs, etc.)
  /tmp    - Temporary files
  /usr    - User utilities and applications
  /opt    - Optional application software
  ```

### 3.2 File Permissions
- **Understanding Permissions**
  ```bash
  # Format: [type][owner][group][others]
  # Example: -rwxr-xr--
  ```
- **Changing Permissions**
  ```bash
  chmod 755 script.sh     # Set rwx for owner, rx for group and others
  chmod u+x script.sh     # Add execute permission for owner
  chmod go-w file.txt     # Remove write permission for group and others
  ```
- **Changing Ownership**
  ```bash
  chown user:group file.txt    # Change owner and group
  chown -R user:group dir/     # Recursively change ownership
  ```

### 3.3 Finding Files
- **Using find**
  ```bash
  find /home -name "*.log"                     # Find by name
  find /var -type f -size +100M                # Find files larger than 100MB
  find /etc -type f -mtime -7                  # Find files modified in last 7 days
  find . -name "*.txt" -exec grep "error" {} \; # Find and process files
  ```
- **Using locate**
  ```bash
  sudo updatedb                  # Update database
  locate "*.conf"                # Find all .conf files
  ```

### 3.4 Working with Archives
- **Creating Archives**
  ```bash
  tar -czvf archive.tar.gz directory/    # Create gzipped tar
  tar -cjvf archive.tar.bz2 directory/   # Create bzip2 tar
  ```
- **Extracting Archives**
  ```bash
  tar -xzvf archive.tar.gz               # Extract gzipped tar
  tar -xjvf archive.tar.bz2              # Extract bzip2 tar
  ```

### Practice Exercise
Create a backup script that finds all `.log` files in log modified in the last day and archives them:
```bash
#!/bin/bash
today=$(date +%Y-%m-%d)
find /var/log -name "*.log" -mtime -1 -type f -print0 | \
    tar -czvf logs-$today.tar.gz --null -T -
```

---

## Module 4: Text Processing

### Learning Objectives
- Edit text files using command line editors
- View and analyze file content efficiently
- Perform basic text manipulation operations

### 4.1 Text Editors
- **Nano (Beginner-Friendly)**
  ```bash
  nano file.txt                  # Open or create a file
  # Ctrl+O to save, Ctrl+X to exit
  ```
- **Vim (Powerful but Steeper Learning Curve)**
  ```bash
  vim file.txt                   # Open or create a file
  # Press 'i' to enter insert mode
  # ESC to exit insert mode
  # :w to save, :q to quit, :wq to save and quit
  ```
- **Essential Vim Commands**
  ```
  dd - Delete line
  yy - Copy (yank) line
  p  - Paste
  /text - Search for "text"
  :%s/old/new/g - Replace all occurrences
  ```

### 4.2 Viewing Files
- **Display File Contents**
  ```bash
  cat file.txt                  # Display entire file
  head -n 10 file.txt           # Display first 10 lines
  tail -n 20 file.txt           # Display last 20 lines
  tail -f /var/log/syslog       # Follow file in real time
  less file.txt                 # Paginated viewing
  ```

### 4.3 Text Manipulation
- **Grep: Finding Text**
  ```bash
  grep "error" logfile.log              # Find lines containing "error"
  grep -i "warning" logfile.log         # Case-insensitive search
  grep -r "TODO" ./src/                 # Recursive search
  grep -v "debug" logfile.log           # Exclude matches
  grep -A 3 -B 2 "exception" log.txt    # Show context (3 lines after, 2 before)
  ```
- **Basic Sed: Stream Editor**
  ```bash
  sed 's/old/new/' file.txt             # Replace first occurrence on each line
  sed 's/old/new/g' file.txt            # Replace all occurrences
  sed -i 's/old/new/g' file.txt         # Replace in-place
  sed '5d' file.txt                     # Delete line 5
  ```
- **Basic Awk: Text Processing**
  ```bash
  awk '{print $1}' file.txt             # Print first field
  awk -F"," '{print $2}' file.csv       # CSV processing
  awk '/error/ {print}' logfile.log     # Filter lines
  ```

### Practice Exercise
Create a log analyzer to extract and count error messages:
```bash
#!/bin/bash
echo "Error analysis in application.log:"
grep -i "error" application.log | wc -l
echo "Most common errors:"
grep -i "error" application.log | awk -F: '{print $3}' | sort | uniq -c | sort -nr | head -5
```

---

## Module 5: Package Management

### Learning Objectives
- Understand package management concepts
- Install, update, and remove software
- Manage repositories and dependencies

### 5.1 APT (Debian/Ubuntu)
- **Repository Management**
  ```bash
  cat /etc/apt/sources.list             # View repositories
  sudo add-apt-repository ppa:name/ppa   # Add PPA
  sudo apt update                        # Update package lists
  ```
- **Installing Packages**
  ```bash
  sudo apt install package-name          # Install a package
  sudo apt install package1 package2     # Install multiple packages
  sudo apt install package=1.2.3         # Install specific version
  ```
- **Managing Packages**
  ```bash
  apt search keyword                     # Search for packages
  apt show package-name                  # Show package details
  sudo apt upgrade                       # Upgrade all packages
  sudo apt remove package-name           # Remove a package
  sudo apt autoremove                    # Remove unused dependencies
  ```

### 5.2 YUM/DNF (RHEL/CentOS)
- **Repository Management**
  ```bash
  cat /etc/yum.repos.d/example.repo      # View repository config
  sudo dnf config-manager --add-repo URL # Add repository
  sudo dnf repolist                      # List repositories
  ```
- **Installing Packages**
  ```bash
  sudo dnf install package-name          # Install a package
  sudo dnf install package1 package2     # Install multiple packages
  sudo dnf install package-1.2.3         # Install specific version
  ```
- **Managing Packages**
  ```bash
  dnf search keyword                     # Search for packages
  dnf info package-name                  # Show package details
  sudo dnf upgrade                       # Upgrade all packages
  sudo dnf remove package-name           # Remove a package
  sudo dnf autoremove                    # Remove unused dependencies
  ```

### 5.3 Managing Software from Source
- **Building from Source**
  ```bash
  wget https://example.com/source-code.tar.gz
  tar -xzvf source-code.tar.gz
  cd source-code
  ./configure
  make
  sudo make install
  ```

### Practice Exercise
Create a script to automate system updates:
```bash
#!/bin/bash
# System update script

# Detect OS
if [ -f /etc/debian_version ]; then
    echo "Debian/Ubuntu detected - using APT"
    sudo apt update
    sudo apt upgrade -y
    sudo apt autoremove -y
elif [ -f /etc/redhat-release ]; then
    echo "RHEL/CentOS detected - using DNF"
    sudo dnf update -y
    sudo dnf autoremove -y
else
    echo "Unsupported OS"
    exit 1
fi

echo "System updated successfully"
```

---

## Beginner Level Projects

### Project 1: System Information Dashboard
Create a Bash script that displays system information including:
- CPU information and load
- Memory usage
- Disk space
- Running processes
- Network interfaces

### Project 2: Log Monitoring Tool
Build a script that:
- Monitors system logs for errors
- Sends email notifications for critical issues
- Rotates and archives old logs

### Project 3: Automated Backup Solution
Develop a backup script that:
- Creates compressed backups of specified directories
- Maintains a configurable number of backups
- Logs backup activities
- Can be scheduled via cron

These projects combine the beginner concepts into practical tools that are relevant for DevOps and Cloud engineering work.
