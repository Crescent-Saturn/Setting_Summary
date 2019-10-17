# PC configuration summary
Setting summary for OS, IDE, Sys, Tools, etc.

## Table of Contents
1. [Windows](#Windows)
2. [Linux](#Linux)
3. [Essential Tools](#Essential-Tools)
	1. [Cross platform](#Cross-platform)
	2. [Open source](#Open-source)



<a name="Windows"></a>
### 1. Windows
*(Windows 10)*
**Disable data logging**:		
- Head to Settings > Privacy, and disable everything, unless there are some things you really need.
- While within the Privacy page, go to Feedback, select Never in the first box, and Basic in the second box.
- Head to Settings > Update and Security > Advanced Options > Choose how updates are delivered, and turn the first switch off.
- Disable Cortana by clicking the Search bar/icon.
- (Optional) Disable web search in Search by going to Settings, and turning off Search online and include web results.

cmd->gpedit.msc:	        
本地计算机 策略        
-->管理模板-->Windows组件         
       1.  -->Windows更新-->配置自动更新-->启用--自动下载并通知安装        
       2.  -->Windows Defender-->关闭 --> 启用        
       3.  -->数据收集和预览版本-->禁用       
       4.  -->OneDrive--禁止使用进行文件存储-->启用            
-->管理模板-->系统        
       1. -->关机选项-->禁用      
       
       
cmd->services.msc:      
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


<a name="Linux"></a>
### 2. Linux
**修复启动：**		

	sudo grub-install /dev/sdb				% Deepin in sdb1, Elementary/Xubuntu/Solus in sdb2
	sudo grub-install --recheck /dev/sdb	% Windows 10 in sda SSD	
	sudo update-grub		
	sudo update-grub2		


**设置时区（双系统同步）**

	sudo hwclock --systohc --localtime
	sudo hwclock --systohc --localtime


**Sudo visudo：**		

	sudo visudo
	Defaults env_reset, pwfeedback, timestamp_timeout=30		% 30 min, pw will have * in terminal
	

>~~Upgrade all pip packages:~~      

>~~pip list --format=legacy -o | cut -d' ' -f1 | xargs pip install -U~~
	   
**Use conda instead of pip**

**Conda tutorials**
>  - Install miniconda
>  - conda config --append channels conda-forge    
>  - vim .condarc:    
  		channels:    
			- defaults    
		  	- conda-forge    
		channel_priority: true
>  - conda update --all -y
  ...

**FFmpeg convert audio files**
cmd:

	for %a in ("*.mp3") do ffmpeg -i "%a" "%~na.m4a" 



**[terminal-colors-branch](https://gist.github.com/danielalvarenga/2df8cabbd6f3041c2378)**

Display git branches in terminal:
```
# Add in ~/.bashrc or ~/.bash_profile
function parse_git_branch () {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
 
RED="\[\033[01;31m\]"
YELLOW="\[\033[01;33m\]"
GREEN="\[\033[01;32m\]"
BLUE="\[\033[01;34m\]"
NO_COLOR="\[\033[00m\]"

# without host
PS1="$GREEN\u$NO_COLOR:$BLUE\w$YELLOW\$(parse_git_branch)$NO_COLOR\$ "
# with host
# PS1="$GREEN\u@\h$NO_COLOR:$BLUE\w$YELLOW\$(parse_git_branch)$NO_COLOR\$ "
```

**Vim**
Check `.vimrc` [here](https://github.com/Crescent-Saturn/Setting_Summary/blob/dev/.vimrc) for details. Copy to `/home/`.

<a name="Essential-Tools"></a>
### 3. Essential Tools

<a name="Cross-platform"></a>
#### 3.1 Cross platform
**Sublime Text 3**  
*Package Control*:    
ST3 `View->Show Consol` :       


	import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)


*Packages*:
- ConvertToUTF8
- Anaconda
- LatexTools
- SublimeREPL
- ExportHtml
- InputArgs
- Side

**New Build** (Python3 Example or conda/envs/python)	        
`Tools -> Build System -> New Build System`

    {       
    "cmd": ["/usr/bin/python3","-u", "$file"], 
    "selector": "source.python", 
    "encoding": "utf8",
    "file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",

    }

Saved As Python3.sublime-build.

More details for setting can be found [here](https://github.com/Crescent-Saturn/Setting_Summary/blob/dev/Preferences.sublime-settings).

Anaconda plugin setting for Sublime Text can be found [here](https://github.com/Crescent-Saturn/Setting_Summary/blob/dev/Anaconda.sublime-settings)



**PDF Reader background color:**

仿墨水屏的配色:    
文本颜色RGB：0,0,0    (HEX:000000)    
页面背景色RGB：223,223,223 (HEX: E9E9E9)    

**[TrafficMonitor](https://github.com/zhongyang219/TrafficMonitor)**
*Windows 10*:
> 用于显示当前网速、CPU 及内存利用率的桌面悬浮窗软件，并支持任务栏显示和更换皮肤

**[QuickLook](http://pooi.moe/QuickLook/)**
Windows 空格预览工具，免费开源

<a name="Open-source"></a>
#### 3.2 Open source

**Coding fonts**

 - [Cascadia Code](https://github.com/microsoft/cascadia-code)
 - [Source Code Pro](https://fonts.google.com/specimen/Source+Sans+Pro)
