# DELL_Latitude_5401_OpenCore0.8.9
Some configs OpenCore for Dell Latitude 5401 Coffee Lake

Dell Latitude 5401
BIOS version 1.24.0

![about and neofetch](https://github.com/SerjNIX/DELL_Latitude_5401_OpenCore0.8.9/blob/3885eaba86a837e6541833d907e6ec0ed71ddec1/Pictures/Latitude5401.png)

Tested on Big Sir, Monterey, Ventura
Using MacBookPro15,3 SMBIOS
The EFI was designed for Monterey

## My Specs:

- Model Make: Dell Latitude 5401

- CPU: Intel Core i7-9850H

- GPU: Intel UHD Graphics 630

- DRAM: 32GB (2x16GB) 2666MHZ DDR4

- Realtek ALC236 (Codec name in macos ALC236)

- Storage: PC SN730 NVMe WDC 512GB (nvme slot)

- Network adapters: Intel(R) Wireless-AC 9560 BT+Wifi, I219-LM Intel Ethernet

- 3x USB 3.1 and Thunderbolt 3 (usb type-C)


## What works:
- UHD 630 graphics full aceleration

- HDMI output 4Kx60Hz (whithout audio)

- Thunderbolt check only USB-C to USB-3 (DisplayPort check later when goes adapter)

- Audio keys - native, Brightness keys (Fn+s/Fn+b)

- Battery

- Keyboard, Touchpad full, Trackpoint full

- Wifi + Bluetooth

- Ethernet LAN

- WebCam (Internal)

- SDCard Reader

- Audio: Speakers and Microphone, ComboJack

- Power Management

- Sleep and Wake

## What not works:
- HDMI audio output

- Somthing else

## Bios Config:

Boot mode: UEFI

SATA Mode: AHCI

Fast Boot: Thorough

SecureBoot = Disable

Absolute(R) = Disabled

Intel SGX: Software Controlled

## Configs notes

- AirportItlwm.kext must be choice for platform (for BigSur works on BigSur and Ventura, but in Monterey brokes and reboot.)

- USBMap.kext for MBP15,3 (if need other SMBIOS require edit plist inside)

- if copy config you must find some files (eg. HFSPlus.efi), edit PlatformInfo, enable framebuffer-stolenmem if DVMT by default, etc

## WARNING! info for unlock CFG Lock and set DVMT. Be careful, it can makes laptop brick. Otherwise if brick, just clear bios CMOS:

```
CFG Lock = Disable
    (VarOffset/VarName): 0x6ED
    VarStore: 0x1
    
    Command for check value modGRUBShell.efi: setup_var_3 0x6ED

    Command for set value modGRUBShell.efi: setup_var_3 0x6ED 0x00 
=======================================================================

DVMT Pre-Allocated = 64MB
    (VarOffset/VarName): 0xA11
    VarStore: 0x1
    
    Command for check value modGRUBShell.efi: setup_var_3 0xA11

    Command for set value modGRUBShell.efi: setup_var_3 0xA11 0x02
=======================================================================

DVMT Total Gfx Mem = Max
    (VarOffset/VarName): 0xA12
    VarStore: 0x1
    
    Command for check value modGRUBShell.efi: setup_var_3 0xA12

    Command for set value modGRUBShell.efi: setup_var_3 0xA12 0x03
=======================================================================
```

![](https://github.com/SerjNIX/DELL_Latitude_5401_OpenCore0.8.9/blob/main/Pictures/GB5.png)
![](https://github.com/SerjNIX/DELL_Latitude_5401_OpenCore0.8.9/blob/main/Pictures/IPG.png)
![](https://github.com/SerjNIX/DELL_Latitude_5401_OpenCore0.8.9/blob/main/Pictures/MFC.png)
![](https://github.com/SerjNIX/DELL_Latitude_5401_OpenCore0.8.9/blob/main/Pictures/touchpad.png)
![](https://github.com/SerjNIX/DELL_Latitude_5401_OpenCore0.8.9/blob/main/Pictures/VMX.png)
![](https://github.com/SerjNIX/DELL_Latitude_5401_OpenCore0.8.9/blob/main/Pictures/videoproc2.png)
