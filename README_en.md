# Setting Summary

A personal setup knowledge base for reproducing device setups, finding answers, and reusing configuration files. Procedures that have not been tested recently are labeled **Needs review** rather than presented as verified instructions.

> **Language:** English version. The default Chinese version is [`README.md`](README.md).

## Start here

- **Set up a device:** [Profiles](profiles/README_en.md)
- **Find OS-specific settings:** [Windows](docs/platforms/windows_en.md) · [Linux](docs/platforms/linux_en.md)
- **Find software:** [Software catalog](docs/topics/software-catalog_en.md)
- **Configure developer tools:** [Developer environment](docs/topics/cross-platform/developer-environment_en.md) · [SSH and Git](docs/topics/cross-platform/ssh-git_en.md)
- **Troubleshoot a known issue:** [Troubleshooting index](docs/troubleshooting/README_en.md)
- **Reuse a configuration:** [Configs index](configs/README_en.md)

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

An activation string was removed from the historical README during an earlier reorganization. Removing it from current files does not remove it from Git history; if it was valid or sensitive, revoke or replace it with its vendor and consider repository-history remediation.
