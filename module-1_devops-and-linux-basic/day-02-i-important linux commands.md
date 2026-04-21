Here’s a clear, practical explanation of each Linux command:

---

### 📍 `pwd` (Print Working Directory)

Shows your current location in the filesystem.

```bash
pwd
```

👉 Output example:

```
/home/junaid/projects
```

---

### 📂 `ls` (List)

Lists files and directories in the current directory.

```bash
ls
```

Common variations:

```bash
ls -l   # detailed list (permissions, size, date)
ls -a   # show hidden files (starting with .)
```

---

### 📄 `cat` (Concatenate)

Used to view or combine file contents.

```bash
cat file.txt
```

👉 Displays the content of `file.txt`

You can also combine files:

```bash
cat file1.txt file2.txt > merged.txt
```

---

### 📁 `touch`

Creates a new empty file (or updates timestamp if it exists).

```bash
touch file.txt
```

---

### 📁 `cd` (Change Directory)

Moves you between directories.

```bash
cd folder_name
```

Examples:

```bash
cd ..        # go one level up
cd ~         # go to home directory
cd /         # go to root directory
```

---

### ❌ `rm` (Remove)

Deletes files (and optionally directories).

```bash
rm file.txt
```

⚠️ Be careful — it permanently deletes files.

Useful options:

```bash
rm -r folder   # delete directory and its contents
rm -f file     # force delete without confirmation
```

---

### 📁 `rmdir` (Remove Directory)

Deletes **empty directories only**.

```bash
rmdir folder_name
```

👉 If the directory is not empty, it will fail.

---

### 🔑 Quick Summary

| Command | Purpose                |
| ------- | ---------------------- |
| `pwd`   | Show current directory |
| `ls`    | List files/folders     |
| `cat`   | View file content      |
| `touch` | Create file            |
| `cd`    | Change directory       |
| `rm`    | Delete files/folders   |
| `rmdir` | Delete empty folder    |


