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
