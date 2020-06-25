<p align="center">
	<img src="https://ibin.co/5RG8P2UzRBia.png"/>
</p>
⚠️ <b>OpenCore is still in beta. Please keep this in mind.</b><br><br><br>

**macOS Catalina**: 10.15.5 (19F101) Dual Boot w/ **Windows 10**: 2004 64Bit

**OpenCore version**: 0.5.9 <br>

## Specification
| **Component** | **Model** |
| ------------- | --------- |
| CPU | AMD Ryzen 7 2700X @ 3.7GHz |
| Motherboard | ASUS ROG Strix B450-F Gaming |
| GPU | AMD Radeon RX 500 Series |
| RAM | 32GB @ 2933MHz |

<br>
<b>Please note that sleep mode does not work yet. Therefore, deactivate the automatic switch to sleep mode in the macOS settings to prevent crashes.</b>
<br>
<br>

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
  3. After that, when you see the different macOS version, press R to get only the recovery version that are significantly smaller but still work.
  4. In the list that is now displayed, select macOS Catalina 10.15.5, which must be marked as "Full Install" and hit enter.
  5. Now open "MakeInstall.bat" as administrator, then enter the respective number for your USB stick, as well as the letter o not the number zero (for example "3o").
  6. Wait until it is finished and then enter the path to the macOS recovery file that you just downloaded.
  7. When this is complete, you will now see a USB device called "BOOT" replaced the "EFI" folder contained in it with the one that is contained in this repo.
  
  8. Download [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) and open "GenSMBIOS.bat". Then press 1 and then 2, enter the path to the config.plist that is saved on the "BOOT" USB stick under EFI > OC .
  9. After that press 3 and type in "iMacPro1,1". Then press enter, if you now see a random number combination in the window that follows, you have done everything correctly so far.
  10. Now open the config.plist with "[**ProperTree.bat**](https://github.com/corpnewt/ProperTree)", then enter the MAC address of your Ethernet port under Root > PlatformInfo > Generic > ROM .
  11. Now boot from the USB stick after deactivating secure boot, fast boot, and csm in the BIOS and unplugging all hard drives, apart from a single blank one on which you want to install macOS.
  12. After you have set up macOS, open [**Clover Configurator**](https://www.macupdate.com/app/mac/61090/clover-configurator) and mount the EFI partition with it. Then copy the EFI folder from the USB stick to the hard drive.
  
### Fixing Windows time
1. If your time in Windows is no longer displayed as intended, install the "Windows Universal Time - On.reg" file in Windows.
<p align="center">
	<img src="https://ibin.co/5RG7Fqz6WiHY.png"/>
</p><br><br><br>
