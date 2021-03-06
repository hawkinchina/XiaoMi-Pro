# XiaoMi NoteBook Pro for macOS Mojave & High Sierra & Sierra

Hackintosh your XiaoMi Pro Notebook

[English](README.md) | [中文](README-CN.md)

## Features

* Support 10.13.x and 10.14
* CPU native support
* The sound card is ALC298, fake with AppleALC, layout-id: 99; and injection information is located at `/CLOVER/config.plist`
* Touchpad driver using `VoodooI2C`, support for multiple gestures; touchpad boot can be used normally, no drift, no wakeup
* Other ACPI patch fixes using hotpatch mode, file located in `/CLOVER/ACPI/patched`
* USB shadowing using `/CLOVER/ACPI/patched/SSDT-USB.aml`
* Native Brightness hotkey support, related file is located at `/CLOVER/ACPI/patched/SSDT-LGPA.aml`
* Native Bluetooth is not working well. If you want to disable it to save power or to use BT dongle, please read instructions here: https://github.com/daliansky/XiaoMi-Pro/issues/24 .


## Credits

- [RehabMan](https://github.com/RehabMan) Updated [OS-X-Clover-Laptop-Config](https://github.com/RehabMan/OS-X-Clover-Laptop-Config) and [OS-X-USB-Inject-All](https://github.com/RehabMan/OS-X-USB-Inject-All) and [OS-X-FakeSMC-kozlek](https://github.com/RehabMan/OS-X-FakeSMC-kozlek) and [OS-X-ACPI-Battery-Driver](https://github.com/RehabMan/OS-X-ACPI-Battery-Driver) and [OS-X-Null-Ethernet](https://github.com/RehabMan/OS-X-Null-Ethernet) and [OS-X-Voodoo-PS2-Controller](https://github.com/RehabMan/OS-X-Voodoo-PS2-Controller) for maintenance

- [vit9696](https://github.com/vit9696) Updated [Lilu](https://github.com/acidanthera/Lilu) and [AppleALC](https://github.com/acidanthera/AppleALC) and [WhateverGreen](https://github.com/acidanthera/WhateverGreen) for maintenance

- [BarbaraPalvin](https://github.com/BarbaraPalvin) Updated [IntelGraphicsDVMTFixup](https://github.com/BarbaraPalvin/IntelGraphicsDVMTFixup) for maintenance

- [Pike R. Alpha](https://github.com/Piker-Alpha) Updated [ssdtPRGen.sh](https://github.com/Piker-Alpha/ssdtPRGen.sh) and [AppleIntelInfo](https://github.com/Piker-Alpha/AppleIntelInfo) for maintenance

- [PMheart](https://github.com/PMheart) Updated [CPUFriend](https://github.com/PMheart/CPUFriend) for maintenance

- [alexandred](https://github.com/alexandred) Updated [VoodooI2C](https://github.com/alexandred/VoodooI2C) for maintenance

- [PavelLJ](https://github.com/PavelLJ) for valuable suggestions

- [Javmain](https://github.com/javmain) for valuable suggestions


## Installation

Please refer to the detailed installation tutorial (Chinese version) [macOS安装教程兼小米Pro安装过程记录](https://blog.daliansky.net/MacOS-installation-tutorial-XiaoMi-Pro-installation-process-records.html).

A complete EFI archive is available [releases](https://github.com/stevezhengshiqi/XiaoMi-Pro/releases) page,Thanks to the continuous update of [stevezhengshiqi](https://github.com/stevezhengshiqi/XiaoMi-Pro).

### Mojave Installation

1. Use direction key to choose `Options` icon at Clover screen

2. Press `Space` key to select `Configs` - `config_install`

3. Press `Space` key to choose `Return` and boot your Mojave partition

4. The installer may restart several times, please repeat step 2 and step 3 after every restart

5. You may now successfully boot into the system. Open `Terminal.app` and type `sudo kextcache -i /`

6. Wait until the process ends and restart. Enjoy your Mojave!



## Change Log:

- 10-14-2017
   - EFI update, touch pad is working
- 10-17-2017
   - EFI update, fixed graphics driver
   - Add HDMI Audio output
   - Driver Update:
     - Lilu v1.2.0
     - AppleALC v1.2.1
     - IntelGraphicsDVMTFixup v1.2.0
     - AirportBrcmFixup v1.1.0
   - Driver repair:
     - IntelGraphicsFixup v1.2.0
- 10-18-2017
   - tested graphics driver is not as good as the first version, now the graphics driver is restored to fake 0x19160000
   - ACPI repair
       Driver fixes
   - Remove USBInjectAll with SSDT-UIAL.aml built-in USB device
- 10-19-2017
   - Graphics driver is normal
   - The touchpad turns on normally, multi-gestures are normal after waking up
   - normal sleep
   - Battery information is normal
- 10-31-2017
   - Update sound card driver, fix earphone problem
   - New driver to increase layoutid: 13
   - Supports four nodes to support the headset to switch freely, Mic / LineIn is working properly
- 11-2-2017
   - Lilu v1.2.0 update, support 10.13.2Beta
   - AppleALC update, using the latest revision of Lilu co-compiler to solve 10.13.1 update can not be driven after the problem
- 11-5-2017
   - Integrate AppleALC_ALC298_id13_id28.kext driver to EFI
   - Add EFL directory ALCPlugFix directory, please enter the ALCPlugFix directory after the installation is complete, double-click the install double-click to automatically install. Command Install the headset plug-in state correction daemon
   - Fixed Drivers64UEFI to solve the problem that can not be installed
   - Updated apfs.efi to version 10.13.1
- 11-7-2017
   - Lilu v1.2.1 is not stable at the moment, with the risk of inability to enter the system, so downgrade to v1.2.0
   - AppleALC downgraded to V1.2.0
       **EFI temporarily does not support macOS 10.13.2Beta version of the installation, Lilu does not exhaust will continue to update**
- 1-25-2018
   - Support for 10.13.x installation
   - Updated VoodooI2C to version 2.0.1, supports multi-gestures, touchpad boot can be used normally, no drift, no wakeup
   - Fixed the issue of percentage refreshes
   - Fix sound card sleep wake up soundless problem
   - Fixed screen brightness can not be saved problem
   - Updated Lilu v1.2.2
   - Updated AppleALC v1.2.2 support millet pro, injection ID: 99
   - Update IntelGraphicsFixup v1.2.3   
- 4-8-2018
   - Support for 10.13.4 installation
   - Updated ACPIBatteryManager v1.81.4
   - Updated AppleALC v1.2.6
   - Updated FakeSMC v6.26-344-g1cf53906.1787
   - Updated IntelGraphicsDVMTFixup v1.2.1
   - Updated IntelGraphicsFixup v1.2.7, no need kexts for faking Intel Graphics' ID
   - Updated Lilu v1.2.3
   - Updated Shiki v2.2.6
   - Updated USBInjectAll v0.6.4
   - Add AppleBacklightInjector to widen the range of brightness
   - Add CPUFriend and CPUFriendDataProvider to enable native XCPM and HWP
   - Add boot parameters "shikigva=1", "igfxrst=1" and "igfxfw=1" to make the Graphics card more powerful and fix strange secondary boot interface.
   - Add SSDT-LGPA.aml, support native brightness hotkey
- 4-12-2018
   - Update AppleALC v1.2.7
   - Update SSDT-IMEL.aml, SSDT-PTSWAK.aml, SSDT-SATA.aml, SSDT-XOSI.aml from Rehabman's Github
   - Edit SSDT-LPC.aml to load native AppleLPC
   - Update Clover r4438


- 5-14-2018
   - Rename some SSDTs to fit with Rehabman's sample:https://github.com/RehabMan/OS-X-Clover-Laptop-Config. Also update SSDT-GPRW.aml, SSDT-DDGPU.aml, SSDT-RMCF.aml and SSDT-XHC.aml
   - Delete some useless renames in config
   - Redo the USB Injection, now it supports type-c USB3.0
   - Delete SSDT-ADBG.aml since it's useless
   - Delete SSDT-IMEI.aml to avoid kernel error report(Graphics id is automatically injected by IntelGraphicsFixup)
   - Add SSDT-EC.aml and SSDT-SMBUS.aml to launch AppleBusPowerController and AppleSMBusPCI
   - Edit SSDT-PCIList.aml to let System Information.app show correct information
   - Update Lilu v1.2.4
   - Update CPUFriendDataProvider to save power
   - Update Clover r4458

- 7-27-2018
   - Update Clover r4625
   - Update AppleALC v1.3.1
   - Update Lilu v1.2.6
   - Update CPUFriendDataProvider by using MBP15,2's PM template
   - Update VoodooI2C v2.0.3
   - Update CodecCommander v2.6.3
   - Use WhateverGreen to replace IntelGraphicsFixup and Shiki
   - Use VoodooPS2Controller to replace ApplePS2SmartTouchPad
   - Add minStolen Clover patch
   - Add support for Mojave (the installation instruction is at above)

## A reward

| Wechat                                                     | Alipay                                               |
| ---------------------------------------------------------- | ---------------------------------------------------- |
| ![wechatpay_160](http://7.daliansky.net/wechatpay_160.jpg) | ![alipay_160](http://7.daliansky.net/alipay_160.jpg) |

## Support and discussion

- QQ群:
  - 247451054 [小米PRO黑苹果高级群](http://shang.qq.com/wpa/qunwpa?idkey=6223ea12a7f7efe58d5972d241000dd59cbd0260db2fdede52836ca220f7f20e)
  - 137188006 [小米PRO黑苹果](http://shang.qq.com/wpa/qunwpa?idkey=c17e190b9466a73cf12e8caec36e87124fce9e231a895353ee817e9921fdd74e)
  - 331686786 [一起吃苹果](http://shang.qq.com/wpa/qunwpa?idkey=db511a29e856f37cbb871108ffa77a6e79dde47e491b8f2c8d8fe4d3c310de91)
  - 688324116 [一起黑苹果](https://shang.qq.com/wpa/qunwpa?idkey=6bf69a6f4b983dce94ab42e439f02195dfd19a1601522c10ad41f4df97e0da82)
  - 257995340 [一起啃苹果](http://shang.qq.com/wpa/qunwpa?idkey=8a63c51acb2bb80184d788b9f419ffcc33aa1ed2080132c82173a3d881625be8)



