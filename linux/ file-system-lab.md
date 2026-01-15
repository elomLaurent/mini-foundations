# Linux File System Lab (WSL)

#### Environment
- Host OS: Windows 10/11
- Linux Distro: Ubuntu 22.04 (WSL2)
- Terminal: Windows Terminal / Ubuntu WSL



#### Objective
Understand the Linux filesystem hierarchy and how system and user files are organized.



#### Why this matters
Most cloud servers and DevOps environments run Linux.  
Understanding the Linux file system is critical for:

- System troubleshooting and administration
- Application deployment
- Log analysis and monitoring
- Security and permissions management
- CI/CD and automation workflows

#### Why Linux mastery is essential for DevOps
Linux is the **foundation of modern DevOps**. Mastering it allows you to:

1. **Deploy and maintain applications** reliably on servers (Linux dominates cloud infrastructure).  
2. **Automate tasks efficiently** using Bash scripts, Ansible, Terraform, Docker, Kubernetes.  
3. **Debug and troubleshoot** production issues quickly by understanding logs, processes, and file permissions.  
4. **Secure the environment**, controlling who can read, write, or execute files and managing services safely.  
5. **Think like a DevOps engineer**, understanding server architecture, reproducing environments, and documenting processes.

> In short: mastering Linux is **the universal language of DevOps**.


#### Standards Reference
This lab follows the **Filesystem Hierarchy Standard (FHS)** defined by the Linux Foundation.  
Reference: https://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html


#### Prerequisites
- Basic command-line knowledge
- WSL2 installed
- Ubuntu distribution configured


#### Core Linux Directories Overview

| Directory | Purpose |
|--------|--------|
| `/` | Root directory (top of the filesystem) |
| `/etc` | System-wide configuration files |
| `/var` | Logs and variable data |
| `/home` | User home directories |
| `/bin` | Essential system binaries |
| `/usr` | User applications and utilities |
| `/tmp` | Temporary files |



## Lab Steps

#### 1. Access Linux root filesystem

```bash
cd /
ls
````

Observation:

* All Linux directories originate from `/`
* This is different from Windows drive-based structure



#### 2. Explore critical system directories

#### `/etc` – Configuration files

```bash
ls /etc
```

Contains:

* System configuration
* Service configuration
* Network and user settings

⚠️ Warning: Do **NOT** edit files here unless you know what you are doing.



#### `/var` – Logs and runtime data

```bash
ls /var
ls /var/log
```

Common DevOps use:

* Debug application errors
* Analyze server issues
* Monitor system behavior



#### `/home` – User directories

```bash
ls /home
```

Each user has a personal directory here
Best practice: **store application and lab files inside your home directory**



##### 3. Create a DevOps lab workspace

```bash
mkdir ~/devops_lab
cd ~/devops_lab
pwd
```

This directory will contain:

* Practice files
* Scripts
* Experiments


##### 4. Create files

```bash
touch file1.txt file2.txt
ls
```



#### 5. View file permissions

```bash
ls -l
```

Example output:

```text
-rw-r--r-- 1 user user 0 file1.txt
```

Permission structure:

* Owner (rw-)
* Group (r--)
* Others (r--)


#### 6. Modify file permissions

```bash
chmod 644 file1.txt
chmod 600 file2.txt
ls -l
```

Why this matters:

* Controls who can read, write, or execute files
* Critical for system security



#### 7. WSL-specific filesystem behavior

```bash
ls /mnt
ls /mnt/c
```

Explanation:

* `/mnt/c` maps to Windows `C:\`
* Allows interaction between Windows and Linux files

Best practice:

* Run Linux tools on Linux files
* Avoid running heavy Linux processes on `/mnt/c`


#### Validation Checklist

* Can explain the purpose of `/etc`, `/var`, `/home`
* Can create directories and files
* Can read and change file permissions
* Understands Linux vs Windows filesystem differences
* Understands why mastering Linux is critical for DevOps


#### Common Errors & Solutions

| Error             | Cause                | Solution                |
| ----------------- | -------------------- | ----------------------- |
| Permission denied | Restricted directory | Use `sudo` carefully    |
| Command not found | Incorrect PATH       | Verify command spelling |
| File not visible  | Wrong directory      | Use `pwd` and `ls`      |


#### Best Practices

* Never work as root unless required
* Keep labs inside `/home`
* Back up configuration files before editing
* Follow FHS standards

#### Outcome

After completing this lab, I am able to:

- Understand the Linux filesystem hierarchy and its standards (FHS)
- Navigate safely through critical Linux directories
- Create and manage files and directories
- Interpret and modify Linux file permissions
- Work confidently with Linux inside a Windows environment using WSL2
- Explain why Linux mastery is essential for DevOps engineering

This lab provides a solid foundation for further learning in Linux administration, automation, containerization, and cloud infrastructure.

