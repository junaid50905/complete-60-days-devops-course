# 📁 1. File System Navigation & Manipulation

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

Shows files and directories.

```bash
ls
```

### 🔹 Common Options

```bash
ls -l    # detailed list (permissions, size, date)
ls -a    # include hidden files
ls -la   # combine both
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

Opens file in a scrollable view.

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
cd ..   # go back
cd ~    # home directory
cd /    # root directory
```

---

## ❌ `rm` — Remove Files/Directories

```bash
rm file.txt
```

### 🔹 Options

```bash
rm -r folder   # delete directory
rm -f file     # force delete
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
| ls      | List files and folders |
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

### 🔑 Permission Types

| Symbol | Meaning |
| ------ | ------- |
| r      | Read    |
| w      | Write   |
| x      | Execute |

---

## 🔹 Check Permissions

```bash
ls -l
```

**Example:**

```bash
-rwxr-xr-- 1 user user 1234 Apr 22 file.sh
```

**Breakdown:**

```
-rwxr-xr--
 ||| ||| ||
 ||| ||| └── Others (r--)
 ||| └──── Group (r-x)
 └──────── User (rwx)
```

---

## 🔹 `chmod` — Change Permissions

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
chmod 777 file.sh   # ⚠️ not recommended
```

---

## 🔹 `chown` — Change Ownership

```bash
chown user file.txt
chown user:group file.txt
```

**Example:**

```bash
chown junaid:developers project.txt
```

---

## 🔹 `chgrp` — Change Group

```bash
chgrp developers file.txt
```

---

## 🔹 Important Tips 🔥

* For directories:

  * `x` = permission to enter
* Use recursive flag for folders:

```bash
chmod -R 755 myfolder
```

---

## ⚡ Permission Cheat Sheet

| Command         | Meaning         |
| --------------- | --------------- |
| chmod 755 file  | rwxr-xr-x       |
| chmod 644 file  | rw-r--r--       |
| chmod +x file   | Make executable |
| chown user file | Change owner    |


