<img src="https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/Logos/OpenCore_with_text_Small.png" width="200" height="48"/>

**macOS Big Sur**: 11.4 (20F71)  Triple Boot w/ **Windows 10**: 21H1 and **Ubuntu**: 20.04.1 LTS (Focal Fossa)

**OpenCore version**: 0.7.0 <br>

## My System
| **Component** | **Model** |
| ------------- | --------- |
| CPU | AMD Ryzen 7 2700X @ 3.7GHz |
| Motherboard | ASUS ROG Strix B450-F Gaming - BIOS Version 4007 |
| GPU | AMD Radeon RX 580 |
| RAM | 32GB @ 3000MHz |

### Recommended software
1. AMD Power Gadget: https://github.com/trulyspinach/SMCAMDProcessor/releases - To read and adjust CPU clock frequencies
2. Monitor Control: https://github.com/MonitorControl/MonitorControl/releases - For adjusting the brightness of an external monitor

> If you are using a Navi-based graphics card, you have to open EFI/OC/config.plist with [**ProperTree**](https://github.com/corpnewt/ProperTree). Then add `agdpmod=pikera` to your boot-arguments (NVRAM > Add > 7C436110-AB2A-4BBB-A880-FE41995C9F82 > boot-args)

## Installation
  1. Create a USB installer using [**this guide**](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/)
  2. Clone the repository and copy the "BOOT" and "OC" directories into your USB installers "EFI" folder
  3. Download [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) to generate your unique SMBIOS. Run it and select Generate SMBIOS, select iMacPro1,1 as the model
  4. Now open EFI/OC/config.plist with [**ProperTree**](https://github.com/corpnewt/ProperTree) and go to PlatformInfo > Generic. Set MLB (Board Serial), SystemSerialNumber (Serial) and SystemUUID (SmUUID) to the generated values. Change the ROM to the MAC address of your system without colons. You can now boot from the USB installer
  5. After you have set up macOS, download and open [**Clover Configurator**](https://www.macupdate.com/app/mac/61090/clover-configurator/download) and mount the EFI partition with it. Then copy the EFI folder from the USB stick to the hard drive

> Make sure Secure Boot is set to `Other OS` and CSM is disabled if you're having issues booting the macOS installer

## Please also note that the sleep mode may not work if:
1. USB 2.0 device plugged into the motherboard's USB 3.x I/O ports<br>
2. USB 3.x device plugged into the motherboard's USB 2.0 I/O ports<br>
3. USB 2.0 device connected to a USB 3.x hub and plugged into the motherboard's USB 3.x I/O port, sleep only works when the hub is plugged into a USB 2.0 I/O port<br>

## Fixing Windows clock
1. If your clock in Windows does no longer work as intended, open the "Windows Universal Time.reg" file in Windows as administrator
