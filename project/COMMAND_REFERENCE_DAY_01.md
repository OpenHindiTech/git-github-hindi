# COMMAND_REFERENCE_DAY_01.md

# OpenHindiTech - Command Reference (Day 01)

## Purpose
This document explains every command used during Day 01 with syntax, meaning, examples, and common mistakes.

---

# 1. `git --version`

## Purpose
Verify that Git is installed.

```bash
git --version
```

Expected Output:

```text
git version 2.x.x
```

---

# 2. `mkdir`

Creates a new directory.

```bash
mkdir docs
```

---

# 3. `mkdir -p`

Creates parent directories if they don't already exist.

```bash
mkdir -p ~/OpenHindiTech
```

---

# 4. `pwd`

Shows the current working directory.

```bash
pwd
```

---

# 5. `ls`

Lists files and folders.

```bash
ls
```

---

# 6. `tree`

Displays the directory structure.

```bash
tree
```

---

# 7. `git clone`

Downloads a remote repository.

```bash
git clone https://github.com/OpenHindiTech/git-github-hindi.git
```

---

# 8. `git status`

Shows repository status.

```bash
git status
```

Possible states:
- Working tree clean
- Untracked files
- Modified files
- Changes to be committed

---

# 9. `touch`

Creates a new file.

```bash
touch docs/README.md
```

Git tracks files—not empty folders.

---

# 10. `git add`

Moves changes to the staging area.

```bash
git add .
```

`.` means the current directory.

---

# 11. `git commit`

Creates a snapshot.

```bash
git commit -m "Add initial project structure"
```

`-m` = commit message.

---

# 12. `git config`

Configure Git identity.

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

Verify:

```bash
git config --global --list
```

---

# 13. `ssh-keygen`

Generate an SSH key.

```bash
ssh-keygen -t ed25519 -C "your@email.com"
```

Parameters:
- `-t` → algorithm
- `ed25519` → recommended key type
- `-C` → comment (usually your email)

---

# 14. `cat`

Display file contents.

```bash
cat ~/.ssh/id_ed25519_personal.pub
```

Used to copy the public key.

---

# 15. `ssh -T`

Test SSH authentication.

```bash
ssh -T git@github.com
```

Expected:

```text
Hi <username>! You've successfully authenticated...
```

---

# 16. `git remote -v`

Display configured remotes.

```bash
git remote -v
```

---

# 17. `git remote set-url`

Switch from HTTPS to SSH.

```bash
git remote set-url origin git@github.com:OpenHindiTech/git-github-hindi.git
```

---

# 18. `git push`

Upload commits to GitHub.

```bash
git push origin main
```

Breakdown:

- `git` → Git program
- `push` → Upload commits
- `origin` → Remote repository
- `main` → Branch name

Syntax:

```text
git push <remote> <branch>
```

Common mistake:

❌ `git push main`

✅ `git push origin main`

---

# Day 01 Command Flow

```text
git clone
   ↓
git status
   ↓
touch
   ↓
git add
   ↓
git commit
   ↓
git push
```
