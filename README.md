# Ubuntu General Configuration
## First of all, a brew software list needed...
| Name | Use |
| ------ | ------ |
| [i3-gaps](https://github.com/Airblader/i3) | Tiling window manager for X11, adding a few additional features such as gaps between windows. |
| [feh](http://manpages.ubuntu.com/manpages/bionic/man1/feh.1.html) | image viewer that can also be used to manage the desktop wallpaper for standalone window managers. |
| [fonts](https://www.nerdfonts.com/) | A simple and cool font collection. |
| [rofi](https://github.com/davatorium/rofi) | A simple search menu. |
| [bumblebee-status](https://bumblebee-status.readthedocs.io/en/latest/)  | Modular, theme-able [status line generator](https://github.com/tobi-wan-kenobi/bumblebee-status) for the i3 window manager. |
| [compton](https://manpages.ubuntu.com/manpages/bionic/man1/compton.1.html) | Compositor for X11 |
|Lxrandr| A GUI for xrandr|
|lxappearance|A simple GUI to change theme files and folder icons|

### Step by Step
Installing i3-gaps for Ubuntu
```
sudo add-apt-repository ppa:kgilmer/speed-ricer
sudo apt install i3-gaps
```
I3 config file will be avaible at the wiki
### Theme
We've choosen [Dracula Theme](https://draculatheme.com/) for many of my software apps.
- Dracula theme for Firefox
    ```
     git clone https://github.com/dracula/firefox.git
    ```
    1. Open Firefox and go to about:addons
    2. Themes > Settings > Install addon from file... > Your .xpi file

- Dracula theme for Gnome Terminal
    ```
    sudo apt-get install dconf-cli
    git clone https://github.com/dracula/gnome-terminal
    cd gnome-terminal
    ./install.sh
    ```
- Dracula theme for Gedit
    ```
    wget https://raw.githubusercontent.com/dracula/gedit/master/dracula.xml
    mv dracula.xml $HOME/.local/share/gedit/styles/
    ```
    - Activate in Gedit's preferences dialog
- Dracula theme for rofi
    ```
    git clone https://github.com/dracula/rofi
    sudo mkdir ~/.config/rofi
    ```
    - Copy the config.rasi file into ~/.config/rofi
- Dracula theme for Visual Studio Code
    - Go to View -> Command Palette or press Ctrl+Shift+P
    - Then enter Install Extension
    - Write Dracula Official
    - Select it or press Enter to install

- Install dracula theme for Visual Studio Code using Git
    ```
    git clone https://github.com/dracula/visual-studio-code.git ~/.vscode/extensions/theme-dracula
    cd ~/.vscode/extensions/theme-dracula
    npm install
    npm run build
    ```
    - Copy the config.rasi file into ~/.config/rofi
    
- Dracula theme for Telegram
    - Download using the [GitHub .zip download](https://github.com/dracula/telegram/archive/master.zip) option and unzip them.

    Activating theme
    
    1. In Telegram Desktop, go to setting, active option Bubble Mode and under the Chat background section click on Choose from file.
    
    2.Select the colors.tdesktop-theme file you just downloaded.
    
    3.Click Keep Changes to apply the theme.

- Install dracula theme for Zathura
    ```
    git clone https://github.com/dracula/zathura ~/.config/zathura/
    ```
    - Activating theme

        Double check that it cloned correctly
        Enjoy!

- [AMD DRIVERS UBUNTU](https://drivers.amd.com/drivers/linux/amdgpu-pro-20.20-1098277-ubuntu-20.04.tar.xz)

- Vulkan shaders for ubuntu
```
sudo add-apt-repository ppa:oibaf/graphics-drivers
sudo apt update
sudo apt upgrade
apt install libvulkan1 mesa-vulkan-drivers vulkan-utils
```






