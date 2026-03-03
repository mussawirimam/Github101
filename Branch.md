# Git Branch Cheat-Sheet

-----------------------------------------------------
1. Check current branch:
   $ git branch
   # Output shows all local branches
   # '*' marks the active branch

2. Create a new branch (local only):
   $ git branch my-new-branch

3. Switch to an existing branch:
   $ git checkout my-new-branch

4. Create AND switch to new branch (shortcut):
   $ git checkout -b my-new-branch

5. Push a new branch to remote:
   $ git push -u origin my-new-branch
   # '-u' sets upstream for future pushes

6. List all branches (local + remote):
   $ git branch -a

7. Delete a branch (local):
   $ git branch -d my-old-branch
   # Use '-D' to force delete if not merged

8. Delete a branch (remote):
   $ git push origin --delete my-old-branch

-----------------------------------------------------
Tips:
- Branch names: use lowercase, hyphens or slashes (feature/login, bugfix/header)
- Keep main branch clean; do work in feature branches
- Regularly push branches to remote to backup work
