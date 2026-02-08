# Day 0 - Git Basics (RHCSA Preparation)

Before starting Linux administration, it is important to understand **Git**, because it helps you track your learning, save progress, and publish your work on GitHub.

This Day 0 document introduces Git from scratch, assuming **no prior knowledge**.

---

### What is Git?

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

### Step 1 - Create folders 
If you don’t have folders already, create them using the command:

`mkdir Day0` if you are already in RHCSA Folder <br>
`mkdir -p RHCSA/Day{0..5}` <br>
`mkdir -p RHCSA/Day0 RHCSA/Day1` <br>

### What this does:
mkdir = make directory (create folder) <br>
-p = create parent folders if needed (and don’t error if they already exist)

### Check the structure: <br>
`ls -R RHCSA` <br>

### Step 2 - Create README files (so Git can track content)
Git tracks files, not empty folders.
Each directory should contain at least one file.

### Create README files:
`touch RHCSA/Day0/README.md` <br>
`touch RHCSA/Day1/README.md` <br>
`touch RHCSA/Day2/README.md` <br>

### Verify:
`find RHCSA -type f`

### Expected output:
`RHCSA/Day0/README.md` <br>
`RHCSA/Day1/README.md` <br>
`RHCSA/Day2/README.md` <br>

### Step 3- Move into your repo folder
`cd RHCSA`

### To confirm you are in the right folder:
`pwd` 
`ls` <br>
You should see Day0, Day1, and Day2.

### Step 4 - Initialise Git in your local folder
`git init`

### This command:
- Turns the folder into a Git repository
- Creates a hidden .git directory
- Enables version tracking

### Check:
`ls -a`
You should see .git.

### Step 5 - Configuring Git user identity
Git records who created each commit. This is not GitHub login information. It only appears in commit history.

### Set global identity:
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"

### Verify:
- `git config --global user.name`
- `git config --global user.email`

### If required, identity can also be set only for this repository:
- `git config --local user.name "Your Name"`
- `git config --local user.email "your_email@example.com"`

### Step 6 - Checking Git status
`git status`

### This shows:
- untracked files
- modified files
- staged files
- At first, README files appear as untracked.

### Step 7 - Adding files to Git (staging)
 `git add .`
  This tells Git: “Start tracking these files.”

 Verify using:
 `git status`

### Step 8 - Commit
`git commit -m "Add Day 0, Day 1, and Day 2 structure"`

### A commit: 
- saves a snapshot of files
- records author, time, and message
### View commit history:
`git log`

### Step 9 - Connect your local repo to GitHub (HTTPS)

### Check existing remote configuration:
`git remote -v`

### Add GitHub remote using HTTPS:
`git remote add origin https://github.com/username/RHCSA.git`

### Step 10 - Push to GitHub
Check the branch name:
`git branch`

### You will see something like:
* master OR
* main

### Push based on branch:
- `git push -u origin master`
  or
- `git push -u origin main`
### GitHub will ask for credentials:
- Username → GitHub username
- Password → GitHub Personal Access Token (PAT)

## **Common troubleshooting commands**

### 1) Check repository state:
`git status`

### 2)Check remote URL:
`git remote -v`

### 3)Check configured user identity:
- `git config --global user.name`
- `git config --global user.email`

### 4)Clear cached HTTPS credentials if wrong account was used:
- `rm -f ~/.git-credentials`
- `git config --global --unset credential.helper`
### Then push again.
`git push -u origin main`

### **Key concepts to remember**
- Git tracks files, not folders
- `mkdir` creates directories
- `git init` starts version control
- `git add` stages files
- `git commit` saves history
- `git remote -v` shows HTTPS or SSH usage

