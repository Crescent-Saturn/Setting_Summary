# Windows 上安装 pycocotools

> **状态：** 待复核
> **适用范围：** 原笔记未注明 Windows、Python、`pycocotools` 和 MSVC 的具体版本
> **最后验证：** 尚未测试
> **风险：** 中

## 现象

使用 pip 安装 `pycocotools` 时，编译原生扩展可能失败，例如错误信息中出现 MSVC 链接器。

## 历史笔记

原流程建议使用 Conda 环境、安装 Visual C++ 构建工具和 Windows SDK，然后再次尝试通过 pip 安装。它还建议将 SDK 可执行文件和 DLL 复制到 Visual Studio 目录。这里不建议手动复制这些文件：该步骤针对过时的工具链路径，可能造成编译环境不一致。

## 建议处理方式

1. 创建或激活隔离的 Python 环境。
2. 查看软件包当前的安装说明以及支持的 Python/Windows 版本。
3. 如果必须从源码编译，安装当前受支持的 Visual Studio C++ Build Tools 和 Windows SDK。
4. 重试安装；若仍失败，请保留完整错误输出，不要在不同目录间手动复制工具链文件。

## 验证与回滚

在同一环境中导入 `pycocotools` 并运行项目相关测试。如果构建工具仅用于此软件包，请通过受支持的 Visual Studio 安装程序移除。

## 资料来源

- [PyPI 上的 pycocotools](https://pypi.org/project/pycocotools/)
- [Visual Studio Build Tools](https://visualstudio.microsoft.com/downloads/)
