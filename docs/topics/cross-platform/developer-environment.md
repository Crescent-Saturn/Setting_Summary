# 开发环境

> **状态：** 待复核
> **适用范围：** Windows、macOS 和 Linux；安装方式因平台而异
> **最后验证：** 尚未测试

## Python 与 Conda

需要隔离 Python 环境时可使用 [Miniconda](https://docs.conda.io/projects/miniconda/en/latest/)。旧笔记建议添加 `conda-forge` 并启用频道优先级，但没有注明 Conda 版本或项目兼容要求。更改频道前请查看 Conda 当前的配置文档。

安装支持 GPU 的 PyTorch 时，请使用[官方安装选择器](https://pytorch.org/get-started/locally/)，根据目标操作系统、Python 版本和加速器选择方案。不要直接照搬旧 CUDA/cuDNN 安装命令。

## 编辑器

- [Visual Studio Code](https://code.visualstudio.com/) 及其扩展均为可选。旧版 Linux 清单提到 Python、Remote SSH、Git Graph 以及一些导航和 Markdown 扩展；安装前请核实扩展发布者和维护状态。
- Sublime Text 设置和快捷键保存在 [`configs/sublime/`](../../../configs/sublime/README.md)。这些是历史配置，可能依赖已不再安装的软件包或主题。
- Vim 配置见 [`configs/vim/.vimrc`](../../../configs/vim/.vimrc)。其中配置了 vim-plug 和第三方插件；使用前请检查文件和插件来源。

## Shell

旧版 Linux 笔记提到 Zsh 和 Oh My Zsh。安装、设置为默认 Shell 及加载插件均为可选操作。请遵循项目当前的官方说明，不要把旧的远程脚本命令视作已验证的安装方法。

旧归档还包含一个用于显示当前 Git 分支的 Bash 提示符定制。它只是个人 Shell 偏好，使用前请确认与现有 Shell 配置兼容。

## 零散参考

- Windows 二进制文件拼接示例：`copy /b play*.ts play_new.ts`。执行前请确认输入文件范围和输出路径；这只是单次命令，不是通用媒体合并流程。
- 旧 FFmpeg 循环命令会将当前目录中的 MP3 转换为 M4A。批量执行前请查看 FFmpeg 当前文档，并确认输入和输出文件名。
- 编辑器字体建议见[软件目录](../software-catalog.md)。
