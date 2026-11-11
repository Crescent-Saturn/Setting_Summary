# Pycocotools on Windows

> **Status:** Needs review
> **Applies to:** Windows, Python, `pycocotools`, and MSVC versions not established by the original notes
> **Last verified:** Not tested
> **Risk:** Medium

## Symptom

Installing `pycocotools` with pip may fail while compiling native extensions, including errors mentioning the MSVC linker.

## Historical notes

The original procedure recommended a Conda environment, Visual C++ build tools, Windows SDK components, and a second pip install attempt. It also suggested copying SDK executables and DLLs into a Visual Studio directory. That manual copy step is not recommended here: it targets outdated toolchain paths and can leave an inconsistent compiler installation.

## Recommended approach

1. Create or activate an isolated Python environment.
2. Check the package's current installation instructions and supported Python/Windows versions.
3. Install the current supported Visual Studio C++ Build Tools and Windows SDK if source compilation is required.
4. Retry installation and retain the complete error output if it still fails; do not copy toolchain files between directories.

## Verification and rollback

Import `pycocotools` in the same environment and run the project's relevant tests. If toolchain installation was only for this package, remove it only through the supported Visual Studio installer.

## Sources

- [pycocotools on PyPI](https://pypi.org/project/pycocotools/)
- [Visual Studio Build Tools](https://visualstudio.microsoft.com/downloads/)
