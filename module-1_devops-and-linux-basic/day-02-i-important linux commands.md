
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
ls -l   # detailed list (permissions, size, date) ll do the same thing
ls -a   # show hidden files (starting with .)
```

---

### 📄 `cat` (Concatenate)

Used to view or combine file contents.

```bash
cat file.txt
```

### 📄 `less` (View file content page by page)

`less` is used to **read large files easily** in the terminal without opening them in an editor.

```bash id="q9k2aa"
less file.txt
```

---

### 🔹 Why use `less`?

* Displays content **one screen at a time**
* Faster than `cat` for large files
* Does **not load the whole file at once**

---

### 🔹 Navigation inside `less`

| Key     | Action                   |
| ------- | ------------------------ |
| `Space` | Next page                |
| `b`     | Previous page            |
| `Enter` | Scroll down line by line |
| `/text` | Search forward           |
| `n`     | Next search result       |
| `q`     | Quit                     |

---

### 🔹 Example

```bash id="m8zq0x"
less /var/log/syslog
```

---

---

## ✏️ `vi` (Text Editor)

`vi` is a **powerful terminal-based text editor** used for editing files.

```bash id="v3k1rz"
vi file.txt
```

---

### 🔹 Two main modes in `vi`

1. **Command Mode** (default)
2. **Insert Mode** (for typing)

---

### 🔹 Switching Modes

| Key   | Action                 |
| ----- | ---------------------- |
| `i`   | Enter insert mode      |
| `Esc` | Return to command mode |

---

### 🔹 Basic Commands in `vi`

| Command | Action              |
| ------- | ------------------- |
| `i`     | Start editing       |
| `:w`    | Save file           |
| `:q`    | Quit                |
| `:wq`   | Save and quit       |
| `:q!`   | Quit without saving |

---

### 🔹 Example Workflow

```bash id="2l6c1d"
vi file.txt
```

1. Press `i` → start typing
2. Write content
3. Press `Esc`
4. Type `:wq` → save and exit

---

### 🔥 Difference between `less` and `vi`

| Feature      | `less`     | `vi`       |
| ------------ | ---------- | ---------- |
| Purpose      | View files | Edit files |
| Editing      | ❌ No       | ✅ Yes      |
| Navigation   | Yes        | Yes        |
| Save changes | ❌ No       | ✅ Yes      |

---

### 🔑 Quick Summary

* `less` → view large files safely
* `vi` → edit files directly in terminal

---


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

### 📁 `mkdir` (Make Directory)

Used to create new directories (folders).

---

### 🔹 Basic Usage

```bash
mkdir folder_name
```

👉 Example:

```bash
mkdir projects
```

This creates a folder named `projects` in the current directory.

---

### 🔹 Create Multiple Directories

```bash
mkdir dir1 dir2 dir3
```

---

### 🔹 Create Nested Directories (Important 🔥)

```bash
mkdir -p parent/child/grandchild
```

👉 Example:

```bash
mkdir -p app/controllers/api
```

* `-p` automatically creates all missing parent directories
* Without `-p`, it will throw an error if parent doesn’t exist

---

### 🔹 Set Permissions While Creating

```bash
mkdir -m 755 myfolder
```

---

### ⚠️ Common Errors

* ❌ Folder already exists → `File exists`
* ❌ Missing parent directory (without `-p`)

---

### 🔑 Quick Summary

| Command         | Meaning                 |
| --------------- | ----------------------- |
| `mkdir name`    | Create one folder       |
| `mkdir a b c`   | Create multiple folders |
| `mkdir -p path` | Create nested folders   |
| `mkdir -m 755`  | Set permission          |

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


