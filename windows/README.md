# Installer for Windows 10

## Strategy

* Install Windows 10 manually.
* Install software using [Chocolatey](http://chocolatey.org/).
* Install SDKs using [Scoop](https://scoop.sh/).
* Install others manually.

## BACKUP first before we re-install

* User home
* Desktop
* Downloads
* IDE Workspace

## Pre-requirements

* Create an installation USB stick by downloading [the tool](https://www.microsoft.com/en-us/software-download/windows10%20) from Microsoft.
* Enter BIOS and [set the USB to first boot option](https://www.asus.com/tw/support/FAQ/1008829/) then reboot.
* Finish the Windows 10 installation.
* Upgrade to Windows 10 Pro edition by changing product key.
* Windows UPDATE!
* Setup trackpad, bluetooth mouse, etc.
* Open Microsoft store and install [Windows Terminal](https://www.microsoft.com/zh-tw/p/windows-terminal/9n0dx20hk701)

## Install software

* Install Chocolatey by using administrative shell ([Docs](https://chocolatey.org/install))
  ```
  Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
  ```
* Install [software](software.md) by running [chocolatey script](install-software.bat)
  ```
  .\install-software.bat
  ```

## Install SDKs

* Install Scoop
  ```
  Set-ExecutionPolicy RemoteSigned -scope CurrentUser
  ```
  ```
  Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')
  ```
* Install [SDKs](sdks.md) by running [scoop script](install-sdks.bat)
  ```
  .\install-sdks.bat
  ```

## Reference

* [https://octopus.com/blog/automate-developer-machine-setup-with-chocolatey]()
* [https://ttu.github.io/use-chocolatey-to-install-apps-windows-dev-machine/]()
* [https://docs.microsoft.com/en-us/windows/wsl/install-win10]()
* [https://scoop-docs.vercel.app/apps/]()
* [https://rdpapa.tw/2020/09/03/%E3%80%8Achocolatey-%E5%9C%A8windows-%E4%B8%8A%E7%9A%84%E5%A5%97%E4%BB%B6%E7%AE%A1%E7%90%86%E5%B7%A5%E5%85%B7-%E5%AD%B8%E7%BF%92%E7%AD%86%E8%A8%98%E3%80%8B%E5%B7%A5%E5%85%B7/]()
* [https://www.dotblogs.com.tw/yc421206/2021/06/05/chocolatey_config_install]()
* [https://blog.miniasp.com/post/2017/09/13/Will-2017-Ultimate-Developer-Tool-Software-List]()
* [https://stackoverflow.com/questions/44144253/should-i-disable-built-in-auto-update-of-packages-installed-by-chocolatey]()
