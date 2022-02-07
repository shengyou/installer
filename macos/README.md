# Installer for macOS

## Overall strategy

* Clean installation of macOS (Big sur or Monterey).
* Install software using [Homebrew](https://brew.sh/).
* Install SDKs using dedicated tools (Homebrew, SDKMAN).
* Install others manually.

## BACKUP first before we install anything

* Desktop
* Downloads
* Workspace for IDEs
* Other folders under user's home (~/) 

* dotfiles (ssh key, config, zsh…)
* ~/Library/Colors

* Trainings
* Research
* Writing
* Wallpapers
* Products
* Projects

## OS installation

* **Optional**: disable Activation lock
  - Follow this guide ([en-us](https://support.apple.com/en-us/HT206989) | [zh-tw](https://support.apple.com/zh-tw/HT206989)) if we can't use internet recovery.
* **Recommend**: plug ethernet cables for internet access, it's faster and more convenience. Don't spend time to config the wireless password.
* Reboot mac and hold `Option-Command-R`.
* Must **ERASE** entire disk for **CLEAN INSTALLATION**, follow this guide ([en-us](https://support.apple.com/zh-tw/HT208496) | [zh-tw](https://support.apple.com/zh-tw/HT208496)).
* Install the latest macOS by following this guide ([en](https://support.apple.com/en-us/HT204904) | [zh](https://support.apple.com/zh-tw/HT204904)).
* Finish the installation process (setup Apple ID, Touch ID, Google account, etc.).

## Basic system setup

* Setup theme, trackpad, etc.
  - [Hide recent apps from dock](https://www.howtogeek.com/714379/how-to-hide-recent-apps-from-the-mac-dock)
* Setup input method
  - Download Boshiamy from [official website](https://boshiamy.com/)
  - Install and setup input method
* Install Setapp
  - Download installer from [official website](https://setapp.com/download)
  - Login
  - Download apps
* Install printer & scanner
  - Download driver from [official website](https://support.brother.com/g/b/downloadlist.aspx?c=tw&lang=en&prod=mfc1910w_eu_as&os=10072&flang=English)
  - Install printer driver and scanner driver separately
  - Add printer and driver
* Install [Homebrew](https://brew.sh/) for automation.
  ```
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  ```

## Install software & SDKs

* Install [software](software.md) using [bash script](install-software.sh).
* Install [SDKs](sdks.md) using [bash script](install-sdks.sh)

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
* Setup iTerm
  - Add [JetBrains Mono](https://www.jetbrains.com/lp/mono/) fonts
  - Add [Darcula theme](https://draculatheme.com/iterm)
  - Re-link bin folder
* Setup & sync Dropbox
  - Workspace for IDEs
* Setup Google Drive
* Install/setup [WD Discovery](https://support.wdc.com/downloads.aspx?p=293#WD_softwaremac)

## Boshiamy alternative

* https://journal.travelhackfun.com/2021/05/27/%E5%98%B8%E8%9D%A6%E7%B1%B3mac-os%E5%AE%89%E8%A3%9D-%E5%8F%AA%E8%A6%815%E5%88%86%E9%90%98%EF%BC%8C%E5%9C%A8mac-os%E4%B8%8A%E5%85%8D%E8%B2%BB%E4%BD%BF%E7%94%A8openvanilla%E6%B0%B8%E4%B9%85%E5%AE%89/
* https://vocus.cc/article/5f9fd5c3fd89780001d1ca4b
* https://blog.typeart.cc/rime-liur/guide/

## References

* https://william-weng.github.io/2019/07/12/homebrew-helloworld/
* https://www.onejar99.com/mac-homebrew-homebrew-cask-mac/#Homebrew-2
* https://blog.visioncan.com/2014/introducing-cask/
