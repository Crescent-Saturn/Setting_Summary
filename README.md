# Setting Summary

A personal setup knowledge base for reproducing device setups, finding answers, and reusing configuration files. Procedures that have not been tested recently are labeled **Needs review** rather than presented as verified instructions.

## Start here

- **Set up a device:** [Profiles](profiles/README.md)
- **Find OS-specific settings:** [Windows](docs/platforms/windows.md) · [Linux](docs/platforms/linux.md)
- **Find software:** [Software catalog](docs/topics/software-catalog.md)
- **Configure developer tools:** [Developer environment](docs/topics/cross-platform/developer-environment.md) · [SSH and Git](docs/topics/cross-platform/ssh-git.md)
- **Troubleshoot a known issue:** [Troubleshooting index](docs/troubleshooting/README.md)
- **Reuse a configuration:** [Configs index](configs/README.md)

## Repository map

| Path | Purpose |
|---|---|
| `profiles/` | Ordered device and workload setup checklists |
| `docs/platforms/` | OS-specific behavior and preferences |
| `docs/topics/` | Reusable cross-platform and hardware guidance |
| `docs/troubleshooting/` | Symptoms, diagnosis, fixes, and validation |
| `configs/` | Reusable configuration files and sanitized examples |
| `templates/` | Templates for consistent future entries |

## Maintenance

Keep each setting in one canonical document and link to it from profiles. Separate required steps from optional preferences. Treat untested or version-sensitive procedures as **Needs review**; record the exact environment and date only after testing. Never store credentials, private keys, activation codes, or internal hostnames here.

An activation string was removed from the historical README during this reorganization. Removing it from the current files does not remove it from Git history; if it was valid or sensitive, revoke or replace it with its vendor and consider repository-history remediation.
