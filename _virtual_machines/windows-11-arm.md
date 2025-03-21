---
title: Windows 11
architecture: ARM64
memory: 8 GiB
disk: 20 GiB
display: VGA
spice_installed: true
username:
password:
screenshot: windows-11.png
download: 
---

This guide is designed to only work with Apple Silicon Macs.

## Downloads

* [UTM for Mac](https://github.com/utmapp/UTM/releases)
* [Windows for ARM](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewARM64)
* [SPICE Guest Tools]({% link support.md %})

## Instructions

1. Open UTM and click the "+" button to open the VM creation wizard.
2. Select "Virtualize".
3. Select "Windows".
4. Click "Browse" and select the Windows VHDX downloaded above. Press "Next" to continue.
5. Pick the amount of RAM and CPU cores you wish to give access to the VM. Press "Next" to continue.
6. If you have a directory you want to mount in the VM, you can select it here. Alternatively, you can skip this and select the directory later from the VM window's toolbar. The shared directory will be available after installing SPICE tools (see below). Press "Next" to continue.
7. Press "Save" to create the VM and press the Run button to start the VM.
8. Follow the Windows installer. If you have issues with the mouse, press the mouse capture button in the toolbar to send mouse input directly. Press Control+Option together to exit mouse capture mode. Sometimes, due to driver issues, you can enter and exit capture mode and the mouse cursor works normally again.
9. Once installation is complete and you've logged in, we can proceed to install the guest tools. With the ISO mounted in the D: drive, open Windows Explorer and browse to `D:\`. Run `spice-guest-tools-xxx.exe` which should install all drivers along with QEMU agent, SPICE agent (for copy/paste and dynamic resolution), and shared directory.

## Troubleshooting

### Ping does not work

Note that due to libslirp limitations, `ping` will not work and so Windows may think that there is still no internet connection.

### Networking does not work

Make sure you installed the SPICE guest tools, which includes the network drivers.
