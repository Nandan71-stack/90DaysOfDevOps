TASK 1:

1️⃣ What is a branch in Git?
A branch in Git is a separate line of development.
It allows you to work on new features, bug fixes, or experiments without affecting the main project.
By default, Git creates a branch called main (or master in older versions).
2️⃣ Why do we use branches instead of committing everything to main?

We use branches because:
They keep the main branch stable and clean.
We can work on features without breaking the main code.
Multiple developers can work on different features at the same time.
It allows safe testing before merging changes into main.
If we committed everything directly to main, it could cause bugs and confusion.

3️⃣ What is HEAD in Git?
HEAD is a pointer that tells Git:
Which branch you are currently on.
Which commit you are currently working from.
In simple words:
👉 HEAD points to the latest commit of the current branch.
When you switch branches, HEAD moves to that branch.
4️⃣ What happens to your files when you switch branches?
When you switch branches:
Git updates your working directory.
Your files change to match the latest commit of the branch you switched to.
Files that exist in one branch but not in another may appear or disappear.
Uncommitted changes may cause conflicts if they overlap.


TASK 5:
Clone vs Fork
🔹 1️⃣ What is the difference between Clone and Fork?
✅ Clone
git clone copies a repository from GitHub to your local machine.
It creates a local copy.
The original repo stays on GitHub.
You don’t get your own GitHub copy — just a local version.
👉 Example:
git clone https://github.com/user/repo.git
✅ Fork
Fork creates a copy of someone else’s repository on your GitHub account.
It is a server-side copy (on GitHub).
You become the owner of that fork.
You can modify it freely without affecting the original repo.
After forking, you usually:
git clone https://github.com/your-username/repo.git

🔥 Simple Difference
Clone	Fork
Copy to your local machine	Copy to your GitHub account
Done using Git	Done using GitHub website
Used to download a repo	Used to contribute to others’ projects
🔹 2️⃣ When Would You Clone vs Fork?
🟢 Use Clone When:

It’s your own repository
You just want to download and work locally
You have direct write access to the repo
Example:
Cloning your devops-git-practice project
🟢 Use Fork When:
You want to contribute to someone else's project
You do NOT have write access
You want your own independent copy on GitHub
Example:
Contributing to an open-source project
🔹 3️⃣ After Forking, How Do You Keep Your Fork in Sync?
After you fork and clone your fork, you must connect the original repo as upstream.
Step 1: Add upstream
git remote add upstream https://github.com/original-owner/repo.git
Check remotes:
git remote -v
You will see:
origin   → your fork
upstream → original repo
Step 2: Fetch updates from original repo
git fetch upstream
Step 3: Merge updates into your branch
If using main branch:
git checkout main
git merge upstream/main

OR (recommended modern way):
git pull upstream main
🧠 Final Summary for Your Notes
Clone = copy repo to your local machine
Fork = copy repo to your GitHub account
Clone when working on your own repo
Fork when contributing to someone else's project
Use upstream remote to sync your fork with original
So basically:
👉 Git rewinds or updates your project to match that branch’s version.
