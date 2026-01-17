# Bandit Learning

**Practical Linux Handling – Beginner to Intermediate**

#### Objective

This document describes the learning process through the **Bandit wargame**, focusing on essential **Linux command-line skills**, SSH access, file handling, and filesystem exploration.
Each level introduces a real-world Linux concept commonly used in **system administration, DevOps, and cloud engineering**.



#### Level 0 – SSH Connection Basics

#### Lesson: Connect to a Remote Server via SSH

SSH (Secure Shell) is used to securely connect to a remote Linux server.

#### Command Syntax

```bash
ssh -p <port_number> <user>@<ip_address>
```

#### Notes

* The **default SSH port** is `22`
* If the server uses a **custom port**, it must be explicitly specified

**Example**

```bash
ssh -p 7770 bandit0@127.0.0.1
```



#### Bonus: How to Change the SSH Port (4 Steps)

1. **Choose a port number**
   Range: `0 – 65535`
   Example: `7770`

2. **Allow the port through the firewall**

```bash
sudo ufw allow 7770
```

3. **Edit the SSH configuration file**

```bash
sudo nano /etc/ssh/sshd_config
```

Change:

```text
Port 22
```

To:

```text
Port 7770
```

4. **Restart the SSH service**

```bash
sudo systemctl restart ssh
```



#### Bandit Level 0 – Reading a File

#### Goal

Read the content of the `readme` file inside the Bandit home directory.

#### Command

```bash
cat readme
```

#### Output

```
The password you are looking for is:
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```



#### Level 1 – Files with Dashed Filenames (`-`)

#### Lesson: Handling Filenames Starting with `-`

Files beginning with `-` are interpreted by Linux commands as **options**, not filenames.

#### Problem

```bash
cat -file
```

This causes errors because `cat` expects an option.

#### Solution

Use a **relative path (`./`)** to explicitly reference the file.

#### Bandit Level 1 Command

```bash
cat ./-
```

#### Output

```
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```



#### Level 2 – Files with Spaces and Dashes

#### Lesson: Special Characters in Filenames

* **Spaces** confuse the shell → use **quotes** or **escaping**
* **Leading dashes (`-`)** → use `--` to stop option parsing

#### Examples

```bash
cat "My File.txt"
cat My\ File.txt
cat -- "--spaces in this filename--"
```

#### Bandit Level 2 Command

```bash
cat -- "--spaces in this filename--"
```

#### Output

```
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```



#### Level 3 – Hidden Files

#### Lesson: Listing Hidden Files

Hidden files start with `.` and are not visible with a simple `ls`.

#### Commands

```bash
ls -la
ls -al
```

#### Bandit Level 3 Output

```
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```



#### Level 4 – Finding Human-Readable Files

#### Lesson: Using `find` and Wildcards

Objectives:

* Navigate directories using `cd`
* Identify human-readable files
* Handle filenames starting with `-`
* Use `*` to represent all files

#### Commands

```bash
find -- *
cat -- "-file07"
```

#### Output

```
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```



#### Level 5 – File Search by Size

#### Lesson: Advanced File Filtering with `find`

Search for:

* Regular files
* Exact file size

#### Command

```bash
find . -type f -size 1033c
```

#### Read the File

```bash
cat <filename>
```

#### Output

```
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```



#### Key Skills Learned

* Secure SSH access
* Linux filesystem navigation
* File permission & visibility
* Handling special filenames
* Using `find` for real-world system inspection



#### Relevance for DevOps & Cloud Engineering

These skills are foundational for:

* Linux server administration
* Debugging production systems
* CI/CD pipelines
* Cloud VM management
* Kubernetes & container environments

