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
* Open Windows store and install [Windows Terminal](https://www.microsoft.com/zh-tw/p/windows-terminal/9n0dx20hk701)

## Install software

* Install Chocolatey by using administrative shell ([Docs](https://chocolatey.org/install))
  ```
  Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
  ```
* Install [software](software.md) by running [chocolatey script](software.bat)

## Install SDKs

* Install Scoop
  ```
  Set-ExecutionPolicy RemoteSigned -scope CurrentUser
  ```
  ```
  Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')
  ```
* Install [SDKs](sdks.md) by running [scoop script](install-sdks.bat)

## Reference

* [https://octopus.com/blog/automate-developer-machine-setup-with-chocolatey]
* [https://ttu.github.io/use-chocolatey-to-install-apps-windows-dev-machine/]
* [https://docs.microsoft.com/en-us/windows/wsl/install-win10]
* [https://scoop-docs.vercel.app/apps/]
 
