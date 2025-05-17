**Bandit Wargame Walkthrough (OverTheWire) by Mpho Lekhuleni**

---

> ![Banner](https://raw.githubusercontent.com/yourusername/bandit-walkthrough/main/assets/banner.png)

---

### 📘 Overview

This project documents my personal walkthrough of the [Bandit](https://overthewire.org/wargames/bandit/) wargame hosted by OverTheWire. The Bandit wargame is a Linux-based learning environment designed to help newcomers understand basic shell commands, file system navigation, file manipulation, and terminal-based problem solving. This hands-on challenge is a fantastic starting point for anyone looking to build a solid foundation in Linux system usage and command-line interface (CLI) tools.

---

### 💡 Skills Demonstrated

* Linux file system navigation and structure
* Use of commands like `cat`, `ls`, `cd`, `find`, `file`, `grep`, `sort`, `uniq`
* Understanding of file types, permissions, hidden files, and special characters
* Use of search tools to filter and extract specific data
* Application of basic logic and troubleshooting in a CLI environment

---

### ⚙️ Getting Started

To reproduce the walkthrough:

1. Go to: [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)
2. Use a terminal (Linux, macOS, or Git Bash on Windows).
3. Connect via SSH:

   ```bash
   ssh bandit0@bandit.labs.overthewire.org -p 2220
   ```
4. Follow the walkthrough level by level.

---

### 🧽 Walkthrough Levels

#### Level 0 → Level 1

**Goal:** SSH into the Bandit server.

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
cat readme
```

* `ssh`: Secure shell command to log in to a remote server.
* `cat`: Outputs the contents of a file.

**Password for bandit1:** `[REDACTED]`

---

#### Level 1 → Level 2

**Goal:** Read a file named `-`.

```bash
cat ./-
```

* `./-`: Specifies the file named `-` in the current directory. The `./` avoids confusion with command-line options.

**Password for bandit2:** `[REDACTED]`

---

#### Level 2 → Level 3

**Goal:** Read a file with spaces in the filename.

```bash
cat "spaces in this filename"
```

* `"..."`: Quotes allow reading filenames with spaces.

**Password for bandit3:** `[REDACTED]`

---

#### Level 3 → Level 4

**Goal:** Read a hidden file in the `inhere` directory.

```bash
cd inhere
ls -a
cat .hidden
```

* `ls -a`: Lists all files including hidden ones.

**Password for bandit4:** `[REDACTED]`

---

#### Level 4 → Level 5

**Goal:** Identify and read the only human-readable file.

```bash
cd inhere
file *
cat ./-file07
```

* `file *`: Shows the file type of each item.

**Password for bandit5:** `[REDACTED]`

---

#### Level 5 → Level 6

**Goal:** Find file that is 1033 bytes, readable, and not executable.

```bash
find . -type f -size 1033c ! -executable -exec file {} \;
cat ./maybehere07/.file2
```

* `find`: Locates files matching specific criteria.
* `! -executable`: Excludes executable files.

**Password for bandit6:** `[REDACTED]`

---

#### Level 6 → Level 7

**Goal:** Find a file with specific user/group ownership and size.

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```

* `2>/dev/null`: Hides permission errors from cluttering output.

**Password for bandit7:** `[REDACTED]`

---

#### Level 7 → Level 8

**Goal:** Find the line containing `millionth` in `data.txt`.

```bash
grep millionth data.txt
```

* `grep`: Searches text for a matching pattern.

**Password for bandit8:** `[REDACTED]`

---

#### Level 8 → Level 9

**Goal:** Find the line that occurs only once in `data.txt`.

```bash
sort data.txt | uniq -u
```

* `sort`: Organizes lines alphabetically for `uniq` to compare consecutive lines.
* `uniq -u`: Prints only unique lines that appear once.

**Password for bandit9:** `[REDACTED]`

---

#### Level 9 → Level 10

**Goal:** Extract readable strings with `==` from `data.txt`.

```bash
strings data.txt | grep '=='
```

* `strings`: Extracts human-readable text from binary files.
* `grep '=='`: Filters lines containing `==`.

**Password for bandit10:** `[REDACTED]`

---

#### Level 10 → Level 11

**Goal:** Decode a Base64-encoded file.

```bash
base64 -d data.txt
```

* `base64 -d`: Decodes base64-encoded content.

**Password for bandit11:** `[REDACTED]`

---

### 📷 Screenshots *(Optional)*

Include screenshots of your terminal at each level (optional but visually valuable for LinkedIn/GitHub).

---

### 📘 Lessons Learned

* Deepened understanding of Linux command-line tools.
* Improved problem-solving and command chaining.
* Gained hands-on experience with file searching and filtering.
* Reinforced best practices in shell navigation and permissions.

---

### 🔭 Future Plans

* Continue with more levels of Bandit.
* Explore other OverTheWire games like Narnia or Leviathan.
* Automate CLI tasks with Bash scripts.
* Apply lessons to CTFs (e.g., TryHackMe, Hack The Box).

---

### 📣 Sharing Progress

* Share progress every 5–10 levels on **LinkedIn**.
* Publish this as a GitHub README.
* Tag relevant skills and platforms (Linux, InfoSec, OverTheWire, CLI).

---

### 📄 License

This walkthrough is publicly available under the [MIT License](https://opensource.org/licenses/MIT). Feel free to fork, contribute, or build your own documentation based on it.

---

**Author:** Mpho Lekhuleni
**LinkedIn:** [https://www.linkedin.com/in/mpho-lekhuleni](https://www.linkedin.com/in/mpho-lekhuleni)
**Project:** Bandit Wargame Linux Terminal Walkthrough
**Platform:** [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/)
