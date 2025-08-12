# Git & GitHub Guide – Week 1

## Part 1 – Core Git Concepts

### What is Version Control?
Version control is a way to track and manage changes made to files over time.  
It allows developers to go back to an earlier version, compare changes, and work safely in teams without overwriting each other’s work.

In a software development company building a mobile banking app, multiple developers work on different features simultaneously — one team handles user authentication, another works on transaction processing, and another on the user interface. Version control systems like Git track every change each developer makes, allowing the team to merge their work without conflicts. If a bug is introduced, they can quickly identify which change caused it and revert to a stable version. This system ensures smooth collaboration, prevents loss of work, and maintains a reliable product throughout development.

### Why is it essential in software development?
- Prevents loss of work
- Keeps a history of changes
- Makes collaboration easier
- Allows rolling back to stable versions if something breaks
Example:
If you’re building a website with friends and everyone edits the same file at the same time, without version control you might accidentally overwrite each other’s work. Version control prevents this and lets you undo mistakes easily, like a “save point” in a video game.

### Problems version control solves
- **Tracking changes** – Know who changed what and when
- **Backups** – Easily restore old versions
- **Rollbacks** – Fix mistakes by reverting to an earlier commit
- **Collaboration issues** – Prevent overwriting other people’s code

Tracking changes: Like Google Docs’ revision history, you can see who changed what and when.

Backups: If your computer crashes or file gets deleted, you can restore old versions from the repository.

Rollbacks: If you accidentally add a bug, you can revert the code to the last working version.

Collaboration issues: Like teammates working on different chapters of a book and combining them smoothly.



### What is Git and why do developers use it?
Git is a distributed version control system.  
It keeps a local copy of your project and its history so you can work offline and sync changes later.  
Developers use Git because it’s fast, reliable, and widely supported.

Example:
Git is like having a personal assistant who remembers every change you make to your project locally. You can work offline, commit changes, and when internet is back, sync everything to the shared cloud storage (GitHub). Developers use it because it’s reliable, fast, and flexible.

### What is GitHub and how is it different from Git?
GitHub is an online platform for hosting Git repositories.  
Git is the tool that does version control on your computer.  
GitHub provides a central place for sharing, reviewing, and collaborating on code.

Example:
Git is like the local notebook you carry with you. GitHub is like the library where you put your notebook so others can read, borrow, or contribute to it. Git manages versions locally; GitHub hosts your project online and helps coordinate teamwork.

When you ran commands like git add, git commit, or git checkout -b branch-name — you used Git locally on your computer to manage your project versions and branches.

When you created a repository on GitHub’s website and pushed your branch using git push origin branch-name — you uploaded your local Git repository to GitHub’s servers, making your work accessible online and shareable with others.

### Benefits of version control in solo and team projects
- **Solo projects** – You can track your own changes, undo mistakes, and experiment with new features safely.
- **Team projects** – Everyone can work in their own branch, review each other’s work, and merge only when it’s ready.

Solo projects: Like having a diary where you can track your progress, try new ideas safely, and revert to earlier drafts if needed.

Team projects: Like multiple chefs working in one kitchen but using separate cooking stations (branches) to avoid spoiling the main dish.

### What is a remote repository?
A remote repository is the version of your project hosted online (like on GitHub).  
It’s used to share work with others and keep a backup.

Think of remote repository as a shared online folder (like Google Drive) where your project lives so everyone on the team can access the latest version anytime.

### What is a branch?
A branch is like a separate workspace within your project.  
You can make changes in a branch without affecting the main code.

Example:
Imagine your project is a tree trunk (main branch). A branch is like a smaller branch growing from it where you can try new things without affecting the trunk. Only after it’s tested and good, you attach it back to the trunk.

### Why create feature branches instead of committing directly to main?
- Keeps `main` stable
- Allows safe testing
- Prevents breaking code for everyone else
- Makes reviewing changes easier

If you directly paint on the museum wall (main), any mistake is visible to everyone immediately. But if you paint on a removable canvas (branch), you can perfect your art and only attach it to the wall once it’s ready.

### What is a pull request (PR)?
A PR is a request to merge changes from one branch into another.  
In teams, PRs are used to review code, discuss improvements, and ensure everything is correct before merging.

A PR is like submitting your homework to the teacher for review before it gets graded and added to the class record. It allows others to check your work, suggest changes, and approve it to ensure quality before merging.

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

**Conventional COMMITS**
- _feat: → A new feature_
- _fix: → A bug fix_
- _docs: → Documentation changes only_
- _style: → Code formatting (no logic changes)_
- _refactor: → Code change that doesn’t fix a bug or add a feature_
- _test: → Adding or updating tests_
- _chore: → Changes to build process, tooling, etc._

git add how-browser-works.md
git commit -m "docs: add how-browser-works.md"
**Push your branch to GitHub:**

git push -u origin week1-submission

**Create a pull request:**

Base branch: main

Compare branch: week1-submission

Adding the Pr title and description and assigning the reviewer

## Why This Workflow Matters
- Keeps main clean and production-ready

- Allows safe experimentation in branches

- Makes teamwork more organized

- Tracks history for learning and debugging