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
So basically:
👉 Git rewinds or updates your project to match that branch’s version.
