# SSH and Git

> **Status:** Needs review
> **Applies to:** OpenSSH clients on Windows, macOS, and Linux
> **Last verified:** Not tested

The sanitized example is in [`configs/ssh/config.example`](../../../configs/ssh/config.example). Copy only the needed entries into `~/.ssh/config`, replace placeholders, and protect the file with appropriate user-only permissions. Never put private-key contents in this repository.

The example shows keepalive options and separate entries for GitHub, GitLab, and a user-defined server alias. Ensure the referenced private key exists locally and that the server hostname and username are correct. SSH connection multiplexing is not configured in the example because it requires a writable control-socket directory and client-specific validation.

## Verification

Use `ssh -T git@github.com` or the corresponding provider's documented test after configuring the local key. A successful authentication test does not grant repository access by itself.

## Rollback

Remove or comment out the entries added to the local SSH config. Keep a backup before editing an existing config.
