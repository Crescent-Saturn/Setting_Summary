# PC configuration summary
Setting summary for OS, IDE, Sys, Tools, etc.

## Table of Contents
- [PC configuration summary](#pc-configuration-summary)
	- [Table of Contents](#table-of-contents)
		- [1. Windows](#1-windows)
			- [1.1 系统优化](#11-%e7%b3%bb%e7%bb%9f%e4%bc%98%e5%8c%96)
			- [1.2 LaTeX 相关](#12-latex-%e7%9b%b8%e5%85%b3)
			- [1.3 效率工具 (UWP)](#13-%e6%95%88%e7%8e%87%e5%b7%a5%e5%85%b7-uwp)
		- [2. Linux](#2-linux)
		- [3. Small tips](#3-small-tips)



<a name="Windows"></a>
### 1. Windows

#### 1.1 系统优化
*(Windows 10)*
**Disable data logging**:		
- Head to Settings > Privacy, and disable everything, unless there are some things you really need.
- While within the Privacy page, go to Feedback, select Never in the first box, and Basic in the second box.
- Head to Settings > Update and Security > Advanced Options > Choose how updates are delivered, and turn the first switch off.
- Disable Cortana by clicking the Search bar/icon.
- (Optional) Disable web search in Search by going to Settings, and turning off Search online and include web results.

**cmd->gpedit.msc**:	        
本地计算机 策略        
-->管理模板-->Windows组件         
    1.  -->Windows更新-->配置自动更新-->启用--自动下载并通知安装        
    2.  -->Windows Defender-->关闭 --> 启用        
    3.  -->数据收集和预览版本-->禁用       
    4.  -->OneDrive--禁止使用进行文件存储-->启用            
-->管理模板-->系统        
    1. -->关机选项-->禁用      
       
       
**cmd->services.msc**:      
HomeGroup Listener, Provider--> Disabled       
Superfetch-->Disabled       

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

电源计划－默认方案
用管理员命令运行“sc config ndu start= disabled”

WPS专业增强版：
THUV2-32HH7-6NMHN-PTX7Y-QQCTH

#### 1.2 LaTeX 相关
**LaTeX moderncv No PDF output solution (MiKTeX)**

cmd:
    
    initexmf --mkmaps  
    initexmf --update-fndb  
     

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

#### 1.3 效率工具 (UWP)

**[TrafficMonitor](https://github.com/zhongyang219/TrafficMonitor)**  
> 用于显示当前网速、CPU 及内存利用率的桌面悬浮窗软件，并支持任务栏显示和更换皮肤

**[QuickLook](http://pooi.moe/QuickLook/)**  
> 空格预览工具，免费开源

**[EarTrumpet](https://www.microsoft.com/en-us/p/eartrumpet/9nblggh516xp)**  
> 最细致的音量调节软件

**[Snipaste](http://zh.snipaste.com/)** 
> 截图 + 贴图 

**[PowerToys](https://github.com/microsoft/PowerToys)**
> Windows system utilities to maximize productivity


<a name="Linux"></a>
### 2. Linux

Check [linux_setup.md](https://github.com/Crescent-Saturn/Setting_Summary/blob/dev/linux_setup.md) for more details.

<a name="Small-tips"></a>
### 3. Small tips

**Merge TS file by CMD**    
    
	copy /b play*.ts play_new.ts

**PDF Reader background color:**

仿墨水屏的配色:    
文本颜色RGB：0,0,0    (HEX:000000)    
页面背景色RGB：223,223,223 (HEX: E9E9E9)    

**Coding fonts**

 - [Cascadia Code](https://github.com/microsoft/cascadia-code)
 - [Source Code Pro](https://fonts.google.com/specimen/Source+Sans+Pro)
