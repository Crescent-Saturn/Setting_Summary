# LaTeX 与 PDF 笔记

> **状态：** 待复核
> **适用范围：** 原笔记提到 MiKTeX，但未记录具体版本
> **最后验证：** 尚未测试

以下内容是历史排查线索，不保证能解决问题。更改 TeX 安装前请备份项目文件，并查看所用发行版的当前文档。

## MiKTeX 字体映射与文件数据库

旧笔记建议使用 `initexmf --mkmaps` 重建字体映射，并用 `initexmf --update-fndb` 更新文件名数据库。这些命令可能不适用于当前 MiKTeX 版本，也不一定能解决所有 PDF 输出问题。

## XeLaTeX 输出

旧笔记建议尝试 `xelatex --no-pdf` 并检查 XDV 文件，然后添加 `fontspec` 和 OpenType 扩展名设置。请先确认实际错误与字体发现或 PDF 生成有关；不必要的字体设置可能改变文档输出。

## Nomenclature 编译顺序

旧流程使用 XeLaTeX、BibTeX、带 `nomencl.ist` 的 MakeIndex，最后再运行两次 XeLaTeX。具体顺序取决于文档和构建工具，请优先参考项目说明或 LaTeX 宏包当前文档。

## PDF 阅读器配色偏好

旧笔记使用黑色文字和浅灰色页面。这是阅读器偏好，不是故障修复；请在所用应用的辅助功能或页面显示设置中调整。
