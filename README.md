# PC configuration summary
Setting summary for OS, IDE, Sys, Tools, etc.

## Table of Contents
- [PC configuration summary](#pc-configuration-summary)
		- [Table of Contents](#table-of-contents)
	- [1. Windows](#1-windows)
		- [1.1 系统优化](#11-系统优化)
		- [1.2 效率工具 (Win)](#12-效率工具-win)
	- [2. Linux](#2-linux)
 	- [3. Mac](#3-mac)
	- [4. Small tips](#4-small-tips)


<a name="Windows"></a>
## 1. Windows

### 1.1 系统优化
*(Windows 10)*
#### Disable data logging:
- Head to Settings > Privacy, and disable everything, unless there are some things you really need.
- While within the Privacy page, go to Feedback, select Never in the first box, and Basic in the second box.
- Head to Settings > Update and Security > Advanced Options > Choose how updates are delivered, and turn the first switch off.
- Disable Cortana by clicking the Search bar/icon.
- (Optional) Disable web search in Search by going to Settings, and turning off Search online and include web results.

#### cmd->gpedit.msc:

本地计算机 策略
- -->管理模板-->Windows组件
  1.  -->Windows更新-->配置自动更新-->启用--自动下载并通知安装
  2.  -->Windows Defender-->关闭 --> 启用
  3.  -->数据收集和预览版本-->禁用
  4.  -->OneDrive--禁止使用进行文件存储-->启用
- -->管理模板-->系统
  1. -->关机选项-->禁用


#### cmd->services.msc:
- HomeGroup Listener, Provider--> Disabled
- Superfetch-->Disabled

可以尝试以下方案检查系统文件完整性：
在管理员命令提示符下键入以下命令：

	Dism /Online /Cleanup-Image /ScanHealth

这条命令将扫描全部系统文件并和官方系统文件对比，扫描计算机中的不一致情况。

	Dism /Online /Cleanup-Image /CheckHealth

这条命令必须在前一条命令执行完以后，发现系统文件有损坏时使用。

	DISM /Online /Cleanup-image /RestoreHealth

这条命令是把那些不同的系统文件还原成官方系统源文件。

无论以上命令运行结果如何，运行完成后重启，再键入以下命令：

	sfc /SCANNOW

#### 电源计划－默认方案
用管理员命令运行 `sc config ndu start= disabled`


### 1.2 效率工具 (Win)

- **[QuickLook](http://pooi.moe/QuickLook/)**
> 空格预览工具，免费开源

- **[EarTrumpet](https://www.microsoft.com/en-us/p/eartrumpet/9nblggh516xp)**
> 最细致的音量调节软件

- **[PixPin](https://pixpin.cn/)** ~~[Snipaste]~~
> 截图 + 贴图

- **[PowerToys](https://github.com/microsoft/PowerToys)**
> Windows system utilities to maximize productivity

- **[TrafficMonitor](https://github.com/zhongyang219/TrafficMonitor)**
> 用于显示当前网速、CPU 及内存利用率的桌面悬浮窗软件，并支持任务栏显示和更换皮肤

#### WPS专业增强版 (May be out-dated)：
THUV2-32HH7-6NMHN-PTX7Y-QQCTH

<a name="Linux"></a>
## 2. Linux

Check [linux_setup.md](linux_setup.md) for more details.

## 3. Mac
<a name="Mac"></a>

### 实用软件

- **[PixPin](https://pixpin.cn/)** ~~[Snipaste]~~
> 截图 + 贴图

- **[EcoPaste](https://ecopaste.cn/)**
> 好用的剪贴板管理工具

- **[86五笔极点码表 for 鼠须管](https://github.com/KyleBing/rime-wubi86-jidian)**
> 五笔输入

- **[PicView](github.com/Ruben2776/PicView)**
> 图片查看工具

- **[Syntax Highlight](https://github.com/sbarex/SourceCodeSyntaxHighlight)**
> Quick Look 扩展程序查看源码

<a name="Small-tips"></a>
## 4. Small tips

**SSH config** \
`~/.ssh/config`:
```
### =============
### Basic
### =============
Host *
  AddKeysToAgent yes
  ServerAliveInterval 60
  ServerAliveCountMax 10

### =============
### GitHub
### =============
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519
  IdentitiesOnly yes

### =============
### GitLab
### =============
Host gitlab.com
  HostName gitlab.com
  User git
  IdentityFile ~/.ssh/id_ed25519
  IdentitiesOnly yes

### =============
### Remote Server
### =============
Host server_alias
  HostName server address
  User username
  IdentityFile ~/.ssh/id_ed25519
  IdentitiesOnly yes

```
Where `AddKeysToAgent yes` help prevent manually adding private-key everytime of login. Therefore it is set in *Basic*. \
For server connection, name one you like, but for GitLab AND GitHub connection (especially inside remote server), keep `Host` and `HostName` **SAME**!


**Merge TS file by CMD**
```
copy /b play*.ts play_new.ts
```
**PDF Reader background color:**

仿墨水屏的配色:
- 文本颜色RGB：`0,0,0    (HEX:000000)`
- 页面背景色RGB：`223,223,223 (HEX: E9E9E9)`

**Coding fonts**

 - [Cascadia Code](https://github.com/microsoft/cascadia-code)
 - [LXGW WenKai / 霞鹜文楷](https://github.com/lxgw/LxgwWenKai)

<details>
<summary>LaTeX related issues</summary>

**LaTeX moderncv No PDF output solution (MiKTeX)**

cmd:
```
initexmf --mkmaps
initexmf --update-fndb
```

**Xelatex without PDF output file (MikTex):**
cmd:

	xelatex --no-pdf test.tex
	xelatex --vv test.xdv

In .tex file add these lines:

	% Why do I need this one some computers and not others?
	\usepackage{fontspec} % Was able to fix it with this line
	\defaultfontfeatures{Extension = .otf} % ...and this line

Latex makenomenclature:

	xelatex main.tex
	bibtex ch1 ...etc
	makeindex main.nlo -s nomencl.ist -o main.nls
	xelatex main.tex
	xelatex main.tex

</details>
