# Day 0 — Git Basics (RHCSA Preparation)

Before starting Linux administration, it is important to understand **Git**, because it helps you track your learning, save progress, and publish your work on GitHub.

This Day 0 document introduces Git from scratch, assuming **no prior knowledge**.

---

## What is Git?

**Git** is a version control system.  
It helps you keep a history of changes made to files.

In simple terms, Git allows you to:
- save versions of your work
- see what changed and when
- recover older versions if something breaks
- organise learning notes over time

For RHCSA preparation, Git is useful because:
- you write notes and commands daily
- your work stays structured
- GitHub becomes an online backup and portfolio

---

## Git and GitHub are not the same

| Git | GitHub |
|----|-------|
| Software installed on your system | Website that hosts Git repositories |
| Works offline | Requires internet |
| Tracks file changes | Stores and shares repositories |

Git works on your local machine.  
GitHub is where you **push** your Git repository.

---

## Creating the project folders (mkdir)

Linux uses directories to organise files.

To create folders for your RHCSA journey:

```bash
mkdir -p RHCSA/Day{0..5}
Explanation:

mkdir creates directories

-p creates parent directories if needed

no error occurs if folders already exist

Check the structure:

ls -R RHCSA
Creating README files (important for Git)

Git tracks files, not empty folders.
Each directory should contain at least one file.

Create README files:

touch RHCSA/Day0/README.md
touch RHCSA/Day1/README.md
touch RHCSA/Day2/README.md

Verify:

find RHCSA -type f
Moving into the project directory
cd RHCSA

Confirm your location:

pwd
ls

You should see Day0, Day1, and Day2.

Initialising Git in the folder
git init

This command:

turns the folder into a Git repository

creates a hidden .git directory

enables version tracking

Check:

ls -a

You should see .git.

Configuring Git user identity

Git records who created each commit.

This is not GitHub login information.
It only appears in commit history.

Set global identity:

git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"

Verify:

git config --global user.name
git config --global user.email

If required, identity can also be set only for this repository:

git config --local user.name "Your Name"
git config --local user.email "your_email@example.com"
Checking Git status
git status

This shows:

untracked files

modified files

staged files

At first, README files appear as untracked.

Adding files to Git (staging)
git add .

This tells Git:

“Start tracking these files.”

Confirm:

git status
Creating a commit
git commit -m "Add Day 0, Day 1, and Day 2 structure"

A commit:

saves a snapshot of files

records author, time, and message

View commit history:

git log
Connecting the repository to GitHub (HTTPS)

Check existing remote configuration:

git remote -v

Add GitHub remote using HTTPS:

git remote add origin https://github.com/<username>/RHCSA.git

If a remote already exists (for example SSH), replace it:

git remote set-url origin https://github.com/<username>/RHCSA.git

Verify:

git remote -v

URLs must start with https://.

Pushing changes to GitHub

Check the branch name:

git branch

Push based on branch:

git push -u origin master

or

git push -u origin main

GitHub will ask for credentials:

Username → GitHub username

Password → GitHub Personal Access Token (PAT)

Common troubleshooting commands

Check repository state:

git status

Check remote URL:

git remote -v

Check configured author identity:

git config --global user.name
git config --global user.email

Clear cached HTTPS credentials if wrong account was used:

rm -f ~/.git-credentials
git config --global --unset credential.helper

Then push again.

Key concepts to remember

Git tracks files, not folders

mkdir creates directories

git init starts version control

git add stages files

git commit saves history

git remote -v shows HTTPS or SSH usage

HTTPS uses PAT(Personal Access Token), not GitHub password
