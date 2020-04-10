# Retro Windows Terminal
Using Windows Terminal combined with Oh My Zsh and Powerline10K to make this cool little retro look!

![no opacity] (/images/bg2.jpg "no opacity")



If you already run zsh / oh my zsh then just replace the files from this repo for the ones on your system, backup first!
Images that I use for a background are also included and Windows Terminal JSON settings are towards the bottom of this page.

If you do not have anything installed then follow below, I'll try to be clear but it is assumed you have an understanding of terminals, linux, command line etc.

These are basic instructions to get a similar look in your terminal; I use WSL2 in Windows which currently needs a preview build of Win10 though the release version should be coming out around May 2020.

___

## WSL Software
Install ZSH:
```
https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH
```

Install Oh My ZSH:
```
https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH
```

Install P10k theme for ZSH
```
https://github.com/romkatv/powerlevel10k
```
___
Follow thier instructions to get fonts installed, these are vital to get the same look.
I am using FiraCode Nerd Font (non mono).
Your terminal must be set up to use the same font too, for Windows Terminal change the following line in the settings to match the font you are using:
```json
            "fontFace": "FiraCode Nerd Font",
```
___

## WSL Settings
Modify the file .zshrc usually located at ~/.zshrc and change the theme to:
```
ZSH_THEME="powerlevel10k/powerlevel10k"
``` 
This should the run the configuration wizard on next load of the terminal. The first three questions will check that font's are installed. If you are not seeing symbols correctly then go back and make sure the font is installed correctly.

If the font's are installed correctly you can either continue to set up your own look or copy the files from this repo and replace your ones.
Both files exist in the home dir of the installed linux os.
___
## Windows Terminal JSON Settings

Here are some additional Terminal settings that you will need to match the setup I am using.
Hovering over the key in vscode it will display what that key does.
Add the lines required to your Windows Terminal JSON file.

Fonts
Fonts should be installed on both Windows and Linux
They were a bit of work to get working as I wanted, using a Mono font resulted in smaller symbols than I wanted.

Home Directory
The "startingDirectory" key is to redirect to my linux home dir when I open a terminal window, default seems to direct the mounted Windows home dir which is not recommended for using software like Docker. Replace with your own as DISTRO & USER will be different on your setup.

```json
{
            "guid": "{7f586916-8357-53d4-bb2b-ca96f639898a}",
            "hidden": false,
            "name": "WLinux",
            "tabTitle": "WSL2",
            "source": "Windows.Terminal.Wsl",
            "startingDirectory": "\\\\wsl$\\DISTRO\\home\\USER\\",
            "closeOnExit": "always",
            "historySize": 9001,
            "fontFace": "FiraCode Nerd Font",
            "fontSize": 12,
            "padding": "8, 8, 8, 8",
            "useAcrylic": true,
            "acrylicOpacity": 0.2,
            "backgroundImage": "ms-appdata:///roaming/bg5.jpg",
            "backgroundImageOpacity": 0.5,
            "experimental.retroTerminalEffect": true
        },
```


Windows Terminal path to place images used for the background:
```
%LOCALAPPDATA%\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\RoamingState
```


Enjoy the little things like retro gaming looking terminals.
