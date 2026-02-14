TASK 1:
✅ Step 1: Verify Git is Installed
Open your terminal (Git Bash / CMD / PowerShell) and run:
git --version
✔ Expected Output:
git version 2.xx.x

If you see a version → Git is already installed ✅
If you get "git is not recognized" → Install Git from:
👉 https://git-scm.com/downloads
✅ Step 2: Set Up Your Git Identity
Git needs your name and email to track commits.

Run these commands:

git config --global user.name "Your Full Name"
git config --global user.email "your@email.com"

Example:
git config --global user.name "Raghunandan Maurya"
git config --global user.email "raghu@email.com"

⚠ Use the same email you use on GitHub.

✅ Step 3: Verify Your Configuration
To check your settings:
git config --list
You should see:
user.name=Raghunandan Maurya
user.email=raghu@email.com
🎯 Bonus: Check Where Git Stores Config
git config --global --edit

This opens your global config file.
On Windows it is usually located at:
C:\Users\YourUsername\.gitconfig
🔥 Quick Practice Check
Run:
git config user.name
git config user.email
If both show your details → You are properly configured ✅

TASK 2:
You will use terminal (Linux / Git Bash / WSL).

✅ Step 1: Create a New Folder
mkdir devops-git-practice
cd devops-git-practice
Now confirm you're inside the folder:
pwd
✅ Step 2: Initialize Git Repository
git init
You’ll see something like:
Initialized empty Git repository in /home/user/devops-git-practice/.git/
👉 This means Git has created a hidden .git directory.

✅ Step 3: Check Git Status
git status
Output will look like:

On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

🔍 Understand What Git Is Saying

On branch master (or main) → You are on default branch.

No commits yet → This repo has no history.

Nothing to commit → There are no files yet.

Right now, Git is tracking nothing.

✅ Step 4: Explore the Hidden .git/ Directory
Show hidden files:
ls -a
You’ll see:

.  ..  .git

Now enter the .git folder:
cd .git
ls
You will see something like:
HEAD
config
description
hooks
info
objects
refs

🔎 What These Files Mean
📌 HEAD

Contains:

ref: refs/heads/master

👉 Tells Git which branch you're currently on.

📌 config

Stores repository configuration (username, email, remote, etc.)

Open it:

cat config

📌 objects/

This is the heart of Git ❤️
Stores all commits, files, history in compressed format.

Right now it's almost empty.

📌 refs/

Stores references to branches and tags.

📌 hooks/

Contains sample scripts for automation (like pre-commit hooks).

🧠 Important Concept

👉 The .git folder is the brain of your repository.
If you delete .git, your project is no longer a Git repo.

Try this command to go back:
cd ..
🎯 What You Just Learned
You now understand:
How to create a Git repo
What git init actually does
How to read git status
What is inside the .git folder
How Git stores data internally


TASK 3:
Inside your devops-git-practice repo, create the file:

touch git-commands.md


Then open it in your editor:

nano git-commands.md
# or
code git-commands.md


Copy the content below into git-commands.md:

📘 Git Commands Reference
🔹 1. Setup & Config
git init

What it does: Initializes a new Git repository in the current folder.
Example:

git init

git config --global user.name

What it does: Sets your global Git username.
Example:

git config --global user.name "Raghunandan Maurya"

git config --global user.email

What it does: Sets your global Git email.
Example:

git config --global user.email "your@email.com"

git clone

What it does: Creates a copy of a remote repository on your local machine.
Example:

git clone https://github.com/username/repo.git

🔹 2. Basic Workflow
git status

What it does: Shows the current state of files in the repository.
Example:

git status

git add

What it does: Stages changes before committing.
Example:

git add file.txt

git add .

What it does: Stages all changed files.
Example:

git add .

git commit

What it does: Saves staged changes to the repository history.
Example:

git commit -m "Initial commit"
git push
What it does: Uploads local commits to the remote repository.
Example:
git push origin main
git pull
What it does: Fetches and merges changes from the remote repository.
Example:
git pull origin main
🔹 3. Viewing Changes
git log
What it does: Shows commit history.
Example:
git log
git log --oneline
What it does: Shows a short version of commit history.
Example:
git log --oneline
git diff
What it does: Shows differences between working directory and staged files.
Example:
git diff
git diff --staged
What it does: Shows differences between staged changes and last commit.
Example:
git diff --staged
✅ After Adding the File
Save the file, then run:
git add git-commands.md
git commit -m "Added Git commands reference file"
git push

TASK 4:
Good 👍 Now we’ll complete Task 4 properly like a real DevOps workflow.
Make sure you are inside your repository:
cd devops-git-practice
✅ Step 1: Stage Your File
git add git-commands.md
👉 This moves the file from working directory → staging area.
✅ Step 2: Check What’s Staged
git status
You should see something like:
Changes to be committed:
  new file:   git-commands.md
If you want to see exactly what is staged:
git diff --staged
✅ Step 3: Commit with a Meaningful Message
git commit -m "Add categorized Git command reference with examples"
✔ Good commit messages:
Start with a verb (Add, Update, Fix, Remove)
Be clear and short
Explain what changed
✅ Step 4: View Your Commit History
Short version (recommended):
git log --oneline
Full detailed version:
git log
You should now see your new commit at the top.
🎯 What You Just Practiced
You completed the full Git workflow:
Working Directory → Staging Area → Commit → History

TASK 5:

Good 👍 This task is about building real Git history — exactly what interviewers like to see.

Let’s do it step-by-step inside your devops-git-practice project.

✅ Step 1: Edit git-commands.md

Open and add more commands:

nano git-commands.md


Add something like:

## Branch Commands
git branch
git checkout -b feature-branch
git merge feature-branch

## Remote Commands
git remote -v
git push origin main
git pull origin main


Save and exit.

✅ Step 2: Check What Changed
git status


You’ll see something like:

modified: git-commands.md


To see exact changes:

git diff


👉 This shows what was added/removed since last commit.

✅ Step 3: Stage and Commit (1st new commit)
git add git-commands.md
git commit -m "Added branch and remote git commands"

🔁 Repeat the Process (At Least 3 Times)
✏️ Edit Again

Add more:

## Log & History
git log
git log --oneline
git show <commit-id>

## Undo Commands
git reset --soft HEAD~1
git restore <file>

Check Changes
git status
git diff

Commit Again (2nd new commit)
git add .
git commit -m "Added log and undo related git commands"

✏️ Edit Again (3rd time)

Add:

## Stash Commands
git stash
git stash list
git stash apply

Stage & Commit
git add .
git commit -m "Added stash commands section"

✅ Now View Full History (Compact Format)
git log --oneline


Example output:

a3f4d21 Added stash commands section
9bc2e11 Added log and undo related git commands
5de8a90 Added branch and remote git commands
1ab34cd Initial commit with basic git commands


👉 Each line is one commit.
👉 The left part is short commit ID.
👉 Right part is your commit message.

🚀 Bonus (Very Important for DevOps)

To see a visual history graph:

git log --oneline --graph --decorate --all


This shows branch structure visually.

🧠 What You Just Practiced

Modifying tracked files

Checking changes with git diff

Creating meaningful commits

Building commit history

Viewing history in compact format

This is real Git workflow used daily in DevOps.


