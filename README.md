# Matebook_13/14_2020_Hackintosh_OpenCore
![Banner](https://github.com/Zero-zer0/Matebook_13_14_2020_Hackintosh_OpenCore/blob/master/Debug/banner.jpg)

English | [简体中文](https://github.com/Zero-zer0/Matebook_13_14_2020_Hackintosh_OpenCore/blob/master/README_CN.md)
## 
| Component | Details                                                                                                         |
|:--------------:|:------------------------------------------------------------------------------------------------------------------:|
|Model | Huawei Matebook 13/14 **2020**|
| CPU |    Intel Core i5 10210U / i7 10510U (Comet Lake) |
| GPU | Intel UHD620 </br> Nvidia MX250 / MX350 |
|RAM  |     8GB / 16GB LPDDR3|
| Wireless / BT  | Intel 9462AC / 9560AC CNVio2 <br>|
| Touchpad/Touchscreen|  ELAN962C </br> SYNA7813 (MB14) / ELAN224A (MB13)</br>  |
| Sound card |  ALC256 |
|SSD | SAMSUNG PM981 <br> WDC PC SN730 </br> Toshiba XG6 |
| LCD | 2160*1440|
|SMBIOS | MacBookPro 15,4|
| BIOS | 1.10 </br>(**some exist problem in v1.12**)|
--------
### ⚠️I DON"T own this laptop. 
### ⚠️The repo is created out of interest.
### ⚠️PR, Fork, issue are welcomed though I won't fix😝
### ⚠️BTW, FUCK ~~macx.top~~ for they steal the repos on GitHub and ask for pay on their own website. Shame!

- Note: **Huawei just squeeze some toothpaste to upgrade Matebook 13/14, this repo may not help you with the boot issue on other Comet Lake platform laptops.**

## What's working
- [x] Intel UHD 620
- [x] Brightness Control
- [x] Backlight shortcuts
- [x] USB
- [x] Internal speaker
- [x] Headphone output
- [x] Internal Mic
- [x] Touchpad
- [x] Intel Bluetooth
- [x] Hibernation
- [x] NVRAM
- [x] HDMI output
   - The HDMI port of `Matebook 14 2020` is HDMI 1.4, only support 4K30P or 4K50P in 4:2:0.
- [x] DP output (Recommended)
   - Use `ru.efi` or `H2OUVE` to unlock `DVMT Pre-allocated` to `64M` if you want 4K60P output.
</br>


## What's not working 
-  Nvidia MX250
-  Intel Wireless 9462/9560 AC CNVio2 (wait for [itlwmx](https://github.com/zxystd/itlwm))
-  SPI fingerprint sensor
-  Internal camera (AzureWave)
-  SAMSUNG PM981 NVMe SSD (unstale)
</br>

## Working with issues
- `kernel_task` may suddenly cause high CPU usage (thanks to AppleALC)
   - Try sleep/wake or restart your laptop.

- Touchscreen
   - Any issue related is welcomed. (~~Though I won't fix~~)

- Line in (Mic in) of headphone jack 
   - The `internal mic` and `line in` share the same node. In Windows, the switch is done by the driver. Need further research.

- Type-C to VGA will cause Kernel Panic (issue [#3](https://github.com/Zero-zer0/Matebook_13_14_2020_Hackintosh_OpenCore/issues/3))
   - May related to `LSPCON`
   - It's 2020 now, why not embrace digital output? </br> 

</br>


## TODOs after install
   1. Install `ComboJack` to improve the headphone sound quality. 
      - [Click HERE](https://github.com/Heporis/ComboJack) to download. Credit to [Heporis](https://github.com/Heporis).
      - Execute the script in the directory below
         
         > ComboJack_Installer/install.sh
   

   2. **Realtek USB NIC Driver by [chris111](https://github.com/chris1111)**：[Link](https://github.com/chris1111/Wireless-USB-Adapter/files/4301778/Wireless.USB.Adapter-V11.zip)  
      - You may still need a Realtek USB Wireless card so far. The drivers on Intel wireless card are ~~far from stable~~ and still have speed issues.

   3. `VoodooPS2Controller` may turn off the touchpad occasionally。Click `F11` if your touchpad is suddenly disabled.  

         
   4. HiDPI
      - See [one-key-hidpi](https://github.com/xzhih/one-key-hidpi)
      - **DO NOT** inject EDID.
      - Choose the icon you like.
      - Input custom 3:2 resolutions.</br>e.g. `1650*1100`, `1500x1000`, `1350x900`

</br>

## Download 
   Download from Release：

   - [![Release](https://img.shields.io/github/release/Zero-zer0/Matebook_13_14_2020_Hackintosh_OpenCore.svg)](https://github.com/Zero-zer0/Matebook_13_14_2020_Hackintosh_OpenCore/releases)
</br></br>



____________
 ## Credits
 - [Acidanthera](https://github.com/acidanthera) for OpenCore (and related documents) , Lilu, AppleALC and other awesome projects.
   - [AppleALC](https://github.com/acidanthera/AppleALC)
   - [CPUFriend](https://github.com/acidanthera/CPUFriend)
   - [HibernationFixup](https://github.com/acidanthera/HibernationFixup)
   - [NVMeFix](https://github.com/acidanthera/NVMeFix)
   - [Lilu](https://github.com/acidanthera/Lilu)
   - [OpenCore](https://github.com/acidanthera/OpenCorePkg)
   - [VoodooPS2]()
   - [VirtualSMC](https://github.com/acidanthera/VirtualSMC)
   - [WhateverGreen](https://github.com/acidanthera/WhateverGreen)
   
- [Alex James](https://github.com/al3xtjames) for
   - [NoTouchID](https://github.com/al3xtjames/NoTouchID)

- [chris111](https://github.com/chris1111) for maintaing supports on Realtek USB wireless card.  

- [Daliansky](https://github.com/daliansky) for instructions on AppleALC and ALCPlugFix.

- [laozhiang](https://github.com/laozhiang) for handy ACPI Hotpatch on Huawei Matebooks.

- [OC-little](https://github.com/daliansky/OC-little) for their handy ACPI Hotpatches for OpenCore.

- [RehabMan](https://github.com/RehabMan)
   - [OS-X-ACPI-Battery-Driver](https://github.com/RehabMan/OS-X-ACPI-Battery-Driver)
   - [OS-X-Fake-PCI-ID](https://github.com/RehabMan/OS-X-Fake-PCI-ID)
  - [OS-X-Null-Ethernet](https://github.com/RehabMan/OS-X-Null-Ethernet)
     

- [VoodooI2C Developer Team](https://github.com/VoodooI2C) for their magnificent work on I2C trackpads.  
   - [VoodooI2C](https://github.com/VoodooI2C/VoodooI2C)

- [zxystd](https://github.com/zxystd)  for awesome works on Intel wireless cards.  
   - [IntelBluetoothFirmware](https://github.com/zxystd/IntelBluetoothFirmware)

