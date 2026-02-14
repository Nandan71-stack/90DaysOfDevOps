

Then add the following content inside it 👇

Day 22 – Understanding Git Workflow
1️⃣ What is the difference between git add and git commit?

git add moves changes from the working directory to the staging area.

git commit saves the staged changes permanently into the repository history.

In simple words:
git add = “prepare this file”
git commit = “save this snapshot permanently”
So first we stage changes, then we commit them.

2️⃣ What does the staging area do? Why doesn’t Git commit directly?
The staging area (also called index) is a temporary place where we prepare changes before committing.
It allows us to:
Select specific files to commit
Commit only certain changes
Review changes before saving
If Git committed directly, we would not have control over:

Which files go into the commit

Partial commits

Organizing commits properly
The staging area gives flexibility and control.

3️⃣ What information does git log show you?
git log shows the commit history of the repository.
It includes:
Commit ID (hash)

Author name
Date and time
Commit message
This helps us:

Track changes

See who made changes
Go back to older versions

4️⃣ What is the .git/ folder and what happens if you delete it?
The .git/ folder is the hidden directory created when we run:
git init

It contains:

All commit history
Branch information
Configuration
Staging data

Object database
If you delete the .git/ folder:
The project stops being a Git repository

All commit history is lost

Git commands will not work
Your files will still exist, but version control will be gone.

5️⃣ What is the difference between working directory, staging area, and repository?
🔹 Working Directory
This is where you edit your files.
It contains the actual project files.
🔹 Staging Area
This is where you prepare files before committing.
It acts as a middle layer.
🔹 Repository
This is where Git permanently stores committed snapshots.
It is stored inside the .git/ folder.

🔁 Simple Workflow Diagram (Important for Interviews)
Working Directory → git add → Staging Area → git commit → Repository
