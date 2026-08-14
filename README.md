# OverTheWire Bandit – Levels 0 to 6

This repository documents my progress while solving the **OverTheWire Bandit Wargame** using a Kali Linux virtual machine.

I practiced basic Linux commands, file handling, navigation, and searching for specific files through the command line.

## Environment

* Kali Linux
* VMware Workstation
* OverTheWire Bandit
* SSH
* Linux Command Line

---

## Level 0 → Level 1

### Connection

I started by connecting to the Bandit server using SSH:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

The password provided for Level 0 was:

```text
bandit0
```

### Solution

First, I used `ls` to list the existing files in the home directory.

```bash
ls
```

The `readme` file was displayed.

Then, I used the `cat` command to view its contents:

```bash
cat readme
```

The output contained the password required to access the next level.

---

## Level 1 → Level 2

After getting the password from the previous level, I exited the server using:

```bash
exit
```

Then I connected to the next level using SSH and the password obtained from Level 0 → Level 1.

### Solution

I used:

```bash
ls
```

to list the files in the home directory.

The file name was:

```text
-
```

Since the filename is `-`, I used:

```bash
cat ./-
```

The `cat` command displayed the contents of the file, giving me the password for the next level.

---

## Level 2 → Level 3

I exited the previous server using:

```bash
exit
```

Then I logged into the next server using the password obtained from the previous level.

### Solution

First, I used:

```bash
ls
```

The filename contained spaces:

```text
--spaces in this filename--
```

Because the filename contains spaces and starts with `-`, using `cat` directly caused an error.

I used:

```bash
cat -- "--spaces in this filename--"
```

The command displayed the contents of the file and gave me the password for the next level.

---

## Level 3 → Level 4

I exited the previous server:

```bash
exit
```

Then I logged into the next level using the password obtained from the previous level.

### Solution

In this level, the file we were looking for was inside the `inhere` directory.

I moved into the directory using:

```bash
cd inhere
```

Then I used:

```bash
ls -la
```

The `-a` option allowed me to see hidden files.

I found the hidden file:

```text
.hidden-from-you
```

Then I used:

```bash
cat .hidden-from-you
```

The contents of the file gave me the password for the next level.

---

## Level 4 → Level 5

I exited the previous server:

```bash
exit
```

Then I logged into the next server using the password obtained from the previous level.

### Solution

I moved to the `inhere` directory:

```bash
cd inhere
```

Then I used:

```bash
ls -la
```

This showed multiple files.

The challenge required finding the file containing ASCII text, so I used the `file` command:

```bash
file ./*
```

The command showed the type of each file.

The file identified as **ASCII text** was:

```text
./-file07
```

I then used:

```bash
cat ./-file07
```

This displayed the password for the next level.

---

## Level 5 → Level 6

I exited the previous server:

```bash
exit
```

Then I logged into the next server using the password obtained from the previous level.

### Solution

I moved to the `inhere` directory:

```bash
cd inhere
```

Then I used:

```bash
ls -la
```

There were multiple directories and files.

The level required searching for a file with a specific size: **1033 bytes**.

Instead of checking every file manually, I used the `find` command:

```bash
find . -type f -size 1033c
```

This returned the location of the file with the required size.

After getting the filename, I used the `cat` command to display its contents:

```bash
cat <file_path>
```

The output gave me the password required for the next level.

---

## Level 6 → Level 7

The next level continues the practice of searching for files based on specific properties.

I will add the solution and screenshot here after completing the level.

---

## Commands Practiced

Throughout these levels, I practiced the following Linux commands:

```text
ssh
ls
ls -la
cat
cd
exit
file
find
```

### What I Practiced

* Connecting to a remote Linux server using SSH
* Listing files and directories
* Viewing hidden files
* Reading file contents
* Working with filenames containing spaces
* Working with filenames beginning with `-`
* Identifying file types
* Searching for files using specific properties
* Navigating between directories
* Using passwords obtained from previous levels to access the next level

---

## Progress

| Level       | Status         |
| ----------- | -------------- |
| Level 0 → 1 | ✅ Completed    |
| Level 1 → 2 | ✅ Completed    |
| Level 2 → 3 | ✅ Completed    |
| Level 3 → 4 | ✅ Completed    |
| Level 4 → 5 | ✅ Completed    |
| Level 5 → 6 | ✅ Completed    |
| Level 6 → 7 | 🔄 In Progress |

---

## Screenshots

Screenshots of my solutions are included in this repository as evidence of my hands-on practice in the Bandit Wargame.

I will continue updating this repository as I complete more levels.
