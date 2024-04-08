This method works with kali-linux distribution. Tested with TP-Link Archer T2U PLUS.

Kernel Source Code:

https://github.com/microsoft/WSL2-Linux-Kernel

# Make kernel

`$ make KCONFIG_CONFIG=Microsoft/config-wsl modules`

`$ make KCONFIG_CONFIG=Microsoft/config-wsl modules_install`

`$ make KCONFIG_CONFIG=Microsoft/config-wsl`

Then follow instruction to change the .wslconfig file from:

https://learn.microsoft.com/en-us/community/content/wsl-user-msft-kernel-v6

# RTL8821AU driver
Git clone this repo and follow the instruction to install the driver.

https://github.com/morrownr/USB-WiFi

# Connecting Wifi adapter 

Follow the instruction normally.

https://learn.microsoft.com/en-us/windows/wsl/connect-usb

## Error 'usbipd: error: Mounting 'C:\Program Files\usbipd-win\WSL' within WSL failed.'

Use this command in WSL

`$ sudo mount -t drvfs -o "ro,umask=222" "C:\Program Files\usbipd-win\WSL" "/var/run/usbipd-win"`


[wsl2-kernel]:  https://github.com/microsoft/WSL2-Linux-Kernel
[about-wsl2]:   https://docs.microsoft.com/en-us/windows/wsl/about#what-is-wsl-2
[wsl-issue]:    https://github.com/microsoft/WSL/issues/new/choose
[normal-bug]:   https://www.kernel.org/doc/html/latest/admin-guide/bug-hunting.html#reporting-the-bug
[security-bug]: https://www.kernel.org/doc/html/latest/admin-guide/security-bugs.html
[submit-patch]: https://www.kernel.org/doc/html/latest/process/submitting-patches.html
[install-inst]: https://docs.microsoft.com/en-us/windows/wsl/wsl-config#configure-global-options-with-wslconfig
