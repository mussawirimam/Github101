# Git: Create Branch → Push → Merge to Main

-----------------------------------------------------
1. Check current branch:
   $ git branch
   # '*' marks active branch

-----------------------------------------------------
2. Create a new branch:
   $ git branch my-new-branch
   # This creates a branch locally

-----------------------------------------------------
3. Switch to the new branch:
   $ git checkout my-new-branch
   # Or combine steps 2 & 3: git checkout -b my-new-branch

-----------------------------------------------------
4. Stage your changes:
   $ git add *

-----------------------------------------------------
5. Commit your changes:
   $ git commit -m "commit message"

-----------------------------------------------------
6. Push branch to remote and set upstream:
   $ git push -u origin my-new-branch
   # Now future pushes can use 'git push' alone

-----------------------------------------------------
7. Switch back to main:
   $ git checkout main

-----------------------------------------------------
8. Pull latest changes from remote main (optional but recommended):
   $ git pull origin main

-----------------------------------------------------
9. Merge your branch into main:
   $ git merge my-new-branch
   # Resolve conflicts if any

-----------------------------------------------------
10. Push updated main branch to remote:
   $ git push origin main

-----------------------------------------------------
### to delete old branch
# Switch to main branch
git checkout main

# Delete local branch
git branch -d my-old-branch

# Delete remote branch
git push origin --delete my-old-branch
-----------------------------------------------------
Tips:
- Use descriptive branch names (feature/login, bugfix/header)
- Keep main branch stable; always work in feature branches
- Push frequently to backup your work
