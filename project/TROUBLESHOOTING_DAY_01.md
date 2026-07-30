# TROUBLESHOOTING_DAY_01.md

# OpenHindiTech - Troubleshooting Guide (Day 01)

This document contains the real problems we faced while setting up Git and GitHub and how we solved them.

---

# Issue 1 - Git Ignored Empty Folders

## Problem

After creating folders, `git status` showed:

```text
nothing to commit
working tree clean
```

## Root Cause

Git tracks files, not empty directories.

## Solution

Create a file inside each folder.

```bash
touch docs/README.md
touch assets/README.md
touch examples/README.md
```

## Prevention

Always keep a README.md or `.gitkeep` inside empty folders.

---

# Issue 2 - Author identity unknown

## Error

```text
Author identity unknown
fatal: unable to auto-detect email address
```

## Root Cause

Git username and email were not configured.

## Solution

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Verify

```bash
git config --global --list
```

---

# Issue 3 - Password authentication is not supported

## Error

```text
remote: Invalid username or token.
Password authentication is not supported.
```

## Root Cause

GitHub removed password authentication for Git over HTTPS.

## Solution

- Configure SSH authentication.
- Change the repository remote from HTTPS to SSH.

Check remote:

```bash
git remote -v
```

Change remote:

```bash
git remote set-url origin git@github.com:OpenHindiTech/git-github-hindi.git
```

---

# Issue 4 - Company SSH Key vs Personal SSH Key

## Observation

The system already had SSH keys associated with the company environment.

## Risk

Using the same key for company and personal accounts can create confusion.

## Best Practice

Maintain separate SSH keys.

Example:

```
~/.ssh/id_ed25519_company
~/.ssh/id_ed25519_personal
```

---

# Issue 5 - SSH Key Save Failed

## Error

```text
Saving key "~/.ssh/id_ed25519_personal" failed:
No such file or directory
```

## Root Cause

`~` was entered inside the interactive prompt.

## Solution

Use the full path.

Example:

```text
/home/username/.ssh/id_ed25519_personal
```

---

# Issue 6 - SSH Authentication Test

Command

```bash
ssh -T git@github.com
```

Expected

```text
Hi username!
You've successfully authenticated...
```

If this does not work:

- Verify the public key is added to GitHub.
- Check the correct key is loaded.
- Verify the remote URL uses SSH.

---

# Issue 7 - Push Still Used HTTPS

## Symptom

Even after adding an SSH key, `git push` still asked for HTTPS authentication.

## Root Cause

The repository remote was still configured with an HTTPS URL.

## Fix

```bash
git remote -v
```

If you see:

```text
https://github.com/...
```

Switch to:

```bash
git remote set-url origin git@github.com:OpenHindiTech/git-github-hindi.git
```

Verify:

```bash
git remote -v
```

You should now see:

```text
git@github.com:OpenHindiTech/git-github-hindi.git
```

---

# Best Practices

- Configure Git before the first commit.
- Prefer SSH over HTTPS.
- Never share your private SSH key.
- Keep company and personal SSH keys separate.
- Commit small, meaningful changes.
- Use clear commit messages.

---

# Day 01 Lessons Learned

✓ Git tracks files, not folders.

✓ Configure Git identity before committing.

✓ SSH is the recommended authentication method.

✓ Always verify your remote URL.

✓ Read error messages carefully—they usually tell you the solution.

---

# Quick Checklist

- [x] Git Installed
- [x] Git Configured
- [x] Repository Cloned
- [x] Files Added
- [x] Commit Created
- [x] SSH Configured
- [x] Remote Changed to SSH
- [x] First Push Successful
