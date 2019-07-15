# Setting_Summary
Setting summary for OS, IDE, Sys, etc.


## Sublime Text 3  
**Package Control**:     
ST3 `View->Show Consol` :       


	import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)



**Packages**:		
- ConvertToUTF8
- Anaconda
- Material Theme
- LatexTools
- SublimeREPL
- ExportHtml
- InputArgs

**New Build** (Python3 Example)	        
`Tools -> Build System -> New Build System`

    {       
        "cmd": ["/usr/bin/python3","-u", "$file"], 
        "selector": "source.python", 
        "encoding": "utf8",
        "file_regex": "file \"(...*?)\", line ([0-9]+)"
    }
    
Saved As Python3.sublime-build.


## Windows 10

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

### LaTeX moderncv No PDF output solution (MiKTeX):

cmd:
    
    initexmf --mkmaps  
    initexmf --update-fndb  
     

### Xelatex without PDF output file (MikTex):
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



## FFmpeg convert audio files
cmd:

	for %a in ("*.mp3") do ffmpeg -i "%a" "%~na.m4a" 



## Linux (Deepin, Mint, Elementary OS, Xubuntu, Solus, etc.)
修复启动：		

	sudo grub-install /dev/sdb				% Deepin in sdb1, Elementary/Xubuntu/Solus in sdb2
	sudo grub-install --recheck /dev/sdb	% Windows 10 in sda SSD	
	sudo update-grub		
	sudo update-grub2		


设置时区（双系统同步）

	sudo hwclock --systohc --localtime
	sudo hwclock --systohc --localtime


Sudo visudo：		

	sudo visudo
	Defaults env_reset, pwfeedback, timestamp_timeout=30		% 30 min, pw will have * in terminal
	

uCareSystem Core 是一种能够自动执行基本的系统维护活动的轻型实用程序，另一方面它可以通过多种方式减少系统管理员的任务，节省大量时间。它没有任何 GUI，并提供纯粹的命令行界面来执行活动。  

	sudo add-apt-repository ppa:utappia/stable
	sudo apt update
	sudo apt install ucaresystem-core
	sudo ucaresystem-core

~~Upgrade all pip packages:~~      

~~pip list --format=legacy -o | cut -d' ' -f1 | xargs pip install -U~~
	
    
**Use conda instead of pip**
---

### PDF Reader background color:    
仿墨水屏的配色:    
文本颜色RGB：0,0,0    
页面背景色RGB：223,223,223    


### Conda tutorials    
  - Install miniconda
  - conda config --append channels conda-forge    
  - vim .condarc:    
  		channels:    
			- defaults    
		  	- conda-forge    
		channel_priority: true
  - conda update --all -y
  ...
