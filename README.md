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

https://learn.microsoft.com/en-us/windows/wsl/connect-usb

## Error 'usbipd: error: Mounting 'C:\Program Files\usbipd-win\WSL' within WSL failed.' in PowerShell
Use this command in WSL

`$ sudo mount -t drvfs -o "ro,umask=222" "C:\Program Files\usbipd-win\WSL" "/var/run/usbipd-win"`

# Introduction

The [WSL2-Linux-Kernel][wsl2-kernel] repo contains the kernel source code and
configuration files for the [WSL2][about-wsl2] kernel.

# Reporting Bugs

If you discover an issue relating to WSL or the WSL2 kernel, please report it on
the [WSL GitHub project][wsl-issue]. It is not possible to report issues on the
[WSL2-Linux-Kernel][wsl2-kernel] project.

If you're able to determine that the bug is present in the upstream Linux
kernel, you may want to work directly with the upstream developers. Please note
that there are separate processes for reporting a [normal bug][normal-bug] and
a [security bug][security-bug].

# Feature Requests

Is there a missing feature that you'd like to see? Please request it on the
[WSL GitHub project][wsl-issue].

If you're able and interested in contributing kernel code for your feature
request, we encourage you to [submit the change upstream][submit-patch].

# Build Instructions

Instructions for building an x86_64 WSL2 kernel with an Ubuntu distribution are
as follows:

1. Install the build dependencies:  
   `$ sudo apt install build-essential flex bison dwarves libssl-dev libelf-dev`
2. Build the kernel using the WSL2 kernel configuration:  
   `$ make KCONFIG_CONFIG=Microsoft/config-wsl`

# Install Instructions

Please see the documentation on the [.wslconfig configuration
file][install-inst] for information on using a custom built kernel.

[wsl2-kernel]:  https://github.com/microsoft/WSL2-Linux-Kernel
[about-wsl2]:   https://docs.microsoft.com/en-us/windows/wsl/about#what-is-wsl-2
[wsl-issue]:    https://github.com/microsoft/WSL/issues/new/choose
[normal-bug]:   https://www.kernel.org/doc/html/latest/admin-guide/bug-hunting.html#reporting-the-bug
[security-bug]: https://www.kernel.org/doc/html/latest/admin-guide/security-bugs.html
[submit-patch]: https://www.kernel.org/doc/html/latest/process/submitting-patches.html
[install-inst]: https://docs.microsoft.com/en-us/windows/wsl/wsl-config#configure-global-options-with-wslconfig
