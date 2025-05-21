# 🐧 Linux Engineer Hands-On Journey

Welcome to my public GitHub portfolio where I document my learning journey as a **Linux Engineer**. Each section includes screenshots, explanations, and commands I've used during my hands-on labs. This is a living document, updated regularly as I grow.

---

## 🔧 Virtualization Setup

### ✅ Tools Installed

- **VirtualBox**  
  VirtualBox is one of the most commonly used hypervisors for running Linux OS in a virtual environment.

<p align="center">
  <img src="https://github.com/user-attachments/assets/43a70421-6881-4689-a034-ead81b4563d7" width="250"/>
  <img src="https://github.com/user-attachments/assets/956e4ab0-375c-4761-958a-5a93ab570cec" width="250"/>
</p>

---

- **VMware Workstation (Optional)**  
  Alternative to VirtualBox, used for running virtual machines with more advanced features.

**📋 Requirements:**

- Windows 10 or later (64-bit)
- CPU with virtualization support (Intel VT-x / AMD-V)
- 4GB RAM or more

**🔧 Installation Steps:**

1. Download VMware Workstation Player/Pro  
   👉 [VMware Download Link](https://www.vmware.com/go/getworkstation)
2. Run the installer and accept license terms.
3. Choose default settings or customize features.
4. Restart your computer after installation.

<p align="center">
  <img src="https://github.com/user-attachments/assets/10ff9abf-7021-4d73-9a4e-0a583fa65a69" width="300"/>
</p>

---

### ✅ Ubuntu Installation

- Created a virtual machine and installed **Ubuntu 24.04.2 LTS**

<p align="center">
  <img src="https://github.com/user-attachments/assets/7489c7c9-1e09-452a-9671-ca454e199613" width="250"/>
  <img src="https://github.com/user-attachments/assets/9074be7a-1f1e-49b9-91dd-44c9411fb16c" width="250"/>
  <img src="https://github.com/user-attachments/assets/ed18ebf6-d6d0-4dea-a9e1-76dfee6f8f06" width="250"/>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/dfdabcf0-1ce3-42dc-b1c3-ea193896e257" width="250"/>
  <img src="https://github.com/user-attachments/assets/c480e013-d10d-4d11-9cc0-ed6eeda106d8" width="250"/>
  <img src="https://github.com/user-attachments/assets/7e9a6c9f-37c6-4448-a803-bd8d519e7984" width="250"/>
</p>

---

## 📸 Taking Snapshots (Best Practice)

Snapshots provide a critical **restore point** before making risky system changes. They help maintain a clean rollback path in case something breaks during updates or configuration.

**🛠️ How I Took My Snapshot:**

1. Click on `Machine` → `Take Snapshot`
2. Name the snapshot
3. Add a useful description, like:

> **"System update - cron job setup before 8:30 AM"**

<p align="center">
  <img src="https://github.com/user-attachments/assets/fcea1684-ab4e-44ea-a00e-35886c3b72c7" width="250"/>
  <img src="https://github.com/user-attachments/assets/86172c02-e742-4862-a294-a95e83605460" width="250"/>
  <img src="https://github.com/user-attachments/assets/a258e2a2-93af-4423-8fde-fab24860fd1e" width="250"/>
</p>

---

## 📁 Linux Filesystem & Navigation

### ✅ Topics Covered

- Linux Filesystem Structure
- Navigation with `cd`, `ls`, `pwd`
  ![image](https://github.com/user-attachments/assets/33ff045c-968e-40ca-b9a4-407af303aafd)


- Absolute vs Relative Paths
- Creating & Removing Files/Folders
- File Types and Search Tools (`find`, `locate`)
- File Compression & Archiving

---

### 🔤 Sample Commands

```bash
# File Navigation
ls -al /etc                   # List all files in /etc
cd /home/user                 # Change to user directory
mkdir projects                # Create a folder
rm -rf old_backup             # Delete a folder

# File Searching
find / -name "*.conf"         # Find all .conf files

# --- Compressing with gzip ---
gzip filename.txt             # Compress to 'filename.txt.gz'
gunzip filename.txt.gz        # Decompress to 'filename.txt'

# --- Compressing with bzip2 ---
bzip2 filename.txt            # Compress to 'filename.txt.bz2'
bunzip2 filename.txt.bz2      # Decompress to 'filename.txt'

# --- Compressing with xz ---
xz filename.txt               # Compress to 'filename.txt.xz'
unxz filename.txt.xz          # Decompress to 'filename.txt'

# --- Creating and Extracting tar Archives ---
tar -cvf archive.tar myfolder/        # Create .tar archive (no compression)
tar -xvf archive.tar                  # Extract .tar archive

# --- tar.gz Archives ---
tar -czvf archive.tar.gz myfolder/   # Create gzip-compressed tar
tar -xzvf archive.tar.gz             # Extract gzip-compressed tar

# --- tar.bz2 Archives ---
tar -cjvf archive.tar.bz2 myfolder/  # Create bzip2-compressed tar
tar -xjvf archive.tar.bz2            # Extract bzip2-compressed tar

# --- Working with zip files ---
zip archive.zip file1.txt file2.txt          # Zip multiple files
zip -r archive.zip folder_name/              # Recursively zip a folder
unzip archive.zip                            # Extract zip
unzip archive.zip -d target_directory/       # Extract to specific directory
unzip -l archive.zip                         # List contents of zip
Files and Permissions
````
## 📁 Linux Files and Directory Permissions (Letters)

Linux permissions are represented by letters:

r = read

w = write

x = execute
````
ls -l
# -rw-r--r-- 1 user group 0 May 13 08:30 file.txt
chmod u+x script.sh     # Add execute permission to the user
chmod g-w file.txt      # Remove write from group
chmod o+r file.txt      # Add read for others
````
## 🔢 Files and Directory Permissions (Numeric)
Each permission has a value: r = 4, w = 2, x = 1
````
chmod 755 script.sh     # rwxr-xr-x
chmod 644 file.txt      # rw-r--r--
````
👥 File Ownership Commands
Check ownership and change ownership
````
ls -l
chown newuser file.txt         # Change owner
chown newuser:newgroup file.txt # Change owner and group
````
## Access Control List (ACL)
ACL provides more fine-grained permission control.
Enable ACL on filesystem:
````mount -o remount,acl / ````
Set ACL:
````setfacl -m u:john:rwx file.txt````
````getfacl file.txt````
## 🧭 Navigation & Productivity 🆘 Help Commands
````
man chmod
chmod --help
info chmod
````
## ⌨️ TAB Completion & History
Use TAB to auto-complete paths and commands.

Press ↑ (Up arrow) to navigate command history.

## 📝 Adding Text to Files
````
echo "Hello, world" > hello.txt
cat > note.txt
````
##🔁 Input/Output Redirection
````
📤 Standard Output to File

echo "Output" > out.txt      # Overwrite
echo "More" >> out.txt       # Append
````
##📋 Using tee to Save and Display

````
echo "Log line" | tee logfile.txt
````
##🔗 Pipes

The | Pipes command is used for chaining or channelling initial command to produce a fine output 
````
ls -l | grep ".txt"
````
##🛠️ File Operations

🧹 File Maintenance Commands some of the commands here are used to create new file, remove or delete a file , move a file and even copy a file
````
    touch newfile.txt
    rm oldfile.txt
    mv oldname.txt newname.txt
    cp file.txt backup.txt
 ````   

##🔍 File Viewing & Text Processing
📖 File Display Commands
````
cat file.txt
less file.txt
head -n 5 file.txt
tail -f logfile.txt
````

##🧹 Filters (Text Processors)
  ✂️ cut
````
cut -d ":" -f1 /etc/passwd
````
  📄 awk
````
awk '{print $1, $3}' users.txt
````
🔍 grep / egrep
````
grep "error" logfile.txt
egrep "fail|error" logfile.txt
````
🧮 wc (Word Count)
````
wc file.txt
wc -l file.txt   # Line count
````
📑 sort, uniq
````
sort names.txt | uniq
sort -u names.txt
````
📂 Compare Files
````
diff file1.txt file2.txt
cmp file1.txt file2.txt
````
📦 Archiving and Compression
🗜️ Compress & Uncompress
bash
````
gzip file.txt
gunzip file.txt.gz
````
````
bzip2 file.txt
bunzip2 file.txt.bz2
````
````
xz file.txt
unxz file.txt.xz
````
  ✂️ Truncate File Size
````
truncate -s 0 logfile.txt       # Empties file
truncate -s 1K data.txt         # Set size to 1KB
````
  🧩 File Combination and Splitting
````
cat part1.txt part2.txt > full.txt      # Combine
split -b 1M bigfile.txt chunk_          # Split into 1MB files
````
⚙️ Linux System Administration & Utilities
This section covers essential Linux system administration tools, from user management to process scheduling and system monitoring. Commands are presented with descriptions and practical examples.

✍️ Linux File Editors
 vi vs vim
vi is the classic text editor; vim is an improved version.

vim supports syntax highlighting, plugins, and more user-friendly operations.
````
vi filename           # Open or create a file
i                     # Switch to insert mode
:w                    # Save file
:q                    # Quit vi
:wq                   # Save and quit
dd                    # Delete a line
vi filename.txt                      # Open or create a file
i                                    # Enter insert mode
Esc                                  # Exit insert mode
:w                                   # Save changes
:q                                   # Quit editor
:wq                                  # Save and quit
:q!                                  # Quit without saving
dd                                   # Delete current line
yy                                   # Copy (yank) current line
p                                    # Paste copied line
u                                    # Undo last change
Ctrl + r                             # Redo
:set number                          # Show line numbers
:set nonumber                        # Hide line numbers
/word                                # Search for a word
:n                                   # Go to next search result
:N                                   # Go to previous search result
:10                                  # Go to line 10
:%s/old/new/g                        # Replace all instances of "old" with "new"
:r filename                          # Insert content of another file
:!ls                                 # Run shell command from vi
vim filename.txt                     # Open file in vim
vi filename.txt                      # Open file in vi (minimal features)
vimdiff file1 file2                  # Compare two files
vim -O file1 file2                   # Open files in vertical split
vim -p file1 file2                   # Open files in tabs
vim -u NONE filename.txt             # Open vim without plugins/settings

````
✂️ Text Stream Editors
🔹 sed Command (Stream Editor)
````      
sed 's/original/replacement/' file.txt   # Replace first occurrence in each line
sed -n 2,4p file.txt                      # Print lines 2 to 4
sed '/pattern/d' file.txt                # Delete lines matching pattern
sed -i 's/old/new/g' file.txt            # In-place substitution
sed '2d' file.txt                        # Delete 2nd line
sed -n '/pattern/p' file.txt             # Print lines matching pattern
sed 's/old/new/' file.txt            # Replace first "old" with "new" per line
sed 's/old/new/g' file.txt           # Replace all "old" with "new"
sed -i 's/ubuntu/debian/g' file.txt  # Edit file in-place
sed -n '/pattern/p' file.txt         # Print lines matching pattern
sed '/pattern/d' file.txt            # Delete lines with matching pattern
sed -n '5,10p' file.txt              # Print lines 5 to 10
sed '1d' file.txt                    # Delete the first line
sed '$d' file.txt                    # Delete the last line
sed -i '2i\Inserted Line' file.txt   # Insert line above line 2
sed -i '3a\Appended Line' file.txt   # Append after line 3

````

👤 User Account Management
🔹 Managing Users
````
useradd username              # Create new user
passwd username               # Set user password
usermod -aG group username    # Add user to a group
id username                   # Check user ID and group
whoami                        # Show current user
userdel username              # Delete a user
adduser juwop                        # Add a new user
useradd -m user1                    # Create user with home directory
passwd juwop                        # Set password for user
usermod -aG sudo juwop              # Add user to sudo group
deluser juwop                       # Delete user
userdel -r user1                    # Delete user and home directory
groupadd devops                     # Create new group
usermod -aG devops juwop            # Add user to group
id juwop                            # Show UID, GID and groups
groups juwop                        # Show user's groups
chage -l juwop                      # Show user password aging info

````
⏳ Password Aging
````
chage -l username             # View password aging info
chage -M 90 username          # Set max password age
chage -m 7 username           # Set min password age
chage -W 10 username          # Set warning days before expiration
chage -E 2025-12-31 username  # Expiry date
passwd -x 90 username         # Another way to set max age
````
 Switching Users and Using Sudo
 ````
chage -l username             # View password aging info
chage -M 90 username          # Set max password age
chage -m 7 username           # Set min password age
chage -W 10 username          # Set warning days before expiration
chage -E 2025-12-31 username  # Expiry date
passwd -x 90 username         # Another way to set max age
su - juwop                          # Switch to user
sudo su                            # Switch to root via sudo
sudo apt update                    # Run command as root
sudo -u www-data ls /var/www       # Run command as another user
whoami                             # Display current user
sudo -i                            # Start root login shell

````
👀 Monitor and Talk to Users
````
who                          # List users currently logged in
w                            # See what users are doing
id                           # Show user ID info
last                         # Show last login of users
write username               # Send message to a user
wall "Message"               # Broadcast message to all users
who                              # List users currently logged in
w                                # Display users and their activities
users                            # Show logged-in usernames only
id juwop                         # Show UID, GID, groups for a user
groups juwop                     # Show user’s groups
logname                          # Show current login name
whoami                           # Display effective username
hostname                         # Show system hostname
uptime                           # Show how long system has been running
lslogins                        # Display detailed user account information
last                             # Show last logins
last -a                          # Show logins with hostname
last -x                          # Include system shutdown/reboot info
lastlog                          # Show last login for all users
lastlog | grep -v "**Never logged in**"  # Show users who have logged in
faillog                          # Show failed login attempts
ac                               # Connect time report
ac -d                            # Show connect time per day
ac -p                            # Connect time per user
who -b                           # Show last system boot time
ps -u juwop                      # Show processes owned by user
pgrep -u juwop                   # Get PIDs owned by user
pkill -u juwop                   # Kill all processes for user
top -u juwop                     # Monitor resource usage for user
htop                             # Interactive process monitor
pstree -u juwop                  # Tree of processes for user
lsof -u juwop                    # Open files by user
finger juwop                     # User details (if installed)
who -u                           # Show idle time and PID
whoami && id                    # Show current user and identity info
tty                              # Show current terminal
who -m                           # Display your session only
who -T                           # Show terminal write status
users | tr ' ' '\n' | sort | uniq -c   # Count logged-in sessions per user
loginctl                        # Systemd user sessions
loginctl list-sessions          # Show active user sessions
loginctl show-session $XDG_SESSION_ID  # Session info for systemd
ss -pt                           # Show users connected to SSH/TCP
ps aux | grep ssh               # Show SSH user sessions
cat /etc/passwd                 # Show all user accounts
journalctl _UID=$(id -u juwop)     # View logs by user ID
ausearch -ua $(id -u juwop)        # Search audit logs (if auditd is enabled)
auditctl -l                        # List active audit rules
watch who                          # Monitor logins in real-time
watch 'ps -u juwop'                # Monitor user processes live
last | grep juwop                  # See login history for specific user
getent passwd juwop                # Lookup user info via NSS
stat /home/juwop                   # Show detailed file info for user's home
sudo grep juwop /var/log/auth.log  # Auth logs (Debian/Ubuntu)
sudo grep juwop /var/log/secure    # Auth logs (RHEL/CentOS)

````
🔍 System Utility Commands
This are the day to days activities that will be run on linux system 
````
date                         # Show current date/time
uptime                       # System load and uptime
hostname                     # System hostname
uname -a                     # Kernel and system info
which bash                   # Show path of executable
cal                          # Calendar
bc                           # Command line calculator
````
Process Management
````
ps aux                       # Show all running processes
top                          # Real-time process monitoring
kill PID                     # Kill process by PID
killall process_name         # Kill process by name
bg                           # Send job to background
fg                           # Bring background job to foreground
````

Foreground & Background Process Control
````
sleep 60 &                       # Run command in background
bg                               # Resume stopped job in background
fg                               # Resume job in foreground
ctrl+z                           # Pause (stop) a foreground process
disown                           # Remove job from shell management
nohup command &                  # Run command immune to hangups
setsid command                   # Run in new session
command &>/dev/null &           # Run silently in background
wait                             # Wait for background jobs to finish
jobs -l                          # Jobs with PIDs
````
Killing & Signaling Processes
````
kill <PID>                       # Terminate a process by PID
kill -9 <PID>                    # Force kill (SIGKILL)
killall firefox                  # Kill all processes by name
pkill firefox                    # Kill process by name
pkill -u juwop                   # Kill processes of a specific user
xkill                            # GUI tool to kill a window (X11)
kill -STOP <PID>                 # Stop/suspend process
kill -CONT <PID>                 # Resume stopped process
kill -HUP <PID>                  # Send SIGHUP (often for config reload)
kill -TERM <PID>                 # Send default signal (SIGTERM)
````
Priority and Nice Values
````
nice -n 10 command               # Run command with adjusted priority
nice --20 command                # Run with lowest priority
renice -n 10 -p <PID>            # Change priority of a running process
top -p <PID>                     # Monitor specific PID in top
ionice -c2 -n7 command           # Set IO scheduling class and priority
chrt -f 99 command               # Run command with real-time priority
schedtool -R -p 99 <PID>         # Set real-time scheduling (if installed)
ps -eo pid,ni,cmd | grep <PID>   # Show nice value of process
uptime                           # See system load (affects scheduling)
vmstat 1                         # View processes waiting and sleeping
````
Advanced & Miscellaneous Tools
````
strace -p <PID>                  # Trace system calls
lsof -p <PID>                    # List files opened by process
gdb -p <PID>                     # Debug a running process
cat /proc/<PID>/status           # Show status info of a process
cat /proc/<PID>/cmdline          # Command line of a process
cat /proc/<PID>/io               # I/O stats of a process
cat /proc/<PID>/sched            # Scheduling info
watch "ps -ef | grep nginx"      # Monitor a specific process live
top -d 1                         # Refresh process view every second
atop                             # Advanced process/resource monitor (if installed)
````
 Systemctl (Service Control)
 
 ````
systemctl start service      # Start service
systemctl stop service       # Stop service
systemctl status service     # Check service status
systemctl enable service     # Enable service at boot
systemctl disable service    # Disable from boot
systemctl restart service    # Restart service
````
🔹 Process Signals
````
kill -9 PID                  # SIGKILL – force terminate
kill -15 PID                 # SIGTERM – request terminate
trap "command" SIGNAL        # Trap signal and run a command
pkill -SIGINT process_name   # Send specific signal to process
````
⏰ Scheduling Jobs
🔹 crontab
````
crontab -e                   # Edit user cron jobs
crontab -l                   # List current cron jobs
crontab -r                   # Remove all cron jobs
````
🔹 at command
````
at 5pm                       # Schedule job at 5 PM
atq                          # Show pending at jobs
atrm 2                       # Remove job ID 2
````
Additional Cron Directories
````
/etc/cron.hourly/
/etc/cron.daily/
/etc/cron.weekly/
/etc/cron.monthly/
````
📊 System Monitoring
````
df -h                        # Disk space usage
dmesg | less                 # Kernel ring buffer
iostat 1                     # CPU and I/O usage
netstat -tuln                # Network sockets and ports
free -h                      # Memory usage
top                          # Interactive process view
````
🧾 System Logs & Maintenance
````
tail -f /var/log/syslog      # Real-time log monitoring
shutdown -h now              # Shutdown immediately
init 0                       # Another shutdown method
reboot                       # Reboot the system
halt                         # Halt the system
journalctl                   # View systemd logs
````
🖥️ Hostname & System Info
````
hostnamectl set-hostname newname    # Change hostname
uname -r                            # Kernel version
dmidecode -t system                 # BIOS/hardware info
arch                                # System architecture
````
Terminal Tips 
````
clear                        # Clear terminal screen
exit                         # Exit shell session
script                       # Record terminal session
CTRL+C                       # Kill current command
CTRL+Z                       # Suspend current command
CTRL+D                       # End of input or logout
````

🔐 Root Password Recovery
Reboot into single-user mode
Mount the system with write permissions:
````
mount -o remount,rw /
````
Reset password:
````
passwd root
````
🧾 SOS Report (System Diagnostic Report)

````
sosreport                    # Collect system diagnostic data (RedHat-based)
````
🌍 Environment Variables

````
printenv                     # Print all env vars
echo $PATH                   # Show PATH variable
export VAR=value             # Set variable
unset VAR                    # Unset variable
env                          # Run command with environment
````
🔐 Special Permissions
````
chmod u+s file               # SetUID
chmod g+s dir                # SetGID
chmod +t dir                 # Sticky bit
````
🧩 Terminal Multiplexers
````
screen                      # Start screen session
screen -r                   # Reattach to screen
tmux                        # Start tmux session
tmux ls                     # List tmux sessions
tmux attach-session -t 0    # Attach to session 0
tmux new -s mysession        # Create new session
````



