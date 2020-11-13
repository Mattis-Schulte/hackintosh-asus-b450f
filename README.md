<img src="https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/Logos/OpenCore_with_text_Small.png" width="200" height="48"/>
⚠️ <b>OpenCore is still in beta. Please keep this in mind.</b>

**macOS Big Sur**: 11.0.1 (20B29)  Triple Boot w/ **Windows 10**: 20H2 and **Ubuntu**: 20.04.1 LTS (Focal Fossa)

**OpenCore version**: 0.6.3 <br>

## My System
| **Component** | **Model** |
| ------------- | --------- |
| CPU | AMD Ryzen 7 2700X @ 3.7GHz |
| Motherboard | ASUS ROG Strix B450-F Gaming |
| GPU | AMD Radeon RX 580 |
| RAM | 32GB @ 3000MHz |

### Software needed
1. gibMacOS: https://github.com/corpnewt/gibMacOS
2. GenSMBIOS: https://github.com/corpnewt/GenSMBIOS 
3. ProperTree: https://github.com/corpnewt/ProperTree
4. Clover Configurator: https://www.macupdate.com/app/mac/61090/clover-configurator

### Recommended software
1. AMD Power Gadget: https://github.com/trulyspinach/SMCAMDProcessor/releases - To read and adjust CPU clock frequencies
2. Monitor Control: https://github.com/MonitorControl/MonitorControl/releases - For adjusting the brightness of an external monitor

## Installation
  1. Format a USB stick, preferably USB 3, with the NTFS file system
  2. Then download [**gibMacOS**](https://github.com/corpnewt/gibMacOS) and open "gibMacOS.bat" as administrator. Install Python if necessary.
  3. After that, when you see the different macOS version, press R to get only the recovery versions that are significantly smaller but still work.
  4. In the list that is now displayed, select operating system version you want, which has to be marked as "Full Install" and hit enter.
  5. Now open "MakeInstall.bat" as administrator, then enter the respective number for your USB stick, as well as the letter o not the number zero (for example "3o").
  6. Wait until it is finished and then enter the path to the macOS recovery file that you just downloaded.
  7. When this is complete, you will now see a USB device called "BOOT" replaced the "EFI" folder contained in it with the one that is contained in this repo.
  
  8. Download [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) and open "GenSMBIOS.bat". Then press 1 and then 2, enter the path to the config.plist that is saved on the "BOOT" USB stick under EFI > OC .
  9. After that press 3 and type in "iMacPro1,1". Then press enter, if you now see a random number combination in the window that follows, you have done everything correctly so far.
  10. Now open the config.plist with "[**ProperTree.bat**](https://github.com/corpnewt/ProperTree)", then enter the MAC address of your Ethernet port under Root > PlatformInfo > Generic > ROM .
  11. Now boot from the USB stick after deactivating secure boot, fast boot, and csm in the BIOS and unplugging all hard drives, apart from a single blank one on which you want to install macOS.
  12. After you have set up macOS, open [**Clover Configurator**](https://www.macupdate.com/app/mac/61090/clover-configurator) and mount the EFI partition with it. Then copy the EFI folder from the USB stick to the hard drive.

> Set OS Type in your BIOS to `Other OS` if you're having issues booting the macOS installer.

> If you are using a Navi-based graphics card instead of Polaris or Vega, you will also need to download [**ProperTree**](https://github.com/corpnewt/ProperTree) and open EFI/OC/config.plist with it. Then add `agdpmod=pikera` to your boot-arguments (NVRAM > Add > 7C436110-AB2A-4BBB-A880-FE41995C9F82 > boot-args).

### Please also note that the sleep mode may not work if:
1. USB 2.0 device plugged into the motherboard's USB 3.x I/O ports<br>
2. USB 3.x device plugged into the motherboard's USB 2.0 I/O ports<br>
3. USB 2.0 device connected to a USB 3.x hub and plugged into the motherboard's USB 3.x I/O port, sleep only works when the hub is plugged into a USB 2.0 I/O port.<br>
- [**Source**](https://amd-osx.com/forum/viewtopic.php?f=61&t=9294)

### Fixing Windows time
1. If your time in Windows is no longer displayed as intended, install the "Windows Universal Time.reg" file in Windows.
