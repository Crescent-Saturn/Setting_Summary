# Developer environment

> **Status:** Needs review
> **Applies to:** Windows, macOS, and Linux; installation details vary by platform
> **Last verified:** Not tested

## Python and Conda

Use [Miniconda](https://docs.conda.io/projects/miniconda/en/latest/) when isolated Python environments are useful. The old notes recommended adding `conda-forge` and enabling channel priority, but did not specify a Conda version or project compatibility constraints. Review the current Conda configuration documentation before changing channels.

For GPU-enabled PyTorch, use the [official selector](https://pytorch.org/get-started/locally/) for the target operating system, Python version, and accelerator. Avoid copying old CUDA/cuDNN installation commands.

## Editors

- [Visual Studio Code](https://code.visualstudio.com/) and its extensions are optional. The previous Linux list included Python, Remote SSH, Git Graph, and several navigation/Markdown extensions; verify each extension's current publisher and maintenance status.
- Sublime Text settings and key bindings are preserved under [`configs/sublime/`](../../../configs/sublime/README.md). They are historical starting points and may depend on packages or themes that are no longer installed.
- A Vim configuration is available at [`configs/vim/.vimrc`](../../../configs/vim/.vimrc). It configures vim-plug and third-party plugins; review the file and plugin sources before using it.

## Shell

The old Linux notes mentioned Zsh and Oh My Zsh. Installation, changing the default shell, and loading plugins are optional. Follow the projects' current official instructions; do not treat an old remote-script command as a verified installation method.

The former archive also included a Bash prompt customization that showed the current Git branch. Treat it as a personal shell preference and review it for compatibility with the shell configuration you use.

## Small references

- Windows binary concatenation example: `copy /b play*.ts play_new.ts`. Check the input set and output path first; this is a one-off command, not a general media-merging workflow.
- The old FFmpeg loop converted each MP3 in the current directory to M4A. For media conversion, check the current FFmpeg documentation and review the input/output names before running a batch operation.
- Suggested editor fonts are listed in the [software catalog](../software-catalog.md).
