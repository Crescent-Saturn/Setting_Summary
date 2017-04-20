# Setting_Summary
Setting summary for OS, IDE, Sys, etc.


## Sublime Text 3  
**Package Control**:     
ST3  `ctrl+`` or  ``View->Show Consol` :    
```
	import urllib.request,os,hashlib; h = 'df21e130d211cfc94d9b0905775a7c0f' + '1e3d39e33b79698005270310898eea76'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```	
	
**Packages**:		
- ConvertToUTF8
- Anaconda
- Material Theme
- LatexTools        

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


### LaTeX moderncv No PDF output solution (MiKTeX):

cmd:        
    initexmf --mkmaps  
    initexmf --update-fndb  
	
## Linux (Deepin, Elementary OS, Xubuntu, Solus, etc.)
修复启动：		

	sudo grub-install /dev/sdb				% Deepin in sdb1, Elementary/Xubuntu/Solus in sdb2
	sudo grub-install --recheck /dev/sdb	% Windows 10 in sda SSD	
	sudo update-grub		
	sudo update-grub2		


Sudo visudo：		

	sudo visudo
	Defaults env_reset, pwfeedback, timestamp_timeout=30		% 30 min, pw will have * in terminal
	
