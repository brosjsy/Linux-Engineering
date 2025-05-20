# Linux-Engineering
My hands-on lab journey as a Linux Engineer
# 🐧 Linux Engineer Hands-On Journey

Welcome to my public GitHub portfolio documenting my journey as a **Linux Engineer**. This project showcases each lab I complete — with screenshots, explanations, and commands used. I update this regularly as I grow!

---

## 🔧 Getting Started with Virtualization

### ✅ Tasks
- ✅ Installed VirtualBox
- There are different VIRTUAL BOX that can be used to power the linux, unix OS some of the workstation are Virtualbox, Vmware
- ![image](https://github.com/user-attachments/assets/43a70421-6881-4689-a034-ead81b4563d7) ![image](https://github.com/user-attachments/assets/956e4ab0-375c-4761-958a-5a93ab570cec)


- ✅ Installed VMware Player (Optional)
  **🔧 For Windows:**  
    **✅ Prerequisites:**
  64-bit Windows 10 or later.
  
  CPU with virtualization support (Intel VT-x or AMD-V).
  
  At least 2GB RAM (4GB or more recommended).
  
  🪜 Steps:
  **Download VMware Workstation Pro or Player:**
  
  Go to: https://www.vmware.com/go/getworkstation
  
  Choose Workstation Pro (paid/trial) or Workstation Player (free for personal use).
  
  **Run the Installer:**
  
  Double-click the downloaded .exe file.
  
  Allow it to run if prompted by UAC (User Account Control).
  
  **Installation Wizard:**
  
  Accept the license agreement.
  
  Choose the installation directory or go with default.
  
  Customize features (e.g., keyboard driver, enhanced keyboard, network features).
  
  Choose whether to enable product updates and join VMware CEIP.
  
  Install:
  
  **Click Install.**
  
  Wait for the process to complete (takes a few minutes).
  
  **License Key (for Workstation Pro):**
  
  You’ll be prompted to enter a license key or choose trial mode.
  
  **Finish:**
  Restart your system (recommended).
  
- ✅ Launch VMware Workstation from the Start Menu.
  ![image](https://github.com/user-attachments/assets/10ff9abf-7021-4d73-9a4e-0a583fa65a69) To start the Vmware workstation , you can start from the start menu and even create a new virtual machine directly 

- ✅ Created First Virtual Machine
- ✅ Installed CentOS 7
- ✅ Took First Snapshot

### 📸 Screenshots
![VirtualBox Installed](images/virtualbox-installed.png)  
![CentOS Installation](images/centos7-installed.png)

---

## 📁 Filesystem & Navigation

### ✅ Topics Covered
- Linux Filesystem Structure
- Navigating with `cd`, `ls`, `pwd`
- Absolute vs Relative Paths
- Creating & Deleting Files/Dirs
- File Types and `find` / `locate`

### 📜 Sample Commands
```bash
ls -al /etc
cd /home/user
mkdir projects
find / -name "*.conf"
