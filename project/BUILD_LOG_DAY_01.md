# BUILD_LOG_DAY_01.md

# OpenHindiTech - Build Log (Day 01)

**Date:** 29 July 2026

## Session Goal

Create the OpenHindiTech organization, initialize the first Git repository, configure Git, configure SSH authentication, and perform the first successful commit and push.

---

# 1. Project Vision

We decided to build **OpenHindiTech**, an open-source platform that teaches Git & GitHub in Hindi with practical examples instead of only theory.

Goals:

- Hindi + Technical English explanations
- Real terminal output
- Industry best practices
- Interview questions
- Troubleshooting guides
- Hands-on labs

---

# 2. GitHub Organization

Organization Name:

`OpenHindiTech`

Reason:
- Keep all repositories under one identity.
- Allow future contributors.
- Make the project look professional.

---

# 3. First Repository

Repository Name:

`git-github-hindi`

Repository Type:

Public

License:

MIT License

Why MIT?

- Anyone can learn
- Anyone can contribute
- Anyone can modify
- Easy for open-source projects

---

# 4. Clone Repository

Command

```bash
git clone https://github.com/OpenHindiTech/git-github-hindi.git
```

Why?

Downloads the remote repository to your local machine.

---

# 5. Workspace

```bash
mkdir -p ~/OpenHindiTech
cd ~/OpenHindiTech
```

Reason:
Keep all projects in one place.

---

# 6. Create Project Structure

```bash
mkdir docs
mkdir assets
mkdir examples
mkdir .github
```

---

# 7. First Lesson

Command

```bash
git status
```

Output:

```
nothing to commit
working tree clean
```

Why?

Git ignores empty folders.

Important Concept:

> Git tracks files, not empty directories.

Solution:

```bash
touch docs/README.md
touch assets/README.md
touch examples/README.md
```

---

# 8. Stage Files

```bash
git add .
```

Meaning:

Move changes from Working Directory to Staging Area.

---

# 9. Commit

Attempt:

```bash
git commit -m "Add initial project structure"
```

Error:

```
Author identity unknown
```

Reason:

Git didn't know who the author was.

Solution:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Verify:

```bash
git config --global --list
```

---

# 10. HTTPS Push Failed

Error:

```
Password authentication is not supported.
```

Reason:

GitHub no longer accepts account passwords for Git operations.

---

# 11. Existing SSH Keys

Command

```bash
ls -la ~/.ssh
```

Observation:

A company SSH key already existed.

Decision:

Create a separate personal SSH key.

Reason:

Never mix company credentials with personal GitHub.

---

# 12. Create Personal SSH Key

Command

```bash
ssh-keygen -t ed25519 -C "your-personal-email@example.com"
```

When prompted for file:

Use:

```
/home/<username>/.ssh/id_ed25519_personal
```

Do NOT use `~` in the interactive prompt.

---

# 13. View Public Key

```bash
cat ~/.ssh/id_ed25519_personal.pub
```

Copy the output.

---

# 14. Add Key to GitHub

GitHub

Settings

SSH and GPG Keys

New SSH Key

Paste public key

Save

---

# 15. Test SSH

```bash
ssh -T git@github.com
```

Expected:

```
Hi <username>! You've successfully authenticated...
```

---

# 16. Change Remote

Check current remote

```bash
git remote -v
```

Change HTTPS to SSH

```bash
git remote set-url origin git@github.com:OpenHindiTech/git-github-hindi.git
```

Verify again

```bash
git remote -v
```

---

# 17. First Push

```bash
git push origin main
```

Breakdown

- git = Git program
- push = Upload commits
- origin = Remote repository name
- main = Branch name

Syntax

```text
git push <remote> <branch>
```

---

# Commands Practiced

- git clone
- git status
- git add .
- git commit
- git config
- git remote -v
- git remote set-url
- ssh-keygen
- ssh -T
- git push origin main

---

# Common Errors

## Error

Author identity unknown

Fix

Configure Git username and email.

---

## Error

Password authentication is not supported.

Fix

Use SSH authentication.

---

## Error

Git ignored empty folders.

Fix

Create a file inside the folder.

---

# Interview Questions

Q. Does Git track empty folders?

Answer: No.

Q. What is origin?

Answer: Default remote repository name.

Q. What is main?

Answer: Default branch name.

Q. Why use SSH?

Answer: Secure authentication without passwords.

---

# Session Summary

Completed:

- GitHub Organization
- Repository
- Clone
- Folder Structure
- Git Config
- SSH Authentication
- First Commit
- First Push

Next Session:

- Professional README
- Repository structure
- First documentation chapter
