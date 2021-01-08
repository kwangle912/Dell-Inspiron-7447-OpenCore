# Instroduce
Laptop Dell Inspiron 7447

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
* Sleep/Wake: working
* Restart/Shutdown
* Internal Speaker, Audio Digital Out, Headphone and Microphone
* Audio Realtek AC255 (layout-id = 20)
* WiFi
* Brightness + Fn up/down
* All USB Port
* Trackpad
* Keyboard Backlist

Not working
* Nvidia Card (Switchable Graphics is not supported by Hackintosh)
* Etc

# Installing
* Copy EFI directory for OpenCore
* OpenCore Install Guide for Laptop Haswell: https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/haswell.html#cleaning-up

# WiFi
Supported Devices :
```
- 3xxx: 3160 - 3165 - 3168
- 4xxx: 4165
- 7xxx: 7260 - 7265
- 8xxx: 8260 - 8265
- 9xxx: 9260 - 9461 - 9462 - 9560
```
* OpenCore" Copy Kext to /EFI/OC/KEXTS
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
* Download HeliPort here.
* Copy Heliprt To Applications & Reboot
* Run Heliport / check "Launch At Login
* Note : if you want to reset the assignment to en0, 
just delete /Library/Preferences/SystemConfiguration/NetworkInterfaces.plist and reboot.
