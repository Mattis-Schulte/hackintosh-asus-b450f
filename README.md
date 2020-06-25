![Screenshot](/cover.png?raw=true)

**macOS Catalina**: 10.15.5 (19F101) Dual Boot w/ **Windows 10**: 2004 64Bit

**OpenCore version**: 0.5.9  

## Specification
| **Component** | **Model** |
| ------------- | --------- |
| CPU | AMD Ryzen 7 2700X @ 3.7GHz |
| Motherboard | ASUS ROG Strix B450-F Gaming |
| GPU | AMD Radeon RX 500 Series |
| RAM | 32GB @ 2933MHz |

### Software needed
1. gibMacOS: https://github.com/corpnewt/gibMacOS
3. GenSMBIOS: https://github.com/corpnewt/GenSMBIOS 
6. ProperTree: https://github.com/corpnewt/ProperTree

### Recommended software
1. AMD Power Gadget: https://github.com/trulyspinach/SMCAMDProcessor/releases - To read and adjust CPU clock frequencies
2. Monitor Control: https://github.com/MonitorControl/MonitorControl/releases - For adjusting the brightness of an external monitor

## Installation
  1. Format a USB stick, preferably USB 3, with the NTFS file system.
  2. Then download [**gibMacOS**](https://github.com/corpnewt/gibMacOS) and open "gibMacOS.bat" as administrator. Install Python if necessary.
  3. After that, when you see the different MacOS version, press R to get only the recovery version that are significantly smaller but still work.
  4. In the list that is now displayed, select macOS Catalina 10.15.5, which must be marked as "Full Install" and hit enter.
  5. Now open "MakeInstall.bat" as administrator, then enter the respective number for your USB stick, as well as the letter o not the number zero (for example "3o").
