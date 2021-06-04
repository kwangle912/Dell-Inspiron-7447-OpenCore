# Instroduce

Hackintosh macOS Catalina 10.15.7

![my Hackintosh OSX157-19H2 2020-09-26](https://user-images.githubusercontent.com/46493927/120761770-bbd76880-c53f-11eb-9695-255fa82c020f.png)

Hackintosh macOS BigSur 11.4

![my Hackintosh OSX1101-20B29 OC_063R-2020-11-18](https://user-images.githubusercontent.com/46493927/120764103-107be300-c542-11eb-852a-d15fbfc4d900.png)
![my Setting-Big Sur 2020-11-18](https://user-images.githubusercontent.com/46493927/120763052-0d342780-c541-11eb-9b94-dc1b3f1557cf.png)
![my Hackintool check Display 2021-02-03](https://user-images.githubusercontent.com/46493927/120763400-5d12ee80-c541-11eb-9c84-a51f07ed11bc.png)
![my Hackintool check WiFi 2021-02-03](https://user-images.githubusercontent.com/46493927/120763497-7a47bd00-c541-11eb-859e-397c086dcf6b.png)
![my Hackintool check sound 2021-02-03](https://user-images.githubusercontent.com/46493927/120763627-9b101280-c541-11eb-8586-678106aac083.png)

## Laptop Dell Inspiron 7447

Detail Spesification
* Processor : Intel Core i5 4210H @2.9Ghz
* IGPU : Intel HD Graphics 4600
* GPU Discrette : Nvidia GTX 850M
* RAM : 8GB DDR3L PC12800/Bus 1600Mhz (4GB + 4GB)
* Storage : SSD Samsung 850 EVO 500 GB + HDD 500GB
* Audio Codec : Realtek ALC255
* Wifi : Intel Wireless Dual Brand AC 3160 + Bluetooth
* Ethernet : Realtek RTL8111 Gigabit Ethernet
* Touchpad : PS2 Interface (Synaptics)
* Screen Size : 14" HD
* Screen Resolution : 1366x768
* OS : Windows 10 Pro is activated
* Boot Mode : UEFI + GPT
* Bootloader: OC 0.6.x release and lastest
* OS version: macOS Catalina 10.15.x and lastest

# Working
* CPU Power Management
* Sleep/Wake
* Restart/Shutdown
* Internal Speaker, Audio Digital Out, Headphone and Microphone
* Audio Realtek AC255 (layout-id = 20)
* Intel WiFi AC-3160
* Disable dGPU (Card Nvidia GTX)
* Brightness + Fn up/down
* All USB Port
* Trackpad
* Keyboard Backlist

Not working
* Nvidia Card (Switchable Graphics is not supported by Hackintosh)
* Intel Bluetooth is not good 😢
* Etc

# Installing
* Download [OpenCore Release](https://github.com/acidanthera/OpenCorePkg/releases)
* Download [OpenCore Build-Repo](https://github.com/dortania/build-repo/releases)
* Copy EFI directory for [OpenCore](https://github.com/acidanthera/OpenCorePkg/releases)
* OpenCore Install Guide for Laptop Haswell: https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/haswell.html#cleaning-up

## Supported Intel WiFi Cards by itlwm
````
- 2000: `Supported`
- 3xxx: `AC 3160`, `AC 3165`, `AC 3168`
- 4xxx: `AC 4165`
- 7xxx: `AC 7260`, `AC 7265`
- 8xxx: `AC 8260`
- 9xxx：`AC 9260`,`AC 9461`, `AC 9462`, `AC 9560`
- 22000：`ax200`, `ax201`, `AC 9462`
````
- [Supported Devices](https://openintelwireless.github.io/itlwm/Compat.html)
- Link download [AirportItlwm.kext](https://github.com/kwangle912/AirportItlwm-for-Hackintosh)
* Disable SIP & install AirportItlwm into /Library/Extensions "With Hackintool" & rebuild kext cache then reboot (use AirportItlwm Catalina and install [Hackintool.app](https://github.com/headkaze/Hackintool/releases))


* OpenCore: Copy kext to /EFI/OC/KEXTS
* edit oc plist  "see methode for OpenCore Only" with PlistEdit Pro
```
 Add: BundlePath       string   itlwm.kext
      Comment          string  
      Enabled          Boolean  YES
      ExecutablePath   String   Contents/MacOS/itlwm
      MaxKernel        String
      MinKernel        String
      PlistPath        String   Contents/Info.plist
```
* Download [HeliPort.app](https://github.com/OpenIntelWireless/HeliPort/releases)
* Copy Heliprt To Applications & Open it and check "Launch At Login" ✅
* Note : if you want to reset the assignment to en0, 
just delete /Library/Preferences/SystemConfiguration/NetworkInterfaces.plist ❌ and reboot. Enjoy 🎉
