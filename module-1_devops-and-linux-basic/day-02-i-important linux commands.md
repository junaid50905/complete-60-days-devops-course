# 1. 🐧 File System Navigation & Manipulation

---

## 📍 `pwd` — Print Working Directory

Shows your current location in the filesystem.

```bash
pwd
```

👉 Example output:

```bash
/home/junaid/projects
```

---

## 📂 `ls` — List Directory Contents

Displays files and folders in the current directory.

```bash
ls
```

### 🔹 Common options:

```bash
ls -l   # long format (permissions, size, date)
ls -a   # show hidden files
ls -la  # combine both
```

👉 Note: `ll` is usually an alias for `ls -l`

---

## 📄 `cat` — View File Content

Displays file contents in the terminal.

```bash
cat file.txt
```

### 🔹 Combine files:

```bash
cat file1.txt file2.txt > merged.txt
```

---

## 📄 `less` — View Large Files (Paged View)

Used for reading large files easily.

```bash
less file.txt
```

### 🔹 Navigation:

| Key     | Action        |
| ------- | ------------- |
| `Space` | Next page     |
| `b`     | Previous page |
| `Enter` | Scroll down   |
| `/text` | Search        |
| `n`     | Next match    |
| `q`     | Quit          |

---

## ✏️ `vi` — Terminal Text Editor

Used to create and edit files.

```bash
vi file.txt
```

### 🔹 Modes:

* **Command mode** (default)
* **Insert mode** (`i` to edit)

### 🔹 Basic commands:

| Command | Action               |
| ------- | -------------------- |
| `i`     | Insert mode          |
| `Esc`   | Back to command mode |
| `:w`    | Save                 |
| `:q`    | Quit                 |
| `:wq`   | Save & quit          |
| `:q!`   | Quit without saving  |

---

## 📁 `mkdir` — Create Directory

Creates folders.

```bash
mkdir folder_name
```

### 🔹 Multiple folders:

```bash
mkdir dir1 dir2 dir3
```

### 🔹 Nested folders:

```bash
mkdir -p parent/child/grandchild
```

### 🔹 With permissions:

```bash
mkdir -m 755 myfolder
```

---

## 📄 `touch` — Create File

Creates an empty file or updates timestamp.

```bash
touch file.txt
```

---

## 📂 `cd` — Change Directory

Move between directories.

```bash
cd folder_name
```

### 🔹 Shortcuts:

```bash
cd ..   # go back
cd ~    # home directory
cd /    # root directory
```

---

## ❌ `rm` — Remove Files/Directories

Deletes files permanently.

```bash
rm file.txt
```

### 🔹 Options:

```bash
rm -r folder   # remove directory recursively
rm -f file     # force delete
```

⚠️ No recycle bin — use carefully.

---

## 📁 `rmdir` — Remove Empty Directory

Deletes only empty folders.

```bash
rmdir folder_name
```

---

# 🔑 Quick Summary Table

| Command | Purpose                       |
| ------- | ----------------------------- |
| `pwd`   | Show current directory        |
| `ls`    | List files and folders        |
| `cat`   | View file content             |
| `less`  | View large files page by page |
| `vi`    | Edit files                    |
| `mkdir` | Create directories            |
| `touch` | Create files                  |
| `cd`    | Change directory              |
| `rm`    | Delete files/folders          |
| `rmdir` | Delete empty folders          |















# 🔹 2. Basic Idea of Permissions

Every file/folder has **3 types of users**:

* **u (user)** → owner
* **g (group)** → group members
* **o (others)** → everyone else

And **3 types of permissions**:

* **r (read)** → view content
* **w (write)** → modify
* **x (execute)** → run file / access folder

---

## 🔹 2. Check Permissions

Use:

```bash
ls -l
```

Example output:

```bash
-rwxr-xr-- 1 user user 1234 Apr 22 file.sh
```

Breakdown:

```
-rwxr-xr--
 ||| ||| ||
 ||| ||| └─ others (r--)
 ||| └──── group (r-x)
 └──────── user (rwx)
```

---

## 🔹 3. Change Permissions with `chmod`

### 👉 Method 1: Symbolic (easy to read)

```bash
chmod u+x file.sh
```

Add execute permission to user.

More examples:

```bash
chmod g-w file.txt     # remove write from group
chmod o+r file.txt     # give read to others
chmod u+rwx file.sh    # full access to user
chmod a+x script.sh    # give execute to everyone
```

---

### 👉 Method 2: Numeric (very common)

Each permission has a number:

* r = 4
* w = 2
* x = 1

Add them:

* 7 = rwx
* 6 = rw-
* 5 = r-x
* 4 = r--

Example:

```bash
chmod 755 file.sh
```

Meaning:

* user = 7 (rwx)
* group = 5 (r-x)
* others = 5 (r-x)

More examples:

```bash
chmod 644 file.txt   # rw-r--r--
chmod 777 file.sh    # full access (not recommended ⚠️)
chmod 600 secret.txt # only owner can read/write
```

---

## 🔹 4. Change Ownership with `chown`

```bash
chown user file.txt
```

Change user + group:

```bash
chown user:group file.txt
```

Example:

```bash
chown junaid:developers project.txt
```

---

## 🔹 5. Change Group Only (`chgrp`)

```bash
chgrp developers file.txt
```

---

## 🔹 6. Special Tips (Important 🔥)

* For **folders**:

  * `x` = permission to enter the folder
* Use `-R` for recursive:

```bash
chmod -R 755 myfolder
```

---

## 🔹 7. Quick Cheat Sheet

| Command           | Meaning         |
| ----------------- | --------------- |
| `chmod 755 file`  | rwxr-xr-x       |
| `chmod 644 file`  | rw-r--r--       |
| `chmod +x file`   | make executable |
| `chown user file` | change owner    |

---



