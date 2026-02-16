🟢 1️⃣ Git Setup Commands
Check version
git --version

Set username
git config --global user.name "Your Name"

Set email
git config --global user.email "your@email.com"

Check config
git config --list

🟢 2️⃣ Create & Initialize Repository
Create folder
mkdir project-name
cd project-name

Initialize Git
git init

🟢 3️⃣ Basic Workflow Commands
Check status
git status

Add file to staging
git add file.txt

Add all files
git add .

Commit changes
git commit -m "Your message"

View commit history
git log


Compact view:

git log --oneline

🟢 4️⃣ Branching Commands
List branches
git branch

Create branch
git branch feature-1

Switch branch (old way)
git checkout feature-1

Switch branch (new way)
git switch feature-1

Create & switch
git checkout -b feature-2

Delete branch
git branch -d feature-1


Force delete:

git branch -D feature-1

🟢 5️⃣ Remote & GitHub Commands
Add remote repository
git remote add origin https://github.com/username/repo.git

View remotes
git remote -v

Remove remote
git remote remove origin

🟢 6️⃣ Push & Pull Commands
Push to GitHub
git push -u origin main


After first push:

git push

Pull changes
git pull origin main

Fetch changes
git fetch origin

🟢 7️⃣ Clone & Fork
Clone repository
git clone https://github.com/username/repo.git

Add upstream (after fork)
git remote add upstream https://github.com/original/repo.git

Sync fork
git fetch upstream
git merge upstream/main

🟢 8️⃣ View Changes
Show file differences
git diff

Show staged changes
git diff --staged

🟢 9️⃣ Undo / Fix Commands
Unstage file
git restore --staged file.txt

Discard changes
git restore file.txt

Reset last commit (keep changes)
git reset --soft HEAD~1

Reset completely
git reset --hard HEAD~1

🟢 🔟 Useful Commands
Rename branch
git branch -m new-name

Show current branch
git branch --show-current

Show remote branches
git branch -r

🧠 Quick Difference: Git vs GitHub
Git	GitHub
Version control tool	Cloud hosting for Git
Works locally	Works online
git init, git add	fork, pull request

If you want, I can next give you:

🔥 20 Most Important Git Commands for Interview

🔥 Real Project Git Workflow

🔥 Git Cheat Sheet (1-page format)

🔥 Advanced Git Commands (merge, rebase, stash)

Tell me what level you want next 🚀
