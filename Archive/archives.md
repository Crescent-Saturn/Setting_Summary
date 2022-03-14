
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

