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
