# Linux workstation setup

> **Status:** Needs review
> **Applies to:** Debian/Ubuntu-family distributions; exact releases and desktop environments have not been tested
> **Last verified:** Not tested
> **Risk:** Medium — partitioning, bootloader, privilege, and driver choices are device-specific

This is a checklist distilled from older notes, not a universal installation recipe. Back up important data and consult the distribution's current installation documentation before changing partitions or boot configuration.

## Required

1. Install the desired distribution using its current installer. Confirm the target disk and boot mode (UEFI/BIOS) before changing partitions. The previous dual-disk partitioning notes are not retained as instructions.
2. Complete the distribution's supported system update procedure.
3. Install tools needed for the intended workload. The earlier notes used Git, Vim, curl, CMake, and ImageMagick; treat this list as a starting point, not a requirement.
4. Configure the shell and editor you actually use. See [Developer environment](../docs/topics/cross-platform/developer-environment.md).
5. If this is a development machine, set up Conda and VS Code only as needed; see the [software catalog](../docs/topics/software-catalog.md).

## Optional preferences

- GNOME extensions, preview utilities, themes, and shell customizations are optional and vary by distribution and desktop version. Review each project's current installation guidance before installing.
- Oh My Zsh and its plugins were previously installed by running a downloaded shell script. That command is intentionally not repeated here; use the project's current official instructions and inspect installation changes first.
- The previous notes suggested changing `sudoers` password feedback and timeout settings. Those changes affect privilege behavior and are omitted pending a security and version review.
- For CUDA workloads, see [NVIDIA GPU and CUDA](../docs/topics/hardware/nvidia-gpu-cuda.md). Do not use the historical cuDNN commands without checking current compatibility.

## Verification

Confirm the system boots normally, networking works, updates complete, and each installed application starts. Record the distribution release, desktop environment, hardware, and test date before changing this page's status to **Verified**.

## Rollback

Use the distribution's documented recovery process for boot or partition problems. Remove optional applications through the package manager that installed them. Do not copy old bootloader repair commands without confirming the disk and boot mode.

## Sources

- [Ubuntu installation documentation](https://ubuntu.com/tutorials/install-ubuntu-desktop)
- [Ubuntu community help wiki](https://help.ubuntu.com/)
