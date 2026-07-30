# INTERVIEW_QNA_DAY_01.md

# OpenHindiTech - Git & GitHub Interview Questions (Day 01)

**Level:** Beginner

---

## Q1. What is Git?

**Answer:**
Git is a Distributed Version Control System (DVCS) used to track changes in source code and collaborate with multiple developers.

---

## Q2. What is GitHub?

**Answer:**
GitHub is a cloud platform that hosts Git repositories and provides collaboration features like Pull Requests, Issues, Actions, and Discussions.

---

## Q3. Difference between Git and GitHub?

| Git | GitHub |
|------|---------|
| Version control software | Cloud hosting platform |
| Works locally | Works online |
| Tracks code changes | Hosts Git repositories |

---

## Q4. What is a Repository?

**Answer:**
A repository (repo) is a project folder tracked by Git that contains files, folders, commit history, and branches.

---

## Q5. What is a Commit?

**Answer:**
A commit is a snapshot of your staged changes saved in the Git history.

---

## Q6. Why do we use `git add` before `git commit`?

**Answer:**
`git add` moves changes to the staging area. Only staged changes are included in a commit.

Flow:

Working Directory → Staging Area → Commit

---

## Q7. What does `git status` do?

**Answer:**
It shows the current state of your repository including untracked, modified, staged, and committed files.

---

## Q8. Does Git track empty folders?

**Answer:**
No. Git tracks files, not empty directories.

---

## Q9. What is SSH?

**Answer:**
SSH (Secure Shell) is a secure authentication method that uses a public/private key pair.

---

## Q10. What is the difference between Public Key and Private Key?

**Public Key**
- Shared with GitHub
- Safe to share

**Private Key**
- Stays on your computer
- Never share it

---

## Q11. Why is SSH preferred over HTTPS?

**Answer:**
- More secure
- No password for every push
- Industry standard

---

## Q12. What is `origin`?

**Answer:**
`origin` is the default name of the remote repository created during `git clone`.

---

## Q13. What is `main`?

**Answer:**
`main` is the default branch name in modern Git repositories.

---

## Q14. Explain `git push origin main`.

- `git` → Git program
- `push` → Upload commits
- `origin` → Remote repository
- `main` → Branch to push

---

## Q15. Why did `Author identity unknown` occur?

**Answer:**
Git username and email were not configured.

Fix:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

## Q16. Why did HTTPS push fail?

**Answer:**
GitHub no longer supports password authentication for Git operations over HTTPS.

Solution:
Use SSH or a Personal Access Token (PAT).

---

## Quick Revision

- Git = Version Control
- GitHub = Hosting Platform
- Commit = Snapshot
- Repository = Project
- Origin = Remote
- Main = Default branch
- SSH = Secure authentication
