# GitHub SSH Key Setup for Git Push

1. Generate a new SSH key (ed25519 is recommended):
   $ ssh-keygen -t ed25519 -C "your_email@example.com"

   - Press Enter to accept default file location (~/.ssh/id_ed25519)
   - Enter a passphrase (optional but recommended)

2. Copy the public key:
   $ cat ~/.ssh/id_ed25519.pub
   # Copy the entire output to your clipboard

3. Add SSH key to GitHub:
   - Go to https://github.com/settings/keys
   - Click "New SSH key"
   - Give it a title (e.g., "VPS Terra Key")
   - Paste the public key from step 2
   - Click "Add SSH key"

4. Test SSH connection:
   $ ssh -T git@github.com
   > You should see: "Hi username! You've successfully authenticated..."

5. Change your Git repo remote to SSH:
   $ git remote set-url origin git@github.com:username/repo.git

6. Verify remote URL:
   $ git remote -v
   origin  git@github.com:username/repo.git (fetch)
   origin  git@github.com:username/repo.git (push)

7. Push to GitHub using SSH (no password required):
   $ git push -u origin main

# Notes:
- Use `main` or your current branch name.
- Once SSH is set up, Git will not ask for username/token again.
- Optional: Add key to ssh-agent for passphrase caching:
  $ eval "$(ssh-agent -s)"
  $ ssh-add ~/.ssh/id_ed25519
