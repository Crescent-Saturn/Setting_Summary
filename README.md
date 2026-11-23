# 个人设备配置知识库

这是个人设备、开发环境与常用工具的配置知识库，用于按步骤重建环境、查找问题和复用配置文件。未经近期实际测试的内容会标记为 **待复核**，不会视作已验证操作。

> **Language / 语言：** 中文为默认版本；英文文档见对应的 [`*_en.md`](README_en.md) 页面。

## 从这里开始

- **配置新设备：** [配置清单](profiles/README.md)
- **查找系统设置：** [Windows](docs/platforms/windows.md) · [Linux](docs/platforms/linux.md)
- **查找软件：** [软件目录](docs/topics/software-catalog.md)
- **配置开发工具：** [开发环境](docs/topics/cross-platform/developer-environment.md) · [SSH 与 Git](docs/topics/cross-platform/ssh-git.md)
- **排查已知问题：** [故障排查索引](docs/troubleshooting/README.md)
- **复用配置文件：** [配置文件索引](configs/README.md)

## 仓库结构

| 路径 | 用途 |
|---|---|
| `profiles/` | 按顺序执行的设备和工作负载配置清单 |
| `docs/platforms/` | 操作系统专属的行为和偏好 |
| `docs/topics/` | 跨平台工具与硬件主题 |
| `docs/troubleshooting/` | 问题现象、诊断、处理方式和验证 |
| `configs/` | 可复用配置文件和已清理敏感信息的示例 |
| `templates/` | 新增条目时使用的模板 |

## 维护原则

每项设置只在一个文档中维护，并从配置清单链接到对应说明。区分必需步骤、建议步骤和可选偏好。未经测试或与版本相关的步骤应标为 **待复核**；只有在特定环境中实际测试后，才填写验证环境和日期。仓库中不得保存凭据、私钥、激活码或内部主机名。

重组时已从当前 README 删除一条旧激活字符串，但它仍可能存在于 Git 历史中。如果该字符串曾有效或涉及敏感信息，请联系供应商撤销或更换，并评估是否需要清理仓库历史。
