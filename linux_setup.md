## Linux set-up and configuration

### Installation (Dual boot in two disks)
1. Choose the target disk (ex: sdb1), format into `ext4` and choose `/` as `partion`
2. (optional) Make auto-login enabled when creating the account
3. Set the timezone to make dual ssys time sync:
    ```
    sudo hwclock --systohc --localtime
    sudo hwclock --systohc --localtime
    ```
4. Update and upgrade the system before installing anything:
    ```
    sudo apt update && sudo apt upgrade
    ```
5. Install essential softwares:
    ```
    sudo apt install git vim curl cmake imagemagic
    ```
6. Config vim using `.vimrc` [here](https://github.com/Crescent-Saturn/Setting_Summary/blob/dev/.vimrc), copying into `/home/` and `.bashrc` as personal habitude.
7. Grub personalization:
    ```
    sudo apt install grub-customize
    ```
    Download Tela grub theme [here](https://www.gnome-look.org/p/1307852/), and install with its bash file.
8. Gnome extras:
    ```
    sudo apt intall chrome-gnome-shell gnome-shell-extensions gnome-sushi
    ```
    `gnome-sushi` is for QuickLook in Linux.    
    For the extensions, install `open-weather` and `Bing Wallpaper changer`, then make the proper adjustments.
9. Visudo:
    ```
    sudo visudo
    Defaults env_reset, pwfeedback, timestamp_timeout=30
    ```

10. Zsh || Oh-my-zsh
    Follow the github [ohmyzsh](https://github.com/ohmyzsh/ohmyzsh).
    1. Install zsh (No need to set zsh as default shell)
    ```
    sudo apt install zsh
    ```
    2. Install Oh My Zsh
    ```
    sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
    3. Adjust `.bashrc` to `.zshrc`
    4. Select a theme (in `.zshrc` file)
    ```
    ZSH_THEME="ys"
    ```
    5. Add plugins
    ```
    plugins=(git history zsh-autosuggestions colored-man-pages)
    ```
    **Ex**: zsh autosuggestions
    ```
    git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    ```
    zsh-syntax-highlighting
    ```
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    ```
    **colored-man-pages**

### Work environment settings
#### IDE tools preparation:
- Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html)   
- Install [VSCode](https://code.visualstudio.com/download)  

**1. Conda settins:**

```
conda config --append channels conda-forge
conda config --set channel_priority true
```

**2. VSCode extensions:**
 - Python
 - Bracket Pair Colorizer
 - Path Intellisense
 - Better Comments
 - TODO Tree
 - Markdown Preview Enhanced
 - vscode-icons
 - Remote SSH
 - Git Graph

**3. Coding fonts**
- [Cascadia Code](https://github.com/microsoft/cascadia-code)

#### PyTorch
Following the website tutorial [here](https://pytorch.org/get-started/locally/).