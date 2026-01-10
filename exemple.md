

# 📁 mini-foundations/ (exemples détaillés)

---

## 📄 README.md (racine)

**Objectif du repo**

```md
# Mini Foundations – DevOps & Cloud Journey

This folder contains my foundational learning journey in DevOps and Cloud computing.
It covers core concepts such as SDLC, Linux, Git, Networking, and Cloud models.

Each section includes:
- Key concepts
- Practical notes
- Hands-on labs
- Personal summaries

This foundation prepares me for real-world DevOps projects such as
Two-Tier and Three-Tier Cloud Architectures.
```

---

## 📁 sdlc/

### 📄 sdlc-notes.md

**Exemple de contenu**

```md
# Software Development Life Cycle (SDLC)

## 1. Planning
- Identify business requirements
- Define project scope
- Choose technology stack

Example:
A company wants a web app to manage users.

## 2. Development
- Developers write code
- Version control using Git

## 3. Testing
- Unit tests
- Integration tests
- Manual and automated testing

## 4. Deployment
- Application deployed to servers
- CI/CD pipelines used

## 5. Maintenance
- Monitoring
- Bug fixes
- Performance optimization

## DevOps Role in SDLC
DevOps ensures fast, reliable, and automated delivery using CI/CD,
Infrastructure as Code, and monitoring tools.
```

---

## 📁 linux/

### 📄 commands.md

```md
# Essential Linux Commands

## File & Directory Management
- ls : list files
- cd : change directory
- mkdir : create directory
- rm : delete files

## System Monitoring
- top : view running processes
- df -h : disk usage
- free -m : memory usage

## Permissions
- chmod
- chown
- sudo
```

---

### 📄 file-system-lab.md

```md
# Linux File System Lab

## Objective
Understand Linux directory structure.

## Steps
1. Navigate to root directory `/`
2. Explore `/etc`, `/var`, `/home`
3. Create a test directory:
   mkdir devops_lab
4. Create files and change permissions

## Outcome
Learned how Linux organizes system and user files.
```

---

### 📄 bandit-writeup.md

```md
# OverTheWire Bandit Write-up

## Level 0 → Level 1
Used SSH to connect:
ssh bandit0@bandit.labs.overthewire.org -p 2220

## Skills Learned
- SSH access
- File permissions
- Reading hidden files
- Using grep, find, cat
```

👉 **Très bon signal DevOps**, surtout pour les recruteurs.

---

## 📁 git/

### 📄 git-basics.md

```md
# Git Basics

## Common Commands
- git init
- git clone
- git status
- git add
- git commit
- git push

## Workflow
1. Create branch
2. Make changes
3. Commit
4. Open Pull Request
```

---

### 📄 branching-notes.md

```md
# Git Branching Strategy

## Feature Branching
- main: production-ready code
- dev: integration branch
- feature/*: new features

## Benefits
- Isolated development
- Safer deployments
- Team collaboration
```

---

## 📁 networking/

### 📄 networking-basics.md

```md
# Networking Basics

## Key Concepts
- IP Address
- Subnet
- Gateway
- DNS
- HTTP vs HTTPS

## Example
Client → Internet → Load Balancer → Application Server → Database

## DevOps Importance
Networking is essential for cloud architecture, security, and scaling.
```

---

## 📁 cloud/

### 📄 cloud-models.md

```md
# Cloud Computing Models

## Service Models
- IaaS: EC2, Virtual Machines
- PaaS: Heroku, App Engine
- SaaS: Gmail, Google Docs

## Deployment Models
- Public Cloud
- Private Cloud
- Hybrid Cloud

## Benefits
- Scalability
- Cost optimization
- High availability
```

---

## 📄 learning-summary.md

```md
# Learning Summary

Through this mini-foundations module, I gained:
- Strong understanding of SDLC and DevOps practices
- Hands-on Linux and Git experience
- Networking fundamentals for cloud systems
- Clear understanding of cloud service models

This foundation enables me to build real-world DevOps projects
such as Two-Tier and Three-Tier cloud applications.
```

