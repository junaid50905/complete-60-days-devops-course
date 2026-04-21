# 🐧 Linux Basic Commands Cheat Sheet

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


