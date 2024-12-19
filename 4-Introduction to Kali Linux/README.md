# 🛡️ Cybersecurity Bootcamp
### 🚀 Lesson 4: Introduction to Kali Linux

---

## 📚 **What Will You Learn?**  
1. 🌐 **What is Kali Linux?**  
2. 🗂️ **Linux File System (Filesystem Hierarchy Standard (FHS))**  
3. 💻 **Linux Command Line**  
4. 📂 **Navigating the File System**  
5. ✏️ **Creating and Removing Files/Directories**  
6. 👥 **Users and Groups**  
7. 🔒 **Permissions**  

---

### 🌐 **1. What is Kali Linux?**  

Kali Linux is a **Debian-based Linux distribution** specifically tailored for:  
- Penetration Testing  
- Digital Forensics  
- Cybersecurity  

🔑 **Features**:  
- 🚀 Pre-installed security tools (e.g., Metasploit, Wireshark).  
- 🔐 Secure by default with minimal services enabled.  
- 📦 Portable: Can run live from a USB or install on your system.  

💡 **Use Cases**:  
- Ethical Hacking  
- Vulnerability Assessment  
- Network Security  

---

### 🗂️ **2. Linux File System (Filesystem Hierarchy Standard (FHS))**  

The Linux file system follows a structured hierarchy. Here's an overview:  

| **Directory**   | **Description**                                   |  
|------------------|---------------------------------------------------|  
| `/`             | Root directory. Everything begins here.           |  
| `/bin`          | Essential binaries like `ls`, `cp`, and `mv`.     |  
| `/etc`          | Configuration files.                              |  
| `/home`         | User home directories (`/home/username`).         |  
| `/var`          | Logs, caches, and variable files.                 |  
| `/tmp`          | Temporary files.                                  |  
| `/usr`          | System applications and utilities.                |  
| `/lib`          | Essential shared libraries.                       |  

---

### 💻 **3. Linux Command Line**  

The **Command Line Interface (CLI)** is a powerful way to interact with Linux.  

- ⚙️ **Why CLI?**  
  - Automate repetitive tasks.  
  - Lightweight and resource-efficient.  

- 🛠️ **Essential Commands**:  
  ```bash
  pwd         # Display current directory  
  ls          # List files in a directory  
  cd          # Change directory  
  cp          # Copy files/directories  
  mv          # Move or rename files  
  rm          # Remove files/directories  
  man         # Access command manual  
  ```  

---

### 📂 **4. Navigating the File System**  

📌 Use these commands to explore and manage directories:  

- **`pwd`**: Shows your current directory.  
- **`ls`**: Lists files and directories.  
  - `ls -l` → Detailed list.  
  - `ls -a` → Includes hidden files.  
- **`cd`**: Change directories:  
  - `cd /etc` → Go to `/etc`.  
  - `cd ~` → Go to home directory.  
  - `cd ..` → Move up one level.  

---

### ✏️ **5. Creating and Removing Files/Directories**  

🎨 **Creating Files/Directories**:  
- **`touch file.txt`**: Create an empty file.  
- **`mkdir folder_name`**: Create a directory.  

🗑️ **Removing Files/Directories**:  
- **`rm file.txt`**: Delete a file.  
- **`rm -r folder_name`**: Delete a directory and its contents.  
- **`rmdir folder_name`**: Delete an empty directory.  

---

### 👥 **6. Users and Groups**  

Linux users and groups manage access to system resources.  

- **Users**: Individual accounts with unique permissions.  
  - 🔑 **Root**: Superuser account for administration.  
- **Groups**: Shared access among multiple users.  

🛠️ **Commands**:  
- **`whoami`**: Current logged-in user.  
- **`id`**: Displays user and group IDs.  
- **`sudo`**: Run commands with admin privileges.  

---

### 🔒 **7. Permissions**  

Linux permissions control who can **read (r)**, **write (w)**, or **execute (x)** files.  

💡 **Permission Breakdown**:  
```plaintext
-rwxr-xr--  
Owner: rwx (read, write, execute)  
Group: r-x (read, execute)  
Others: r-- (read only)  
```  

🛠️ **Commands**:  
- **`chmod`**: Change file permissions. Example:  
  ```bash
  chmod 755 file.txt  
  ```  
- **`chown`**: Change file ownership. Example:  
  ```bash
  chown user:group file.txt  
  ```  

---

### 📝 **Summary**  

This lesson covers:  
- The purpose and features of Kali Linux.  
- Navigating the Linux file system and managing files/directories.  
- Understanding users, groups, and file permissions.  

✅ With these foundations, you're ready to explore Linux further and use Kali Linux effectively for cybersecurity tasks!  

---