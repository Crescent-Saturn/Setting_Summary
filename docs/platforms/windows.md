# Windows

> **Status:** Needs review
> **Applies to:** Windows 10 and 11; edition-specific behavior has not been tested
> **Last verified:** Not tested
> **Risk:** Medium

## Legacy Windows 10 notes

The former README contained Windows 10 privacy, Group Policy, service, and power-setting tweaks. They have not been revalidated for current Windows editions and are intentionally not reproduced as a checklist. In particular, do not disable Microsoft Defender or other security protections, disable services, or change update policies based on that historical list.

Before changing a policy, service, or privacy setting, check its current Microsoft documentation, the applicable Windows edition, and the effect on updates, security, and device management. Prefer supported Settings controls and reversible per-user changes.

The old notes also included DISM and SFC repair commands. Use Microsoft's current repair guidance only when diagnosing an actual system issue; these are not routine optimization steps.

## Related

- [Software catalog](../topics/software-catalog.md) — Windows utilities
- [Pycocotools on Windows](../troubleshooting/pycocotools-windows.md) — legacy build notes, not yet validated
