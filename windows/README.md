# Installer for Windows 10 or Windows 11

## Overall strategy

* Clean installation of Windows 10 or Windows 11.
* Install software using [winget](https://docs.microsoft.com/en-us/windows/package-manager/winget/).
* Install SDKs using [Scoop](https://scoop.sh/).
* Install others manually.

## BACKUP first before we install anything

* Desktop
* Downloads
* Workspace for IDEs
* Other folders under user's home (C:\Users\{account}\*)
* dotfiles

## OS installation

* Create a USB installation stick by downloading the tool/ISO for [Windows 10](https://www.microsoft.com/en-us/software-download/windows10ISO) or [Windows 11](https://www.microsoft.com/en-us/software-download/windows11) from Microsoft.
* **Optional**: Use [Rufus](https://rufus.ie/en/) to create bootable USB drives if needed.
* Enter BIOS and [set the USB to first boot option](https://www.asus.com/tw/support/FAQ/1008829/) then reboot.
  - For ZenBook, I use `F2`.
* Finish the Windows installation.
* Windows UPDATE first!
* Upgrade to **PRO** edition by changing product key.

## Basic system setup

* Setup theme, trackpad, bluetooth, etc.
* Enable [Hibernate Mode](https://www.groovypost.com/howto/enable-or-disable-hibernate-mode-on-windows-11/)
* Pin `Download` folder [on taskbar](https://www.makeuseof.com/windows-11-taskbar-pin-almost-anything/#how-to-pin-a-folder-to-windows-11-39-s-taskbar)
* Setup language, keyboard, input method
  - Add languages (zh-cn, zh-tw)
  - Download Boshiamy from [official website](https://boshiamy.com/)
  - Install and setup input method
* Install printer & scanner
    - Add printer using built-in driver, check this [video](https://www.youtube.com/watch?v=UDvTU_X9g2I)
    - ~~Don't need to download the driver from [official website](https://support.brother.com/g/b/downloadlist.aspx?c=tw&lang=en&prod=mfc1910w_eu_as&os=10068&flang=English)~~
    - How to scan document on Windows? check this [video](https://www.youtube.com/watch?v=8LtVTCvrYhA)
* Setup [WSL 2](https://docs.microsoft.com/en-us/windows/wsl/install)
  - Run Windows Terminal as administrator
  - Run the command below
    ```shell
    $ wsl --install
    ```
  - Reboot
  - Set up Linux user info
* Get **winget** command by install [App Installer](https://www.microsoft.com/en-us/p/app-installer/9nblggh4nns1) using Microsoft Store. If you need GUI for search, use [winget.run](https://winget.run/)
* Install [Scoop](https://scoop.sh/)
  ```
  Set-ExecutionPolicy RemoteSigned -scope CurrentUser
  ```
  ```
  Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')
  ```
* Install [PowerToys](https://docs.microsoft.com/en-us/windows/powertoys/)
  - Using winget
    ```shell
    winget install Microsoft.PowerToys --source winget
    ```
  - Remap shortcut
    * Home
    * End
    * Ctrl + Home
    * Ctrl + End

## Install software & SDKs

* Install [software](software.md) by running [script](install-software.bat)
  ```
  .\install-software.bat
  ```
* Install [SDKs](sdks.md) by running [scoop script](install-sdks.bat)
  ```
  .\install-sdks.bat
  ```

## Restore workspaces

* [Generate SSH keys]((https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent))
  ```shell
  # For Ed25519 algorithm
  $ ssh-keygen -t ed25519 -C "your_email@example.com"
  
  # For legacy system
  $ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
  ```
* Deploy SSH Key to:
  - GitHub
  - Gitlab
  - JetBrains Space
  - Servers (AWS, GCP, Aliyun, Laravel Forge, etc.)
* Restore dotfile
  - Clone dotfile
* Setup Windows Terminal
  - Re-link bin folder
  - Restore [configuration](https://docs.microsoft.com/en-us/windows/terminal/customize-settings/startup#center-on-launch)
* Setup & sync Dropbox
  - Workspace for IDEs
* Setup Google Drive
* Install/setup [WD Discovery](https://support.wdc.com/downloads.aspx?p=293)

## Reference

* [Scoop 官方文件](https://scoop-docs.vercel.app/apps/)
* 自動化安裝
  -[https://octopus.com/blog/automate-developer-machine-setup-with-chocolatey](https://octopus.com/blog/automate-developer-machine-setup-with-chocolatey)
  -[https://ttu.github.io/use-chocolatey-to-install-apps-windows-dev-machine/](https://ttu.github.io/use-chocolatey-to-install-apps-windows-dev-machine/)
* Windows Terminal 教學
  - [https://devmanna.blogspot.com/2021/01/developers-friend-windows-terminal.html](https://devmanna.blogspot.com/2021/01/developers-friend-windows-terminal.html)
* 設定 Terminal
  - [https://www.facebook.com/will.fans/videos/1534435513578893](https://www.facebook.com/will.fans/videos/1534435513578893)
* 軟體安裝清單
  - [https://blog.miniasp.com/post/2017/09/13/Will-2017-Ultimate-Developer-Tool-Software-List](https://blog.miniasp.com/post/2017/09/13/Will-2017-Ultimate-Developer-Tool-Software-List)
* 調整快速鍵
  - [Keyboard Shortcut to Cycle through Windows of same Application in Windows](https://stackoverflow.com/questions/11175261/keyboard-shortcut-to-cycle-through-windows-of-same-application-in-windows-7)
  - [Easy Window Switcher](https://neosmart.net/EasySwitch/)
  - [Shortcut in Windows 7 to switch between same application's windows, like Cmd + ` in OS X](https://superuser.com/questions/435602/shortcut-in-windows-7-to-switch-between-same-applications-windows-like-cmd)
  - [AutoHotkey](https://www.autohotkey.com/)
