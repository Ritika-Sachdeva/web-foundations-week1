# Git & GitHub Guide – Week 1

## Part 1 – Core Git Concepts

### What is Version Control?
Version control is a way to track and manage changes made to files over time.  
It allows developers to go back to an earlier version, compare changes, and work safely in teams without overwriting each other’s work.

### Why is it essential in software development?
- Prevents loss of work
- Keeps a history of changes
- Makes collaboration easier
- Allows rolling back to stable versions if something breaks

### Problems version control solves
- **Tracking changes** – Know who changed what and when
- **Backups** – Easily restore old versions
- **Rollbacks** – Fix mistakes by reverting to an earlier commit
- **Collaboration issues** – Prevent overwriting other people’s code

### What is Git and why do developers use it?
Git is a distributed version control system.  
It keeps a local copy of your project and its history so you can work offline and sync changes later.  
Developers use Git because it’s fast, reliable, and widely supported.

### What is GitHub and how is it different from Git?
GitHub is an online platform for hosting Git repositories.  
Git is the tool that does version control on your computer.  
GitHub provides a central place for sharing, reviewing, and collaborating on code.

### Benefits of version control in solo and team projects
- **Solo projects** – You can track your own changes, undo mistakes, and experiment with new features safely.
- **Team projects** – Everyone can work in their own branch, review each other’s work, and merge only when it’s ready.

### What is a remote repository?
A remote repository is the version of your project hosted online (like on GitHub).  
It’s used to share work with others and keep a backup.

### What is a branch?
A branch is like a separate workspace within your project.  
You can make changes in a branch without affecting the main code.

### Why create feature branches instead of committing directly to main?
- Keeps `main` stable
- Allows safe testing
- Prevents breaking code for everyone else
- Makes reviewing changes easier

### What is a pull request (PR)?
A PR is a request to merge changes from one branch into another.  
In teams, PRs are used to review code, discuss improvements, and ensure everything is correct before merging.

---

## Part 2 – Real GitHub Workflow

1. **Create a new repository** on GitHub (e.g., `web-foundations-week1`).
2. **Clone it locally** using:
   ```bash
   git clone <repo-url>

3. **Create a new branch for your work:**
git checkout -b week1-submission
Add your files:

how-browser-works.md

event-loop-advanced.md

http-api-basics.md

git-github-guide.md

**Commit each file using proper commit messages:**

git add how-browser-works.md
git commit -m "docs: add how-browser-works.md"
Push your branch to GitHub:

git push -u origin week1-submission
Create a pull request:

Base branch: main

Compare branch: week1-submission

PR title: Week 1 Submission – Ritika Sachdeva

PR description: List the files added

## Why This Workflow Matters
- Keeps main clean and production-ready

- Allows safe experimentation in branches

- Makes teamwork more organized

- Tracks history for learning and debugging