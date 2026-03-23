### Installation of Pycocotools in Windows
#### 1. Preparation of environment
1. Install Miniconda
2. Create a environment for project
   ```
   conda create -n env_name python 
   ```

#### 2. Install MSVC compiler 14.0 +
1. Download MSVC build tools from [here](https://www.visualstudio.com/downloads/#build-tools-for-visual-studio-2019)
2. In Build tools, install C++ build tools and ensure the latest versions of `MSVCv142 - VS 2019 C++ x64/x86 build tool`s and `Windows 10 SDK` are checked.
3. Add MSVC into your sys Path
4. Try to install pycocotools with:
   ```
   pip install pycocotools
   ```
   if returns with error like:
   `C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\link.exe' failed with exit status 1158`, continue with step 5
5. Add this to your PATH environment variables:\
`C:\Program Files (x86)\Windows Kits\10\bin\x64`

Copy these files `rc.exe` & `rcdll.dll` from:\
`C:\Program Files (x86)\Windows Kits\8.1\bin\x86` to\
`C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\bin`

#### 3. Install pycocotools wih pip
```
pip install pycocotools
```

Continue your project with pycocotools installed.