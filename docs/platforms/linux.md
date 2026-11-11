# Linux

> **Status:** Needs review
> **Applies to:** Distribution- and desktop-environment-specific; no current version has been tested
> **Last verified:** Not tested
> **Risk:** Low to Medium, depending on the setting

Linux desktop behavior differs across distributions, releases, display servers, and desktop environments. Confirm the exact environment before applying a setting or command.

## Desktop preferences

The older notes mentioned GNOME Shell extensions, a file preview tool, and a GRUB theme. These are optional preferences, not setup requirements. Check compatibility and install extensions/themes only from trusted sources; avoid running an unreviewed installer script.

## Dual-boot clock

An older note changed the hardware clock to local time to synchronize Windows and Linux. This can affect time handling and is not included as a default recommendation. Prefer a current distribution-supported solution and verify both operating systems' time-zone and clock behavior before changing it.

## Related

- [Linux workstation profile](../../profiles/linux-workstation.md)
- [Software catalog](../topics/software-catalog.md)
- [NVIDIA GPU and CUDA](../topics/hardware/nvidia-gpu-cuda.md)
