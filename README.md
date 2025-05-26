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

### 📸 Taking Snapshots (Best Practice)

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

### 📁 Linux Filesystem & Navigation

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
### 📁 Linux Files and Directory Permissions (Letters)

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
### 🔢 Files and Directory Permissions (Numeric)
Each permission has a value: r = 4, w = 2, x = 1
````
chmod 755 script.sh     # rwxr-xr-x
chmod 644 file.txt      # rw-r--r--
````
### 👥File Ownership Commands
Check ownership and change ownership
````
ls -l
chown newuser file.txt         # Change owner
chown newuser:newgroup file.txt # Change owner and group
````
### Access Control List (ACL)
ACL provides more fine-grained permission control.
Enable ACL on filesystem:
````mount -o remount,acl / ````
Set ACL:
````setfacl -m u:john:rwx file.txt````
````getfacl file.txt````
### 🧭 Navigation & Productivity 🆘 Help Commands
````
man chmod
chmod --help
info chmod
````
### ⌨️ TAB Completion & History
Use TAB to auto-complete paths and commands.

Press ↑ (Up arrow) to navigate command history.

### 📝 Adding Text to Files
````
echo "Hello, world" > hello.txt
cat > note.txt
````
### 🔁 Input/Output Redirection
````
📤 Standard Output to File

echo "Output" > out.txt      # Overwrite
echo "More" >> out.txt       # Append
````
### 📋 Using tee to Save and Display

````
echo "Log line" | tee logfile.txt
````
### 🔗 Pipes

The | Pipes command is used for chaining or channelling initial command to produce a fine output 
````
ls -l | grep ".txt"
````
### 🛠️ File Operations

🧹 File Maintenance Commands some of the commands here are used to create new file, remove or delete a file , move a file and even copy a file
````
    touch newfile.txt
    rm oldfile.txt
    mv oldname.txt newname.txt
    cp file.txt backup.txt
 ````   

### 🔍 File Viewing & Text Processing
📖 File Display Commands
````
cat file.txt
less file.txt
head -n 5 file.txt
tail -f logfile.txt
````

###🧹 Filters (Text Processors)
###  ✂️ cut
````
cut -d ":" -f1 /etc/passwd
````
### 📄 awk
````
awk '{print $1, $3}' users.txt
````
### 🔍 grep / egrep
````
grep "error" logfile.txt
egrep "fail|error" logfile.txt
````
### 🧮 wc (Word Count)
````
wc file.txt
wc -l file.txt   # Line count
````
### 📑 sort, uniq
````
sort names.txt | uniq
sort -u names.txt
````
### 📂 Compare Files
````
diff file1.txt file2.txt
cmp file1.txt file2.txt
````
### 📦 Archiving and Compression
### 🗜️ Compress & Uncompress
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
###  ✂️ Truncate File Size
````
truncate -s 0 logfile.txt       # Empties file
truncate -s 1K data.txt         # Set size to 1KB
````
### 🧩 File Combination and Splitting
````
cat part1.txt part2.txt > full.txt      # Combine
split -b 1M bigfile.txt chunk_          # Split into 1MB files
````
### ⚙️ Linux System Administration & Utilities
This section covers essential Linux system administration tools, from user management to process scheduling and system monitoring. Commands are presented with descriptions and practical examples.

✍️ Linux File Editors
 vi vs vim
vi is the classic text editor; vim is an improved version.

### vim supports syntax highlighting, plugins, and more user-friendly operations.
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
### ✂️ Text Stream Editors
### 🔹 sed Command (Stream Editor)
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

### 👤 User Account Management
### 🔹 Managing Users
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
### ⏳ Password Aging
````
chage -l username             # View password aging info
chage -M 90 username          # Set max password age
chage -m 7 username           # Set min password age
chage -W 10 username          # Set warning days before expiration
chage -E 2025-12-31 username  # Expiry date
passwd -x 90 username         # Another way to set max age
````
### Switching Users and Using Sudo
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
### 👀 Monitor and Talk to Users
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
### 🔍 System Utility Commands
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
### Process Management
````
ps aux                       # Show all running processes
top                          # Real-time process monitoring
kill PID                     # Kill process by PID
killall process_name         # Kill process by name
bg                           # Send job to background
fg                           # Bring background job to foreground
````

### Foreground & Background Process Control
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
### Killing & Signaling Processes
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
### Priority and Nice Values
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
### Advanced & Miscellaneous Tools
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
### Systemctl (Service Control)
 
 ````
systemctl start service      # Start service
systemctl stop service       # Stop service
systemctl status service     # Check service status
systemctl enable service     # Enable service at boot
systemctl disable service    # Disable from boot
systemctl restart service    # Restart service
````
### 🔹 Process Signals
````
kill -9 PID                  # SIGKILL – force terminate
kill -15 PID                 # SIGTERM – request terminate
trap "command" SIGNAL        # Trap signal and run a command
pkill -SIGINT process_name   # Send specific signal to process
````
### ⏰ Scheduling Jobs
### 🔹 crontab
````
crontab -e                   # Edit user cron jobs
crontab -l                   # List current cron jobs
crontab -r                   # Remove all cron jobs
# 1. Update package list daily at 5 AM
0 5 * * * apt update
# 2. Upgrade system packages every Sunday at 4 AM
0 4 * * 0 apt upgrade -y
# 3. Check system disk usage every hour
0 * * * * df -h > /home/juwop/disk_usage.txt
# 4. Save running processes list every 2 hours
0 */2 * * * ps aux > /home/juwop/ps_report.txt
# 5. Check memory status every 6 hours
0 */6 * * * free -h > /home/juwop/memory_status.txt
# 6. Save list of logged-in users every 15 min
*/15 * * * * who > /home/juwop/loggedin_users.txt
# 7. Run fail2ban log check nightly
0 1 * * * fail2ban-client status > /home/juwop/fail2ban_status.txt
# 8. Monitor top 10 memory-consuming processes
*/30 * * * * ps aux --sort=-%mem | head -n 11 > /home/juwop/top_mem.txt
# 9. Clean apt cache every Friday at 3 AM
0 3 * * 5 apt clean
# 10. Reboot system monthly on the 1st at 4 AM
0 4 1 * * /sbin/reboot
# 11. Backup /etc directory daily at 2 AM
0 2 * * * tar -czf /backup/etc_backup_$(date +\%F).tar.gz /etc
# 12. Backup home directory weekly
0 3 * * 6 tar -czf /backup/home_backup.tar.gz /home/juwop
# 13. Rsync data to remote server daily
30 1 * * * rsync -avz /home/juwop user@server:/backup/
# 14. Backup MySQL database every day at midnight
0 0 * * * mysqldump -u root -pYourPass dbname > /backup/db.sql
# 15. Clear backup older than 30 days
0 5 * * * find /backup -type f -mtime +30 -delete
# 16. Copy logs to external drive weekly
0 6 * * 0 cp /var/log/*.log /mnt/usbdrive/logs/
# 17. Compress Apache logs daily
0 23 * * * gzip /var/log/apache2/*.log
# 18. Backup crontab list weekly
0 4 * * 7 crontab -l > /backup/cron.bak
# 19. Archive system logs every day at 11 PM
0 23 * * * tar -czf /logs/$(date +\%F)_logs.tar.gz /var/log/
# 20. Create system image monthly
0 1 1 * * dd if=/dev/sda of=/backup/system.img
# 21. Delete temp files every day
0 2 * * * rm -rf /tmp/*
# 22. Find and delete old logs over 15 days
0 3 * * * find /var/log -name "*.log" -mtime +15 -exec rm -f {} \;
# 23. Move files from Downloads to Archive every 3 days
0 10 */3 * * mv ~/Downloads/* ~/Archive/
# 24. Empty trash weekly
0 8 * * 6 rm -rf ~/.local/share/Trash/*
# 25. Change file permission on logs every night
0 1 * * * chmod 640 /var/log/*.log
# 26. Rename log files weekly
0 0 * * 0 find /var/log -name "*.log" -exec mv {} {}.bak \;
# 27. Monitor file changes using inotifywait
*/10 * * * * inotifywait -q -e modify /etc/passwd >> /home/juwop/passwd_changes.log
# 28. Remove orphan packages monthly
0 3 1 * * apt autoremove -y
# 29. Set permissions on home directory daily
0 5 * * * chmod 755 /home/juwop
# 30. Clean cache every 2 days
0 4 */2 * * rm -rf ~/.cache/*
# 31. Email system load average
*/30 * * * * uptime | mail -s "Load Avg" your@email.com
# 32. Notify disk usage over 90%
*/15 * * * * df -H | awk '$5+0 > 90 {print $0}' | mail -s "Disk Alert" your@email.com
# 33. Alert for SSH login
* * * * * grep "Accepted" /var/log/auth.log | tail -1 | mail -s "SSH Login" your@email.com
# 34. Send system reboot alert
@reboot echo "System Rebooted at $(date)" | mail -s "Reboot Alert" your@email.com
# 35. Ping server hourly and report if down
0 * * * * ping -c 4 google.com || echo "Ping failed" | mail -s "Ping Alert" your@email.com
# 36. Alert on high CPU load
*/5 * * * * uptime | awk '{if ($10 > 2.00) print $0}' | mail -s "CPU Load High" your@email.com
# 37. Mail current user activity every 3 hrs
0 */3 * * * w | mail -s "User Activity" your@email.com
# 38. Log sudo usage
*/10 * * * * cat /var/log/auth.log | grep sudo >> /home/juwop/sudo_usage.log
# 39. Log firewall activity
0 * * * * journalctl -u ufw > /home/juwop/ufw.log
# 40. Track open ports every 2 hours
0 */2 * * * netstat -tuln > /home/juwop/open_ports.txt
# 41. Open terminal with message (X server only)
0 9 * * * DISPLAY=:0 xterm -e 'echo "Good morning!"'
# 42. Play music every day at 7 AM
0 7 * * * mplayer /home/juwop/music/alarm.mp3
# 43. Run Python script every 10 minutes
*/10 * * * * python3 /home/juwop/scripts/monitor.py
# 44. Execute bash script on weekdays
0 6 * * 1-5 /home/juwop/scripts/weekday_task.sh
# 45. Run cleanup on last day of month
59 23 28-31 * * [ "$(date +\%d -d tomorrow)" = "01" ] && /home/juwop/cleanup.sh
# 46. Set brightness to low at night
0 20 * * * xrandr --output eDP-1 --brightness 0.3
# 47. Remind to take a break every 2 hours
0 */2 * * * notify-send "Take a break"
# 48. Restart network interface every midnight
0 0 * * * systemctl restart NetworkManager
# 49. Run malware scan daily
30 1 * * * clamscan -r /home/juwop > /home/juwop/malware_report.txt
# 50. Log battery status every hour
0 * * * * upower -i /org/freedesktop/UPower/devices/battery_BAT0 > ~/battery_log.txt

````
### 🔹 at command
````
at 5pm                       # Schedule job at 5 PM
atq                          # Show pending at jobs
atrm 2                       # Remove job ID 2
````
### Additional Cron Directories
````
/etc/cron.hourly/
/etc/cron.daily/
/etc/cron.weekly/
/etc/cron.monthly/
````
### 📊 System Monitoring
````
df -h                        # Disk space usage
dmesg | less                 # Kernel ring buffer
iostat 1                     # CPU and I/O usage
netstat -tuln                # Network sockets and ports
free -h                      # Memory usage
top                          # Interactive process view
````
### 🧾 System Logs & Maintenance
````
tail -f /var/log/syslog      # Real-time log monitoring
shutdown -h now              # Shutdown immediately
init 0                       # Another shutdown method
reboot                       # Reboot the system
halt                         # Halt the system
journalctl                   # View systemd logs
# 1. Show memory usage in human-readable format
free -h
# 2. Display CPU and memory usage dynamically
top
# 3. Interactive real-time process viewer
htop
# 4. Show CPU statistics
mpstat -P ALL 1 5
# 5. Show virtual memory statistics
vmstat 2 5
# 6. Display I/O statistics per device
iostat -dx 2 3
# 7. Show disk usage in human-readable format
df -h
# 8. Show inodes usage
df -i
# 9. List disk partition usage
lsblk
# 10. Check block device stats
iostat
# 11. Monitor TCP/UDP network connections
netstat -tulpn
# 12. List open files and network connections
lsof -i
# 13. Monitor network bandwidth
iftop
# 14. Real-time network stats
nload
# 15. Show network interfaces and their states
ip addr
# 16. Show routing table
ip route
# 17. Display active internet connections
ss -tulnp
# 18. Ping a host and show packet loss
ping -c 4 8.8.8.8
# 19. Trace route to host
traceroute google.com
# 20. Monitor kernel messages
dmesg | tail
# 21. Watch CPU frequency in real-time
watch "lscpu | grep MHz"
# 22. Show uptime and load average
uptime
# 23. Display system boot time
who -b
# 24. Show currently logged-in users
who
# 25. View system logs (journalctl)
journalctl -xe
# 26. View logins, shutdowns, reboots
last -x
# 27. Monitor user sessions
w
# 28. Display process tree
pstree
# 29. List running processes sorted by memory
ps aux --sort=-%mem | head
# 30. Show top processes by CPU
ps aux --sort=-%cpu | head
# 31. Show processes in tree structure
ps -ejH
# 32. Show disk I/O per process
iotop
# 33. Show real-time file system usage
watch df -h
# 34. Monitor a file for changes
tail -f /var/log/syslog
# 35. Real-time load and CPU utilization
glances
# 36. Monitor per-process CPU usage over time
pidstat 1 5
# 37. Show number of running processes
ps -e | wc -l
# 38. List zombie processes
ps aux | awk '{ if ($8 == "Z") print $0; }'
# 39. Show system temperature
sensors
# 40. Show top 10 memory consuming apps
ps aux --sort=-%mem | head -n 11
# 41. Show swap usage
swapon --show
# 42. Show disk space used by a directory
du -sh /var
# 43. List largest files in root directory
find / -type f -exec du -Sh {} + | sort -rh | head -n 10
# 44. Count TCP connections
netstat -an | grep -c ESTABLISHED
# 45. Monitor connections per port
ss -s
# 46. Get system hardware summary
lshw -short
# 47. View BIOS and motherboard info
dmidecode | less
# 48. Show PCI devices
lspci
# 49. Show USB devices
lsusb
# 50. List available systemd services
systemctl list-units --type=service --state=running

````
### 🖥️ Hostname & System Info
````
hostnamectl set-hostname newname    # Change hostname
uname -r                            # Kernel version
dmidecode -t system                 # BIOS/hardware info
arch                                # System architecture
````
### Terminal Tips 
````
clear                        # Clear terminal screen
exit                         # Exit shell session
script                       # Record terminal session
CTRL+C                       # Kill current command
CTRL+Z                       # Suspend current command
CTRL+D                       # End of input or logout
````

### 🔐 Root Password Recovery
````
Reboot into single-user mode
Mount the system with write permissions:
mount -o remount,rw /
Reset password:
passwd root
````
### 🧾 SOS Report (System Diagnostic Report)

````
sosreport                    # Collect system diagnostic data (RedHat-based)
````
### 🌍 Environment Variables

````
printenv                     # Print all env vars
echo $PATH                   # Show PATH variable
export VAR=value             # Set variable
unset VAR                    # Unset variable
env                          # Run command with environment
````
### 🔐 Special Permissions
````
chmod u+s file               # SetUID
chmod g+s dir                # SetGID
chmod +t dir                 # Sticky bit
````
### 🧩 Terminal Multiplexers
````
screen                      # Start screen session
screen -r                   # Reattach to screen
tmux                        # Start tmux session
tmux ls                     # List tmux sessions
tmux attach-session -t 0    # Attach to session 0
tmux new -s mysession        # Create new session
````

### 📁 Shell Scripting

This section covers foundational Linux administration concepts around the kernel, shell, scripting, and automating Linux system tasks. All scripts are practical and tailored for what i will be doing as a system administrators.

---

## 🧠 What is Kernel?
The **kernel** is the core of a Linux OS that manages system resources and communication between hardware and software.


## 💬 What is Shell?
The **shell** is a command-line interface (CLI) to interact with the OS. Examples include bash, zsh, and sh.

---

## 🧪 Types of Shells
- **Bash** – Default in most distros.
- **sh** – Original Unix shell.
- **zsh** – Extended features.
- **ksh** – Korn shell.
- **csh** – C-like syntax.

---

### 📜 Shell Scripting
Automate tasks using command sequences saved in `.sh` files.

### ➕ Getting Started

mkdir ~/Josephscripts
cd /Josephscripts
nano ~/scripts/sample.sh
chmod +x ~/scripts/sample.sh
./sample.sh

````
#!/bin/bash
# Display current users
who
# Show date and time
echo "Today is: $(date)"
# Check disk usage
df -h
````
### 📥 Input/Output Scripts
````
# Prompt user input
read -p "Enter username: " user
echo "User is $user"
# Redirect output to a file
ls -l > output.txt
# Display file content
cat output.txt
````
### ❓ if-then Scripts
````
# File existence check
if [ -f /etc/passwd ]; then echo "Exists"; fi
# Check if user is root
[ "$USER" == "root" ] && echo "Root user" || echo "Not root"
# Check if sshd is running
systemctl is-active --quiet sshd && echo "Running" || echo "Stopped"
````
### 🔁 for loop Scripts
````
# Loop users
for user in alice bob; do echo $user; done
# Repeated disk checks
for i in {1..3}; do df -h; sleep 2; done
# Ping servers
for ip in 8.8.8.8 1.1.1.1; do ping -c 1 $ip; done

````
### 🔄 while loop Scripts
````
# Countdown
count=5; while [ $count -gt 0 ]; do echo $count; ((count--)); done

# Repeat uptime
while true; do uptime; sleep 3; done

# Exit loop on keyword
while true; do read -p "exit?: " input; [ "$input" = "exit" ] && break; done
`````
### 🧱 case Statement
````
# Menu-driven script
read -p "1.Date 2.Uptime: " choice
case $choice in 1) date ;; 2) uptime ;; *) echo "Invalid" ;; esac

# Service check
read -p "Enter service: " svc
case $svc in sshd|httpd) systemctl status $svc ;; *) echo "Unknown" ;; esac

# Confirm input
read -p "Y/N? " ans
case $ans in [Yy]*) echo "Yes" ;; [Nn]*) echo "No" ;; *) echo "Invalid" ;; esac
````
✅ Enabling Internet in Linux VM
To enable internet in your Linux virtual machine:

🛠️ For VMware:
Open VM Settings → Go to Network Adapter.

Choose NAT (Network Address Translation) to share host internet.

Boot the VM and run:
````
nmcli connection show     # View network interfaces
nmcli device connect eth0 # Connect the Ethernet adapter
````
🛠️ For VirtualBox:
Settings → Network → Adapter 1

Select: Attached to: NAT

Boot the VM and run:

````
dhclient                   # Request IP address via DHCP
ping -c 3 google.com       # Test internet connectivity
````
📂 Important Network Files
````
File	Purpose
/etc/sysconfig/network-scripts/ifcfg-*	Interface configuration
/etc/resolv.conf	DNS resolver settings
/etc/hosts	Manual hostname-to-IP mapping
/etc/hostname	Defines system hostname
/etc/network/interfaces (Debian/Ubuntu)	Interface definitions
````
⚙️ Network Commands with Examples
🔍 ping – Check Host Connectivity
````
ping google.com                      # Ping domain to check internet
ping -c 4 8.8.8.8                    # Send 4 ICMP packets
ping -i 2 1.1.1.1                    # Set interval to 2 seconds
ping -s 100 www.example.com          # Send 100 bytes packets
ping -W 5 google.com                 # Wait max 5 sec for a reply
ping -b 192.168.1.255                # Ping broadcast address
````
📡 ifconfig – Interface Configuration
````
ifconfig                             # Show all interfaces
ifconfig eth0                        # Show eth0 only
ifconfig eth0 up                     # Enable eth0
ifconfig eth0 down                   # Disable eth0
ifconfig eth0 192.168.1.10 netmask 255.255.255.0 up   # Set static IP
ifconfig eth0 promisc                # Enable promiscuous mode
````
🔔 ifconfig is deprecated; prefer ip a or nmcli on modern distros.


🔁 ifup and ifdown – Enable/Disable Interfaces
````
ifup eth0                            # Bring eth0 up
ifdown eth0                          # Bring eth0 down
ifup enp0s3                          # Start interface by name
ifdown enp0s3                        # Shut down that interface
````

📶 netstat – Network Statistics
````
netstat -tuln                       # List all listening ports
netstat -rn                         # Show routing table
netstat -ap                         # Show all connections + PIDs
netstat -s                          # Show protocol statistics
netstat -i                          # Display interface stats
netstat -plunt                      # See ports + program names
````
✅ Use ss as a modern alternative: ss -tuln

🧪 tcpdump – Network Packet Capture Tool
````
tcpdump -i eth0                     # Capture packets on eth0
tcpdump -n -i eth0                  # Do not resolve IP/port to names
tcpdump -c 10                       # Capture only 10 packets
tcpdump port 80                     # Capture HTTP traffic
tcpdump host 192.168.1.1            # Capture packets to/from a host
tcpdump -w output.pcap              # Write capture to file
tcpdump -r output.pcap              # Read from capture file
````
🔐 Requires root privileges.

🖧 Advanced Network Configuration & Utilities
This section dives into setting up and managing NICs, configuring bonded interfaces, using modern network management tools, and downloading files via the terminal.

1️⃣ Setting Up and Managing NICs (Network Interface Cards)
🔧 Tasks and Commands:
````
ip a                                # Show all interfaces and IPs
ip link set eth0 up                # Enable NIC
ip link set eth0 down              # Disable NIC
ip addr add 192.168.1.10/24 dev eth0   # Assign static IP
ip route add default via 192.168.1.1   # Add default gateway
ip link show                       # Show NIC status
ethtool eth0                       # View NIC capabilities
nmcli device status                # List devices
nmcli con show                     # Show active connections
````
Setting Up and Configuring NIC Bonding
NIC bonding allows multiple network interfaces to act as one for redundancy or throughput.

✅ Steps (RHEL/CentOS-based):
Install bonding kernel module:
modprobe bonding
echo "bonding" >> /etc/modules-load.d/bonding.conf
2. Create bond configuration file:
````
nmcli con add type bond con-name bond0 ifname bond0 mode active-backup
nmcli con add type ethernet con-name slave1 ifname eth0 master bond0
nmcli con add type ethernet con-name slave2 ifname eth1 master bond0
nmcli con up bond0
````
3. Verify
````
cat /proc/net/bonding/bond0
ip a
````
 Modern Network Utilities
🔹 nmtui – Text UI for Network Manager
nmtui                              # Launch interactive menu
````# Use arrows to edit or activate connections````
nmcli – Command-Line Network Management
````
nmcli device                      # Show all network devices
nmcli con show                    # Show all connections
nmcli device connect eth0         # Connect interface
nmcli device disconnect eth0      # Disconnect interface
nmcli con mod eth0 ipv4.addresses 192.168.1.50/24
nmcli con mod eth0 ipv4.gateway 192.168.1.1
nmcli con mod eth0 ipv4.method manual
nmcli con up eth0
````
🔹 nm-connection-editor – GUI Network Tool
````nm-connection-editor              # Launch GUI connection editor (X required)
````
 # GNOME Network Settings
Navigate: Settings > Network
Manage Wi-Fi, VPN, Proxy, Ethernet
Requires desktop environment.

4️⃣ Downloading Files and Apps
📥 wget – Non-interactive file downloader
````
wget http://example.com/file.iso             # Download file
wget -c http://example.com/file.iso          # Resume interrupted download
wget -O myfile.zip http://example.com/file.zip   # Rename output
wget -r http://example.com/folder/           # Recursive download
wget --limit-rate=100k http://example.com    # Limit bandwidth usage
````
🔁 curl – Transfer data using various protocols
````
curl http://example.com                      # Fetch and display content
curl -O http://example.com/file.zip          # Download file (original name)
curl -o newfile.txt http://example.com/page  # Rename output
curl -L http://bit.ly/xyz                    # Follow redirects
curl -I http://example.com                   # Show HTTP headers only
curl -u user:pass http://example.com/secure  # Authenticated request
````
📶 ping – Check Internet or Host Connectivity
````
ping 8.8.8.8                                 # Test basic connectivity
ping -c 5 google.com                         # Send 5 ICMP packets
ping -s 64 example.com                       # Ping with specific packet size
ping -W 3 yahoo.com                          # Set timeout
````
🔌 Linux Network Tools: ss, FTP, SCP, rsync

🔍 ss — Socket Statistics
✅ What It Is:
ss (socket statistics) is a tool used to investigate and display information about active socket connections on a Linux system.

🛠️ Installation:

# RHEL/CentOS
````
sudo yum install iproute -y
````

# Ubuntu/Debian
````
sudo apt install iproute2 -y
````
📥 Usage Examples:
````
ss -tuln                          # Show all listening TCP/UDP sockets
ss -tn state established          # Show only established TCP connections
ss -s                             # Show summary statistics of sockets
ss -pl                            # Show processes using ports (requires sudo)
ss -tn sport = :22                # Show connections on source port 22
ss -t state time-wait             # Show TIME_WAIT connections (TCP cleanup)
ss -tp | grep sshd                # Show connections related to sshd
ss -4                             # Show only IPv4 sockets
ss -6                             # Show only IPv6 sockets
ss -nap                           # Show all with PID and app info
````
💡 Use Cases:
Monitor open ports and their services
Check for zombie TCP sessions
Audit incoming SSH or web traffic
Diagnose socket leaks

📁 FTP — File Transfer Protocol (vsftpd)
✅ What It Is:
vsftpd (Very Secure FTP Daemon) is a secure and fast FTP server that allows file sharing using the FTP protocol.

🛠️ Installation:
````
sudo yum install vsftpd -y
sudo systemctl start vsftpd
sudo systemctl enable vsftpd
``````
⚙️ Configuration: /etc/vsftpd/vsftpd.conf
````
anonymous_enable=NO
local_enable=YES
write_enable=YES
chroot_local_user=YES
````
Restart the service:
````
sudo systemctl restart vsftpd
````
📥 Usage (Client Side):
````
ftp <hostname or IP>
Name: user
Password: ******

get file.txt                         # Download file
put upload.txt                       # Upload file
lcd /path/to/local/dir               # Change local directory
cd /path/on/server                   # Change server directory
ls                                   # List remote files
mget *.log                           # Download multiple files
bye                                  # Exit FTP session
````
💡 Use Cases:
Upload backups to centralized FTP servers
Receive log files from remote clients
Public anonymous download server (if configured)

🔐 SCP — Secure Copy Protocol

scp (Secure Copy) is a command-line utility that uses SSH to securely transfer files between computers.

🛠️ Installation:
````
sudo yum install openssh-clients -y
````
📥 Usage:
````
scp file.txt user@remote:/path/             # Copy file to remote
scp user@remote:/file.txt ./                # Copy file from remote
scp -P 2222 file user@host:/dir/            # Use custom SSH port
scp -r folder/ user@remote:/backup/         # Recursively copy folders
scp -i ~/.ssh/id_rsa file user@host:/tmp/   # Use private key for auth
````
💡 Use Cases:
Automated secure backups
Transfer configuration files between servers
Move scripts and deployment files in CI/CD pipelines

🔁 rsync — Remote Sync Utility

rsync is a powerful command-line utility for synchronizing files and directories between local and remote systems with efficiency.

🛠️ Installation:
````
sudo yum install rsync -y
````
📥 Usage:
````
rsync -av file user@remote:/backup/         # Archive mode
rsync -avz dir/ user@remote:/backup/        # Compress during transfer
rsync -e ssh -av file user@remote:/path/    # Transfer over SSH
rsync -av --delete src/ dest/               # Mirror (deletes extras)
rsync -n -av file user@host:/path/          # Dry-run (simulate)
rsync -av --progress bigfile remote:/dest/  # Show progress
rsync -rzvh --exclude "*.log" src/ dest/    # Exclude patterns
````
💡 Use Cases:
Mirror production directories to backup servers
Push code to web servers
Sync config files across a fleet of servers
Efficient large file transfers with delta compression
### 🛠️ Package and Patch Management in Linux
📦 1. System Updates and Repositories
✅ What it is:
System updates pull latest versions of installed packages using online or offline repositories.
```
yum repolist                 # Display current repositories
yum repolist enabled         # List all enabled repositories
yum repolist disabled        # List all disabled repositories
yum list available httpd     # Check if 'httpd' package is available
yum install epel-release -y  # Install EPEL repository for extra packages
yum makecache                # Update the repo metadata cache
yum info nano                # View detailed info about 'nano' package
yum-config-manager --enable <repo-id>    # Enable a specific repository
yum-config-manager --disable <repo-id>   # Disable a specific repository
yum clean all                # Clean all cached data (metadata and packages)
yum clean packages           # Remove cached packages only
yum check-update             # Check for available package updates
yum update vim               # Update only 'vim' package
yum update -y                # Update all installed packages automatically
yum --security update        # Update only security patches
yum repolist all             # List all repositories (enabled and disabled)
vi /etc/yum.repos.d/custom.repo    # Edit or add a custom repo file
echo "fastestmirror=1" >> /etc/yum.conf    # Enable fastest mirror plugin
echo "keepcache=1" >> /etc/yum.conf        # Keep packages in cache after install
````
### System Upgrade and Patch Management
System upgrades and patch management ensure your system is protected by applying security fixes and software improvements. yum upgrade upgrades all packages, and tools like yum history help track or undo updates.
````
yum upgrade -y                  # Upgrade all packages automatically
yum upgrade nginx -y            # Upgrade only the 'nginx' package
yum distro-sync -y              # Sync packages to distro versions (full upgrade)
yum updateinfo list security all    # List all security updates
yum install nginx-1.16.1 -y     # Install specific version of 'nginx'
yum versionlock nginx           # Lock 'nginx' package to current version
yum versionlock delete nginx    # Unlock 'nginx' from version lock
yum versionlock list            # List all version locked packages
yum --showduplicates list nginx # Show all available versions of 'nginx'
yum --security upgrade          # Upgrade all security patches
yum history                    # Show all yum transaction history
yum history info 3             # Show details of transaction #3
yum history undo 3             # Undo transaction #3
yum history redo 3             # Redo transaction #3
yum history rollback 2         # Roll back to transaction #2
rpm -Va                       # Verify installed packages for altered files
yum check                     # Check for broken dependencies or problems
yum upgrade --assumeno nginx  # Simulate upgrade of 'nginx' (no install)
````
### Creating a Local YUM Repository
Explanation:
A local YUM repository stores RPM packages on your local server, allowing you to install software without internet access. createrepo generates metadata for the repository.
````
mkdir -p /var/www/html/yumrepo               # Create local repo directory
cp /path/to/rpms/*.rpm /var/www/html/yumrepo/  # Copy RPM files to repo folder
yum install createrepo -y                     # Install metadata creator
createrepo /var/www/html/yumrepo/             # Create repository metadata
yum install httpd -y                           # Install Apache web server
systemctl start httpd                          # Start Apache server
systemctl enable httpd                         # Enable Apache at boot
chcon -R -t httpd_sys_content_t /var/www/html/yumrepo/   # Allow Apache access (SELinux)
vi /etc/yum.repos.d/local.repo                 # Create/edit local repo config file
# Add to local.repo:
# [localrepo]
# name=Local YUM Repo
# baseurl=http://localhost/yumrepo/
# enabled=1
# gpgcheck=0
yum clean all                                  # Clean yum cache
yum repolist                                   # Verify local repo availability
yum --disablerepo="*" --enablerepo="localrepo" install <package-name> -y  # Install package from local repo
````
### Advanced Package Management
Advanced package management includes troubleshooting dependencies, querying detailed package info, and downloading packages without installing.
````
yum install httpd -y               # Install package with dependencies
yumdownloader nginx                # Download nginx RPM without installing
yum deplist nginx                  # List dependencies of 'nginx'
yum provides */nginx               # Find which repo provides 'nginx'
rpm -qf /usr/sbin/httpd            # Find package owning specific file
rpm -qa                           # List all installed packages
rpm -q nginx                      # Query if 'nginx' installed
yum remove nginx -y               # Remove 'nginx' package
yum reinstall nginx -y            # Reinstall 'nginx' package
rpm -V nginx                     # Verify files of 'nginx' package
repoquery --requires nginx        # Show package dependencies
repoquery --whatrequires nginx    # Show reverse dependencies
rpm -q --changelog nginx          # View changelog of 'nginx'
yumdownloader --source nginx      # Download source RPM of 'nginx'
rpm2cpio nginx.rpm | cpio -idmv   # Extract RPM package contents
rpm -ivh --nodeps package.rpm     # Force install RPM ignoring dependencies
rpm -Uvh nginx.rpm                # Upgrade package using rpm manually
````
### 🔁 Section Rolling Back Updates and Patches
````
yum history                         # List all yum transactions
yum history info 7                 # Show info on transaction #7
yum history undo 7                 # Undo transaction #7
yum history rollback 5             # Roll back to transaction #5
yum downgrade nginx                # Downgrade 'nginx' to previous version
yum remove nginx && yum install nginx-1.16.1 -y   # Remove and install older version
yum versionlock nginx-1.16.1       # Lock 'nginx' to older version
yum history list all               # List all transactions
yum history list update            # List update transactions only
rpm -Uvh --oldpackage nginx-1.16.1.rpm   # Install old RPM manually
cp -r /var/cache/yum /opt/yum-backup     # Backup current cached RPMs
yum remove <package-name>          # Remove broken package
yum-complete-transaction --cleanup-only # Complete or cleanup incomplete yum transaction
echo "keepcache=1" >> /etc/yum.conf      # Keep packages cached after install for rollback
````
### 🔐 Section 1: Setting Up and Managing SSH and Telnet
SSH (Secure Shell) is the secure, encrypted method to remotely access Linux systems. Telnet is an older, unencrypted protocol rarely used now but still found in legacy environments. Managing these services involves installing, configuring, starting/stopping, and securing the servers.
````
# Install OpenSSH server and client
yum install openssh-server openssh-clients -y         # Install SSH server and clients
systemctl start sshd                                  # Start SSH daemon
systemctl enable sshd                                 # Enable SSH to start on boot
systemctl status sshd                                 # Check SSH daemon status
firewall-cmd --permanent --add-service=ssh           # Open SSH port 22 in firewall
firewall-cmd --reload                                 # Reload firewall rules
ss -tnlp | grep ssh                                  # Verify SSH is listening on port 22
vim /etc/ssh/sshd_config                             # Edit SSH server config file
# Example: Change port, disable root login, allow specific users
systemctl restart sshd                                # Restart SSH service after config changes
ssh user@hostname                                     # Connect to remote SSH server
scp file.txt user@hostname:/path                      # Securely copy file via SSH
ssh-keygen                                           # Generate SSH key pair
ssh-copy-id user@hostname                            # Copy SSH public key for passwordless login
yum install telnet -y                                # Install telnet client (rarely used)
yum install telnet-server -y                         # Install telnet server
systemctl start telnet.socket                         # Start telnet socket service
systemctl enable telnet.socket                        # Enable telnet socket service at boot
firewall-cmd --permanent --add-port=23/tcp           # Open telnet port 23 in firewall
firewall-cmd --reload                                 # Reload firewall rules
telnet hostname                                      # Connect to remote host via telnet
ss -tnlp | grep telnet                               # Verify telnet is listening (if enabled)
systemctl stop telnet.socket                          # Stop telnet socket service (recommended to disable)
````
### 🌐 Download, Install and Configure DNS
DNS (Domain Name System) resolves domain names to IP addresses. bind is the most common DNS server software on Linux. Configuring DNS involves installing bind, setting up zone files, and managing service status.
````
yum install bind bind-utils -y                        # Install BIND DNS server and utilities
vim /etc/named.conf                                   # Edit main BIND configuration
# Configure zones, allow queries, logging
vim /var/named/example.com.zone                        # Create forward zone file
vim /var/named/reverse.zone                            # Create reverse zone file
chown named:named /var/named/example.com.zone          # Set proper ownership for zone files
chown named:named /var/named/reverse.zone
systemctl start named                                  # Start DNS server
systemctl enable named                                 # Enable DNS server at boot
firewall-cmd --permanent --add-service=dns            # Allow DNS port 53 TCP/UDP in firewall
firewall-cmd --reload                                 # Reload firewall rules
dig @localhost example.com                            # Test DNS resolution locally
host example.com                                      # Query DNS for example.com
nslookup example.com                                  # Another DNS query tool
systemctl status named                                # Check DNS server status
rndc reload                                           # Reload DNS server config without restart
rndc status                                           # Get current DNS server status
named-checkconf                                       # Check syntax of named.conf
named-checkzone example.com /var/named/example.com.zone  # Validate zone file
tail -f /var/log/messages                             # Monitor DNS server logs
setsebool -P named_write_master_zones on             # SELinux permission for bind to write zones
````
### 🖥 Hostname and IP Lookup
Managing system hostname and performing IP lookups are basic network tasks useful for identifying and diagnosing systems.
````
hostname                                             # Show current hostname
hostnamectl set-hostname newhostname                 # Change system hostname permanently
cat /etc/hostname                                    # View saved hostname
ip addr show                                         # Display all IP addresses on interfaces
ip addr show eth0                                    # Show IP on specific interface
ip route show                                        # Show routing table
nslookup google.com                                  # DNS lookup for google.com
host google.com                                      # Another hostname lookup tool
dig google.com                                       # Detailed DNS lookup
ping -c 4 8.8.8.8                                    # Ping external IP address (Google DNS)
ping -c 4 google.com                                 # Ping domain to test DNS resolution
ip link show                                         # Show network interfaces and status
nmcli device status                                  # Show NetworkManager device status
nmcli connection show                                # List network connections
ifconfig                                            # Show network interfaces (deprecated but still used)
arp -a                                              # Show ARP table entries
ip -s link                                          # Show interface statistics
netstat -ie                                         # Show detailed interface stats
cat /etc/hosts                                      # Check local hostname to IP mappings
`````
### ⏰ Section 4: Network Time Protocol (NTP)
NTP synchronizes system time with global time servers. Proper time sync is critical for logs, security, and operations. CentOS 7 uses ntpd or chronyd.
````
yum install ntp -y                                  # Install NTP daemon
systemctl start ntpd                                # Start NTP service
systemctl enable ntpd                               # Enable NTP service at boot
ntpq -p                                             # Query NTP peers and sync status
timedatectl                                         # Show current time settings
ntpstat                                             # Show synchronization status
ntpdate pool.ntp.org                                # Manually sync time once
systemctl restart ntpd                              # Restart NTP after config changes
vim /etc/ntp.conf                                   # Edit NTP configuration file
firewall-cmd --permanent --add-service=ntp         # Allow NTP port 123 UDP in firewall
firewall-cmd --reload                               # Reload firewall rules
chronyc tracking                                    # Show chrony tracking status (if using chrony)
chronyc sources                                     # Show chrony sources
timedatectl set-ntp true                            # Enable systemd NTP sync
date                                                # Show current system date and time
hwclock --systohc                                   # Sync hardware clock to system time
hwclock --hctosys                                   # Sync system time from hardware clock
````
### chronyd – Newer Version of NTP

chronyd is a modern replacement for ntpd with better performance on intermittent network connections. CentOS 7 uses it by default.
````
yum install chrony -y                               # Install chrony daemon
systemctl start chronyd                             # Start chrony service
systemctl enable chronyd                            # Enable chrony at boot
chronyc tracking                                   # Show current time sync status
chronyc sources                                    # Show configured time servers
chronyc sourcestats                                # Detailed source statistics
chronyc activity                                   # Show chrony activity info
vim /etc/chrony.conf                               # Edit chrony config file
systemctl restart chronyd                           # Restart after config changes
firewall-cmd --permanent --add-service=ntp        # Open UDP port 123 for chrony
firewall-cmd --reload                              # Reload firewall rules
timedatectl set-ntp true                           # Enable NTP sync via systemd
timedatectl status                                 # Check time sync status
date                                               # Show system date/time
hwclock --systohc                                  # Sync hardware clock to system time
chronyc makestep                                  # Force immediate time correction
chronyc sources -v                                # Verbose source info
systemctl status chronyd                           # Check chrony service status
````
### 🕒 Section 6: New System Utility – timedatectl
timedatectl is a modern utility to query and change the system clock and its settings including timezone and NTP status.
````
timedatectl                                          # Show current date/time and NTP status
timedatectl status                                   # Detailed status of time settings
timedatectl set-time "2025-05-26 15:30:00"           # Set system date/time manually
timedatectl set-timezone Africa/Lagos                 # Set timezone
timedatectl list-timezones                             # List all available timezones
timedatectl set-ntp true                               # Enable NTP synchronization
timedatectl set-ntp false                              # Disable NTP synchronization
timedatectl show                                       # Show current settings
timedatectl timesync-status                            # Show systemd-timesyncd status
timedatectl set-local-rtc 1                            # Enable RTC to use local time
timedatectl set-local-rtc 0                            # Disable RTC local time usage
timedatectl show-timesync                              # Show detailed timesync info
date                                                  # Display current date and time
hwclock --systohc                                      # Sync hardware clock from system clock
hwclock --hctosys                                      # Sync system clock from hardware clock
systemctl restart systemd-timesyncd                    # Restart time synchronization service
timedatectl set-time "2025-05-26 10:00:00"             # Example manual time set
````
### Mail Transfer Agent (MTA) – Sendmail
 📌 What is Sendmail?
Sendmail is one of the most widely used Mail Transfer Agents (MTAs) that routes and delivers email on a network. It is complex but highly configurable.

### ✅ Installation & Setup

```bash
yum install sendmail sendmail-cf -y                          # Install Sendmail and config tools
systemctl start sendmail                                     # Start the Sendmail service
systemctl enable sendmail                                    # Enable Sendmail to start at boot
firewall-cmd --permanent --add-port=25/tcp                  # Open SMTP port 25
firewall-cmd --reload                                        # Reload firewall
sendmail -d0.1 -bv root                                      # Test Sendmail config
hostnamectl set-hostname mailserver.local                   # Set a proper hostname for Sendmail
vim /etc/hosts                                               # Ensure hostname resolves to IP
vim /etc/mail/sendmail.mc                                    # Edit macro config file
m4 /etc/mail/sendmail.mc > /etc/mail/sendmail.cf             # Compile config to main file
systemctl restart sendmail                                   # Apply new config by restarting
echo "Test email" | mail -s "Subject" user@domain.com        # Send a test email
mailq                                                       # Show mail queue
sendmail -q                                                  # Force send queue
tail -f /var/log/maillog                                     # Monitor Sendmail logs
yum install mailx -y                                         # Install mail client for sending mail
alternatives --config mta                                    # View/set default MTA
postconf -n                                                  # (Postfix alternative config check)
````
### Web Server – Apache httpd
📌 What is Apache?
Apache is a widely used open-source web server for hosting web content over HTTP/HTTPS.

✅ Installation & Setup
````
yum install httpd -y                                         # Install Apache web server
systemctl start httpd                                        # Start Apache
systemctl enable httpd                                       # Enable Apache to start on boot
firewall-cmd --permanent --add-service=http                 # Allow HTTP port 80
firewall-cmd --permanent --add-service=https                # Allow HTTPS port 443
firewall-cmd --reload                                        # Reload firewall
ss -tnlp | grep :80                                          # Confirm Apache is listening on port 80
vim /etc/httpd/conf/httpd.conf                               # Edit Apache main config file
mkdir -p /var/www/html/testsite                              # Create web directory
echo "Hello Apache" > /var/www/html/testsite/index.html     # Create test HTML file
systemctl restart httpd                                      # Restart to apply changes
httpd -v                                                     # Show Apache version
apachectl configtest                                         # Test Apache config
apachectl graceful                                           # Gracefully restart Apache
tail -f /var/log/httpd/access_log                            # Monitor access log
tail -f /var/log/httpd/error_log                             # Monitor error log
semanage port -a -t http_port_t -p tcp 8080                 # Allow Apache on custom port
systemctl stop httpd                                         # Stop Apache server
````
### Web Server – nginx
📌 What is nginx?
nginx is a lightweight, high-performance web server often used as a reverse proxy and load balancer.
````
yum install epel-release -y                                  # Enable EPEL repo (required for nginx)
yum install nginx -y                                         # Install nginx
systemctl start nginx                                        # Start nginx service
systemctl enable nginx                                       # Enable nginx at boot
firewall-cmd --permanent --add-service=http                 # Allow HTTP
firewall-cmd --permanent --add-service=https                # Allow HTTPS
firewall-cmd --reload                                        # Reload firewall rules
ss -tnlp | grep :80                                          # Check if nginx is listening on port 80
nginx -v                                                     # Check nginx version
vim /etc/nginx/nginx.conf                                    # Edit main nginx config
mkdir -p /usr/share/nginx/html/test                          # Create test website directory
echo "Welcome to nginx" > /usr/share/nginx/html/test/index.html  # Add index.html
nginx -t                                                     # Test nginx configuration
systemctl restart nginx                                      # Restart to apply new config
tail -f /var/log/nginx/access.log                            # Monitor access log
tail -f /var/log/nginx/error.log                             # Monitor error log
systemctl stop nginx                                         # Stop nginx server
nginx -s reload                                              # Reload nginx without full restart
````
Here are basic shell scripts to automate the installation, initial setup, and basic management for the following services, crafted in a clean, professional format for your GitHub Linux Administration Portfolio:

✅ Sendmail (MTA)

✅ Apache (httpd)

✅ nginx

✅ rsyslog (Central Logger)
vi install_sendmail.sh
````
#!/bin/bash
# Script to install and configure Sendmail (MTA)

echo "[+] Installing Sendmail..."
yum install sendmail sendmail-cf mailx -y

echo "[+] Starting and enabling Sendmail..."
systemctl start sendmail
systemctl enable sendmail

echo "[+] Opening SMTP port 25..."
firewall-cmd --permanent --add-port=25/tcp
firewall-cmd --reload

echo "[+] Setting hostname for Sendmail..."
hostnamectl set-hostname mailserver.local
echo "127.0.0.1   mailserver.local" >> /etc/hosts

echo "[+] Verifying Sendmail config..."
sendmail -d0.1 -bv root

echo "[+] Sendmail installed and configured."
````
vi install_httpd.sh 
````
#!/bin/bash
# Script to install and configure Apache HTTPD server

echo "[+] Installing Apache..."
yum install httpd -y

echo "[+] Starting and enabling Apache..."
systemctl start httpd
systemctl enable httpd

echo "[+] Opening HTTP and HTTPS ports..."
firewall-cmd --permanent --add-service=http
firewall-cmd --permanent --add-service=https
firewall-cmd --reload

echo "[+] Creating sample website..."
mkdir -p /var/www/html/testsite
echo "Hello from Apache" > /var/www/html/testsite/index.html

echo "[+] Restarting Apache..."
systemctl restart httpd

echo "[+] Apache setup complete. Visit http://<your_server_ip>/testsite"
````
vi install_nginx.sh
````
#!/bin/bash
# Script to install and configure nginx server

echo "[+] Installing EPEL and nginx..."
yum install epel-release -y
yum install nginx -y

echo "[+] Starting and enabling nginx..."
systemctl start nginx
systemctl enable nginx

echo "[+] Opening HTTP and HTTPS ports..."
firewall-cmd --permanent --add-service=http
firewall-cmd --permanent --add-service=https
firewall-cmd --reload

echo "[+] Creating sample nginx website..."
mkdir -p /usr/share/nginx/html/test
echo "Welcome to nginx server" > /usr/share/nginx/html/test/index.html

echo "[+] Restarting nginx..."
systemctl restart nginx

echo "[+] nginx setup complete. Visit http://<your_server_ip>/test"
````
vi install_rsyslog.sh 
````
#!/bin/bash
# Script to install and configure rsyslog for local and remote logging

echo "[+] Installing rsyslog..."
yum install rsyslog -y

echo "[+] Starting and enabling rsyslog..."
systemctl start rsyslog
systemctl enable rsyslog

echo "[+] Configuring remote logging..."
sed -i '/^#\$ModLoad imudp/s/^#//' /etc/rsyslog.conf
sed -i '/^#\$UDPServerRun 514/s/^#//' /etc/rsyslog.conf
sed -i '/^#\$ModLoad imtcp/s/^#//' /etc/rsyslog.conf
sed -i '/^#\$InputTCPServerRun 514/s/^#//' /etc/rsyslog.conf

echo "[+] Opening UDP/TCP port 514..."
firewall-cmd --permanent --add-port=514/udp
firewall-cmd --permanent --add-port=514/tcp
firewall-cmd --reload

echo "[+] Creating log directory for remote hosts..."
mkdir -p /var/log/remotelogs

echo "[+] Adding custom log rule..."
echo "\$template RemoteLogs,\"/var/log/remotelogs/%HOSTNAME%.log\"" > /etc/rsyslog.d/remote.conf
echo "*.* ?RemoteLogs" >> /etc/rsyslog.d/remote.conf

echo "[+] Restarting rsyslog..."
systemctl restart rsyslog

echo "[+] rsyslog configured for central logging."

````
### ✅ Permissions Note
After saving each script (e.g., install_httpd.sh), ill give it an execute permissions:
chmod a+x install_httpd.sh
to run the script the we can proceed to ````./install_httpd.sh````

### ✅ Installing, Configuring and Managing Nagios on Linux
🔹 What is Nagios?
Nagios is a powerful open-source monitoring system that enables organizations to identify and resolve IT infrastructure problems before they affect critical business processes. It monitors systems, networks, and infrastructure.

🔧 Step-by-Step Installation and Configuration of Nagios on CentOS 7
# Install required packages
````
sudo yum install -y httpd php gcc glibc glibc-common gd gd-devel make net-snmp openssl-devel wget unzip perl

# Create nagios user and group
sudo useradd nagios
sudo groupadd nagcmd
sudo usermod -a -G nagcmd nagios
sudo usermod -a -G nagcmd apache

# Download Nagios Core
cd /tmp
wget https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.4.6.tar.gz

# Extract and compile
tar -xzf nagios-4.4.6.tar.gz
cd nagios-4.4.6
./configure --with-command-group=nagcmd
make all
sudo make install
sudo make install-init
sudo make install-config
sudo make install-commandmode
sudo make install-webconf

# Set Nagios web admin password
sudo htpasswd -c /usr/local/nagios/etc/htpasswd.users nagiosadmin

# Enable Apache and Nagios
sudo systemctl enable httpd
sudo systemctl start httpd
sudo systemctl enable nagios
sudo systemctl start nagios

# Install Nagios plugins
cd /tmp
wget https://nagios-plugins.org/download/nagios-plugins-2.3.3.tar.gz
tar -xzf nagios-plugins-2.3.3.tar.gz
cd nagios-plugins-2.3.3
./configure --with-nagios-user=nagios --with-nagios-group=nagios
make
sudo make install
````
### 🔐 OS Hardening in Linux (Practical Scenarios + Commands)
🔹 What is OS Hardening?
OS hardening secures the underlying operating system by reducing its attack surface, disabling unnecessary services, setting correct permissions, enforcing password policies, etc.
ESSENTIAL OS HARDENING AND THE ESSENTIAL BASH TO AUTOMATE IT 
````
# 1. Disable unnecessary services
systemctl disable bluetooth.service     # Disable Bluetooth if not needed
systemctl disable cups.service          # Disable printing service

# 2. Set password aging policies
chage --maxdays 90 username             # Password expires after 90 days
chage --mindays 7 username              # Minimum days before password change
chage --warn 14 username                # Warn user 14 days before password expiry

# 3. Disable root SSH login
sed -i 's/^PermitRootLogin.*/PermitRootLogin no/' /etc/ssh/sshd_config
systemctl restart sshd                 # Apply SSH configuration changes

# 4. Enable automatic updates (Debian)
apt install unattended-upgrades        # Install auto update package
dpkg-reconfigure unattended-upgrades   # Configure it

# 5. Set strong password policies
echo "minlen = 12" >> /etc/security/pwquality.conf  # Enforce minimum password length

# 6. Disable Ctrl+Alt+Del reboot
ln -sf /dev/null /etc/systemd/system/ctrl-alt-del.target

# 7. Enable auditing
yum install auditd -y                  # Install audit daemon
systemctl enable auditd                # Enable audit service
systemctl start auditd                 # Start audit service

# 8. Lock user account after failed login attempts
authconfig --enablefaillock --update
echo "auth required pam_faillock.so preauth audit silent deny=5 unlock_time=600" >> /etc/pam.d/system-auth

# 9. Set file permissions
chmod 700 ~/.ssh                       # Secure SSH directory
chmod 600 ~/.ssh/authorized_keys       # Secure key files

# 10. Configure firewall
firewall-cmd --add-service=ssh --permanent   # Allow SSH
firewall-cmd --remove-service=ftp --permanent  # Remove insecure services
firewall-cmd --reload                        # Apply firewall rules

# 11. Enable SELinux
sed -i 's/SELINUX=disabled/SELINUX=enforcing/' /etc/selinux/config
setenforce 1

# 12. Disable USB storage
echo "install usb-storage /bin/true" >> /etc/modprobe.d/disable-usb.conf

# 13. Remove unnecessary packages
yum remove telnet rsh ypbind xinetd -y       # Remove insecure or unused services

# 14. Set umask for users
echo "umask 027" >> /etc/profile             # Default permission for new files

# 15. Secure shared memory
echo "tmpfs /dev/shm tmpfs defaults,noexec,nosuid 0 0" >> /etc/fstab
mount -o remount /dev/shm

# 16. Create a banner for legal warning
echo "Authorized access only!" > /etc/issue
echo "Authorized access only!" > /etc/issue.net

# 17. Disable IPv6 if not in use
echo "net.ipv6.conf.all.disable_ipv6 = 1" >> /etc/sysctl.conf
sysctl -p

# 18. Limit use of compilers
chmod 000 /usr/bin/gcc                    # Prevent local users compiling programs

# 19. Run Lynis security audit
yum install epel-release -y
yum install lynis -y
lynis audit system                       # Run system audit

# 20. Create backup of critical files
tar -czvf /root/etc-backup.tar.gz /etc   # Backup configuration files
````
### 🔹 Accessing the Nagios Web Interface
Open your browser and navigate to:

http://<your_server_ip>/nagios
Login using:
Username: nagiosadmin
Password: set during installation via htpasswd

🔹 Core Nagios Directories and Files
Path	Description
/usr/local/nagios/etc	            Main configuration directory
/usr/local/nagios/etc/nagios.cfg	Main Nagios config file
/usr/local/nagios/etc/objects/	  Host/service/group config files
/usr/local/nagios/var/nagios.log	Nagios activity log
/usr/local/nagios/bin/nagios	    Nagios command-line binary

🔹 Useful Nagios Commands

````
# Start Nagios
sudo systemctl start nagios  # Start monitoring engine

# Stop Nagios
sudo systemctl stop nagios

# Restart Nagios
sudo systemctl restart nagios  # Apply new config changes

# Check configuration syntax
/usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg  # Validate config

# View Nagios process
ps aux | grep nagios  # Ensure nagios is running

# Tail logs for troubleshooting
tail -f /usr/local/nagios/var/nagios.log
````
🔹 Add a New Host for Monitoring
Create a new config file:

sudo vim /usr/local/nagios/etc/objects/linux-server.cfg
Example Host Definition:


define host{
    use             linux-server
    host_name       webserver1
    alias           Web Server
    address         192.168.1.10
}

# Add Service Checks:


define service{
    use                 generic-service
    host_name           webserver1
    service_description HTTP
    check_command       check_http
}

define service{
    use                 generic-service
    host_name           webserver1
    service_description PING
    check_command       check_ping!100.0,20%!500.0,60%
}
# Include the new config in nagios.cfg:

echo "cfg_file=/usr/local/nagios/etc/objects/linux-server.cfg" >> /usr/local/nagios/etc/nagios.cfg
Restart Nagios:
````
sudo systemctl restart nagios
````
# 🔹 Custom Check Commands (e.g., check disk usage)
Define a custom check in /usr/local/nagios/etc/objects/commands.cfg:

define command{
    command_name    check_disk_root
    command_line    $USER1$/check_disk -w 20% -c 10% -p /
}
Assign it to a host service:

cfg
Copy
Edit
define service{
    use                 generic-service
    host_name           webserver1
    service_description Root Disk Space
    check_command       check_disk_root
}
# 🔹 Viewing Host/Service Status on Web UI
Navigate to: http://<server_ip>/nagios

Click:

Current Status → to view Hosts and Services

Service Detail → detailed view per host

Notifications → alerts log

Tactical Overview → health summary

# 🔹 Notification & Alerting Configuration
Configure contact in contacts.cfg:

define contact{
    contact_name            sysadmin
    email                  you@example.com
    use                    generic-contact
}

define contactgroup{
    contactgroup_name       admins
    members                 sysadmin
}
Add to host/service definition:


contact_groups            admins
Enable email alerts in /etc/aliases and configure sendmail or postfix.

### 🔹 Using NRPE for Remote Checks
Install NRPE agent on client systems to perform local checks (like CPU, memory, disk usage):

````
yum install nrpe nagios-plugins-all -y
systemctl enable nrpe
systemctl start nrpe
````
Then configure /etc/nagios/nrpe.cfg and add NRPE commands to your Nagios server.

🧠 Example Monitoring Tasks
Task	Check Command
````
Ping host	  	          check_ping
Check HTTP port	        check_http
Check disk space	      check_disk
Check logged in users  	check_users
Check load average	    check_load
Check memory usage	    Custom via NRPE
Check open ports	      check_tcp -p <port>
````
### 📘 Installing, Setting Up, and Managing OpenLDAP on CentOS 7/8
🧩 What is OpenLDAP?
OpenLDAP is an open-source implementation of the Lightweight Directory Access Protocol (LDAP). It is used to maintain a directory of users, groups, and other objects, enabling centralized authentication and directory services.
# 🛠️ Step 1: Install OpenLDAP Server and Clients
````
sudo yum install openldap openldap-servers openldap-clients -y  # Install OpenLDAP packages
sudo systemctl enable slapd  # Enable slapd to start at boot
sudo systemctl start slapd  # Start the slapd (LDAP daemon)
````
# 🧾 Step 2: Verify OpenLDAP Installation
````
slaptest -u  # Validate LDAP configuration
systemctl status slapd  # Check status of the OpenLDAP daemon
````
# 🔐 Step 3: Set LDAP Administrator Password
````
slappasswd  # Generate a hashed password
````
# Then edit or create a file to apply this password using LDIF:
dn: olcDatabase={2}hdb,cn=config
changetype: modify
replace: olcRootPW
olcRootPW: <HASHED_PASSWORD_FROM_ABOVE>
# Apply the configuration:
````
ldapmodify -Y EXTERNAL -H ldapi:/// -f change-password.ldif  # Set admin password
````
# 🗂️ Step 4: Configure LDAP Domain
# Create domain structure using LDIF
````
cat > domain.ldif <<EOF
dn: dc=example,dc=com
objectClass: top
objectClass: dcObject
objectClass: organization
o: Example Company
dc: example

dn: cn=Manager,dc=example,dc=com
objectClass: organizationalRole
cn: Manager
description: Directory Manager
EOF

ldapadd -x -D cn=Manager,dc=example,dc=com -W -f domain.ldif  # Add domain entries
````
# 📁 Step 5: Add LDAP Base Structure (People and Groups)
````
cat > base.ldif <<EOF
dn: ou=People,dc=example,dc=com
objectClass: organizationalUnit
ou: People

dn: ou=Groups,dc=example,dc=com
objectClass: organizationalUnit
ou: Groups
EOF

ldapadd -x -D cn=Manager,dc=example,dc=com -W -f base.ldif  # Add OU structures
````
# 👥 Step 6: Add a User
````
cat > user.ldif <<EOF
dn: uid=jdoe,ou=People,dc=example,dc=com
objectClass: inetOrgPerson
sn: Doe
givenName: John
cn: John Doe
uid: jdoe
userPassword: password
mail: jdoe@example.com
EOF

ldapadd -x -D cn=Manager,dc=example,dc=com -W -f user.ldif  # Add user to directory
````
# 🔎 Step 7: Querying LDAP Entries
````
ldapsearch -x -b "dc=example,dc=com"  # View entire directory
ldapsearch -x -b "ou=People,dc=example,dc=com" uid=jdoe  # Search for a specific user
````
# 🧑‍💼 Step 8: Manage LDAP Users & Groups with Command-Line
````
# Add group
cat > group.ldif <<EOF
dn: cn=developers,ou=Groups,dc=example,dc=com
objectClass: posixGroup
cn: developers
gidNumber: 5000
EOF

ldapadd -x -D cn=Manager,dc=example,dc=com -W -f group.ldif  # Add new group

# Modify user to include in group
cat > usermod.ldif <<EOF
dn: uid=jdoe,ou=People,dc=example,dc=com
changetype: modify
add: gidNumber
gidNumber: 5000
EOF

ldapmodify -x -D cn=Manager,dc=example,dc=com -W -f usermod.ldif  # Assign user to group
````
# 🔐 Step 9: Configure LDAP Client (Optional)
````
sudo yum install nss-pam-ldapd openldap-clients nscd nss-pam-ldapd -y  # Install client packages
sudo authconfig --enableldap --enableldapauth --ldapserver=ldap://<server-ip> --ldapbasedn="dc=example,dc=com" --enablemkhomedir --update  # Configure client authentication
````
# 📦 Optional: Enable TLS Encryption for LDAP (Secure)
Generate certificate:
````
openssl req -new -x509 -nodes -out /etc/openldap/certs/ldap.crt -keyout /etc/openldap/certs/ldap.key -days 365
````
# Configure TLS in slapd config using ldif:
````
dn: cn=config
changetype: modify
add: olcTLSCertificateFile
olcTLSCertificateFile: /etc/openldap/certs/ldap.crt
-
add: olcTLSCertificateKeyFile
olcTLSCertificateKeyFile: /etc/openldap/certs/ldap.key
````
# Apply it:
````
ldapmodify -Y EXTERNAL -H ldapi:/// -f tls.ldif
systemctl restart slapd
````
# 🧪 Useful OpenLDAP Testing & Maintenance Commands
````
systemctl restart slapd                  # Restart the LDAP server
slaptest -u                              # Validate configuration
ldapsearch -x -LLL -b dc=example,dc=com  # Lightweight query of LDAP
slapcat                                  # Backup entire directory content to LDIF
slapadd -l backup.ldif                   # Restore from backup
````
## 3 🔍 Tracing Network Traffic – traceroute
📌 Purpose
traceroute helps trace the path packets take from your Linux system to a destination. It reveals each hop along the route and latency.

✅ Installation (if not installed)
````
sudo yum install traceroute -y     # Install on CentOS/RHEL
sudo apt install traceroute -y     # Install on Debian/Ubuntu
````
🧪 Usage Examples
````
traceroute google.com         # Trace route to google.com
traceroute -n 8.8.8.8         # Use numeric IPs only (skip DNS lookup)
traceroute -m 5 google.com    # Limit hops to 5
traceroute -p 443 example.com # Use custom port (443 here)
traceroute -T google.com      # Use TCP instead of UDP (better for firewalled networks)
````
### 🖼️ Opening Image Files in Linux (CLI-Based)
📌 Purpose
To view images from terminal in GUI or headless mode.

✅ Install image viewers
````
sudo yum install eog -y             # GNOME Eye of Gnome
sudo apt install feh -y             # Lightweight terminal image viewer
````
# 🧪 Usage
````
eog image.png                       # Opens image using Eye of GNOME
feh image.jpg                       # Opens image in feh
fim image.png                       # Opens in framebuffer terminal (for CLI environments)
xdg-open image.jpg                  # Default image viewer
````
### 🔐 Configure and Secure SSH
📌 Purpose
Secure remote access to your server via SSH.

✅ Installation (if SSH is missing)
````
sudo yum install openssh-server -y      # CentOS/RHEL
sudo apt install openssh-server -y      # Debian/Ubuntu
````
# 🚀 Start and Enable SSH
````
sudo systemctl enable sshd              # Enable SSH on boot
sudo systemctl start sshd               # Start SSH now
````
# 🔧 Configuration File
Edit /etc/ssh/sshd_config:
````
sudo vi /etc/ssh/sshd_config
````
# 🔐 Hardening SSH (Best Practices)
````
PermitRootLogin no           # Disable root login
PasswordAuthentication no    # Disable password login if using SSH keys
Port 2222                    # Change default port from 22
AllowUsers adminuser         # Allow only specific users
````
🔄 Restart SSH for changes to take effect

```` sudo systemctl restart sshd ````
### 🔑 SSH Keys – Access Remote Server Without Password
📌 Purpose
Enable secure, password-less login using SSH key pairs.
✅ Step 1: Generate SSH Key Pair
````
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
````
Saves to ~/.ssh/id_rsa and ~/.ssh/id_rsa.pub
✅ Step 2: Copy Public Key to Remote Server
````
ssh-copy-id user@remote_ip        # Automatically copies public key to remote server
````
OR Manually 
cat ~/.ssh/id_rsa.pub | ssh user@remote_ip "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"

✅ Step 3: SSH Without Password
````
ssh user@remote_ip                # Will log in using key authentication
````
🔐 Additional SSH Key Config (Optional)
Edit ~/.ssh/config:
````
Host myserver
    HostName 192.168.1.10
    User admin
    IdentityFile ~/.ssh/id_rsa
````

### ✅ ssh_key_setup.sh – Passwordless SSH Setup Script
````
#!/bin/bash

# ============================
# Passwordless SSH Setup Script
# ============================

# Define your variables
REMOTE_USER="yourusername"           # Remote server username
REMOTE_HOST="your.server.ip"         # Remote server IP address or hostname
REMOTE_PORT=22                       # Custom SSH port (default is 22)
KEY_FILE="$HOME/.ssh/id_rsa"         # SSH private key file path
SSH_CONFIG_FILE="/etc/ssh/sshd_config"

# ----------------------------
# Step 1: Generate SSH key pair (if not already exists)
# ----------------------------
if [ ! -f "$KEY_FILE" ]; then
    echo "[+] Generating SSH key pair..."
    ssh-keygen -t rsa -b 4096 -N "" -f "$KEY_FILE"
else
    echo "[*] SSH key already exists. Skipping key generation."
fi

# ----------------------------
# Step 2: Copy the public key to the remote server
# ----------------------------
echo "[+] Copying public key to remote server..."
ssh-copy-id -i "${KEY_FILE}.pub" -p $REMOTE_PORT "${REMOTE_USER}@${REMOTE_HOST}"

# ----------------------------
# Step 3: Harden SSH on the remote server (optional)
# ----------------------------
echo "[+] Configuring SSH on the remote server for key-only authentication..."

ssh -p $REMOTE_PORT ${REMOTE_USER}@${REMOTE_HOST} << EOF
sudo sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication no/' $SSH_CONFIG_FILE
sudo sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin no/' $SSH_CONFIG_FILE
sudo systemctl restart sshd
EOF

# ----------------------------
# Step 4: Test the connection
# ----------------------------
echo "[+] Testing passwordless SSH login..."
ssh -p $REMOTE_PORT "${REMOTE_USER}@${REMOTE_HOST}" "echo '✅ Passwordless SSH Login Successful!'"

echo "[✔] SSH key-based authentication is set up!"
````






