# GitHub Token / Credential Cleanup Notes

Purpose:
- Remove all stored GitHub tokens
- Clear cached credentials
- Start fresh for HTTPS or switch to SSH

-----------------------------------------------------
1. Unset Git credential helper:
   $ git config --global --unset credential.helper

2. Remove stored credentials file (if using store helper):
   $ rm -f ~/.git-credentials

3. Clear cached credentials (if using cache helper):
   $ git credential-cache exit

4. Remove credentials from OS credential manager:

   Linux (libsecret / Gnome Keyring):
   $ secret-tool clear github.com username

   macOS:
   - Open Keychain Access
   - Search for 'github.com'
   - Delete all relevant entries

   Windows:
   - Open Credential Manager → Windows Credentials
   - Delete all entries for 'git:https://github.com'

5. Verify:
   $ git push
   # Git should now prompt for username and token

6. Optional: Switch to SSH for permanent passwordless authentication

   Generate SSH key:
   $ ssh-keygen -t ed25519 -C "your_email@example.com"

   Copy public key:
   $ cat ~/.ssh/id_ed25519.pub

   Add to GitHub:
   https://github.com/settings/keys → New SSH key

   Change Git remote to SSH:
   $ git remote set-url origin git@github.com:username/repo.git

   Test:
   $ ssh -T git@github.com

   Push code:
   $ git push -u origin main

-----------------------------------------------------
Notes:
- HTTPS tokens expire; SSH avoids repeated prompts
- Clearing credentials ensures you start fresh without conflicts
- Always backup any important credentials if unsure
