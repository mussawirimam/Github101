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

-----------------------------------------------------
            Local Repository
        +-----------------------+
        |                       |
        |         main          |
        |         *             |
        |                       |
        +-----------+-----------+
                    |
                    | git checkout -b feature/login
                    v
        +-----------------------+
        |   feature/login       |
        |         *             |
        +-----------+-----------+
                    |
                    | git add . && git commit -m "Add login feature"
                    v
        +-----------------------+
        |   feature/login       |
        |   commits ahead of main
        +-----------+-----------+
                    |
                    | git push -u origin feature/login
                    v
            Remote Repository (GitHub)
        +-----------------------+
        |       main            |
        |                       |
        | feature/login (new)   |
        +-----------------------+

# Commands Summary:

1. Create & switch to branch:
   $ git checkout -b feature/login

2. Work & commit:
   $ git add .
   $ git commit -m "Commit message"

3. Push branch to remote:
   $ git push -u origin feature/login

4. Switch back to main:
   $ git checkout main

5. Merge branch (optional):
   $ git merge feature/login
