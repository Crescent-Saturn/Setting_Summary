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


### LaTeX moderncv No PDF output solution (MiKTeX):

cmd:        
    initexmf --mkmaps  
    initexmf --update-fndb  
	
