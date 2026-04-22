# 📁 Linux File System & Permissions Guide

A beginner-friendly guide to essential Linux commands for file system navigation, manipulation, and permissions.

---

# 📂 1. File System Navigation & Manipulation

## 📍 `pwd` — Print Working Directory

Displays your current directory path.

```bash
pwd
```

**Example:**

```bash
/home/junaid/projects
```

---

## 📂 `ls` — List Directory Contents

Lists files and directories.

```bash
ls
```

### 🔹 Common Options

```bash
ls -l    # Detailed list (permissions, size, date)
ls -a    # Include hidden files
ls -la   # Combine both
```

💡 Tip: `ll` is often an alias for `ls -l`

---

## 📄 `cat` — View File Content

Display contents of a file.

```bash
cat file.txt
```

### 🔹 Merge Files

```bash
cat file1.txt file2.txt > merged.txt
```

---

## 📄 `less` — Read Large Files

Opens a file in a scrollable view.

```bash
less file.txt
```

### 🔹 Navigation Keys

| Key   | Action        |
| ----- | ------------- |
| Space | Next page     |
| b     | Previous page |
| Enter | Scroll down   |
| /text | Search        |
| n     | Next match    |
| q     | Quit          |

---

## ✏️ `vi` — Text Editor

Create and edit files in terminal.

```bash
vi file.txt
```

### 🔹 Modes

* **Command mode** (default)
* **Insert mode** → press `i`

### 🔹 Common Commands

| Command | Action            |
| ------- | ----------------- |
| i       | Enter insert mode |
| Esc     | Back to command   |
| :w      | Save              |
| :q      | Quit              |
| :wq     | Save & quit       |
| :q!     | Force quit        |

---

## 📁 `mkdir` — Create Directory

```bash
mkdir folder_name
```

### 🔹 Examples

```bash
mkdir dir1 dir2 dir3
mkdir -p parent/child/grandchild
mkdir -m 755 myfolder
```

---

## 📄 `touch` — Create File

```bash
touch file.txt
```

---

## 📂 `cd` — Change Directory

```bash
cd folder_name
```

### 🔹 Shortcuts

```bash
cd ..   # Go back
cd ~    # Home directory
cd /    # Root directory
```

---

## ❌ `rm` — Remove Files/Directories

```bash
rm file.txt
```

### 🔹 Options

```bash
rm -r folder   # Delete directory
rm -f file     # Force delete
```

⚠️ **Warning:** No recycle bin — deletion is permanent.

---

## 📁 `rmdir` — Remove Empty Directory

```bash
rmdir folder_name
```

---

## 🔑 Quick Summary

| Command | Purpose                |
| ------- | ---------------------- |
| pwd     | Show current directory |
| ls      | List files & folders   |
| cat     | View file content      |
| less    | Read large files       |
| vi      | Edit files             |
| mkdir   | Create directories     |
| touch   | Create files           |
| cd      | Change directory       |
| rm      | Delete files/folders   |
| rmdir   | Delete empty folders   |

---

# 🔐 2. Linux Permissions

## 🔹 Permission Basics

### 👥 User Types

| Symbol | Meaning |
| ------ | ------- |
| u      | Owner   |
| g      | Group   |
| o      | Others  |

---

### 🔑 Permission Types

| Symbol | Meaning |
| ------ | ------- |
| r      | Read    |
| w      | Write   |
| x      | Execute |

---

## 🔍 Check Permissions

```bash
ls -l
```

**Example:**

```bash
-rwxr-xr-- 1 user user 1234 Apr 22 file.sh
```

### 🔎 Breakdown

```
-rwxr-xr--
 ||| ||| ||
 ||| ||| └── Others (r--)
 ||| └──── Group (r-x)
 └──────── User (rwx)
```

---

## 🔧 `chmod` — Change Permissions

### 👉 Symbolic Method

```bash
chmod u+x file.sh
chmod g-w file.txt
chmod o+r file.txt
chmod a+x script.sh
```

---

### 👉 Numeric Method

| Permission | Value |
| ---------- | ----- |
| r          | 4     |
| w          | 2     |
| x          | 1     |

### 🔹 Examples

```bash
chmod 755 file.sh   # rwxr-xr-x
chmod 644 file.txt  # rw-r--r--
chmod 600 secret.txt
chmod 777 file.sh   # ⚠️ Not recommended
```

---

## 👤 `chown` — Change Ownership

```bash
chown user file.txt
chown user:group file.txt
```

**Example:**

```bash
chown junaid:developers project.txt
```

---

## 👥 `chgrp` — Change Group

```bash
chgrp developers file.txt
```

---

## 🔁 Recursive Permissions

```bash
chmod -R 755 myfolder
```

---

## 🔥 Important Tips

* For directories:

  * `x` = permission to enter
* Use recursive flag (`-R`) carefully

---

## ⚡ Permission Cheat Sheet

| Command         | Meaning         |
| --------------- | --------------- |
| chmod 755 file  | rwxr-xr-x       |
| chmod 644 file  | rw-r--r--       |
| chmod +x file   | Make executable |
| chown user file | Change owner    |

---

# 👑 3. `chown` — Change Owner (Detailed)

## 🔹 What is `chown`?

`chown` = **Change owner of a file or folder**

---

## 🔹 Basic Syntax

```bash
chown user file
```

**Example:**

```bash
sudo chown junaid file.txt
```

👉 Now `junaid` owns the file

---

## 🔹 Change User + Group

```bash
sudo chown user:group file
```

**Example:**

```bash
sudo chown junaid:developers file.txt
```

---

## 🔹 Change Only Group

```bash
sudo chown :group file
```

**Example:**

```bash
sudo chown :developers file.txt
```

---

## 🔹 Recursive for Folders

```bash
sudo chown -R user:group folder/
```

👉 Changes ownership for everything inside the folder

---

## 🔹 When to Use `chown`

* Fix **permission issues**
* Transfer file ownership
* Configure servers (e.g., web apps)

---

## ⚠️ Important Notes

* Usually requires `sudo`
* Incorrect ownership can break applications

---

## 🧠 Memory Trick

👉 **`chown` = "who owns the file"**

---


