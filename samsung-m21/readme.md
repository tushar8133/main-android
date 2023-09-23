# Links
- Samsung Drivers - https://downloads.corsicanu.ro/samsung/
- Firmware Download - https://samfw.com/firmware/SM-M215F/INS
- Firmware Check Latest Version - https://doc.samsungmobile.com/SM-M215F/012739200617/wel.html
- TWRP XDA Thread - https://forum.xda-developers.com/t/recovery-unofficial-3-5-2-twrp-for-galaxy-m21.4212799/
- TWRP Download - https://github.com/soulr344/android_device_samsung_m21/releases
- TWRP BootLogoPatcher - https://github.com/corsicanu/TWRP_Bootlogo_patcher/releases
- TWRP BluetoothPatch - https://github.com/3arthur6/BluetoothLibraryPatcher/releases
- Magisk Download apk and zip (just rename) - https://github.com/topjohnwu/Magisk/releases
- Magisk Addon BypassBankingApps - https://github.com/kdrag0n/safetynet-fix/releases
- Magisk Addon Skvalex Call Recorder - https://github.com/Magisk-Modules-Repo/callrecorder-skvalex/releases
- LZ4 - https://github.com/lz4/lz4/releases

# Firmware Version
- M215FXXS3CWF1
- `M215F` - Model Numver
- `XX` XX is for International/European. Others could be United States, South Korea, China, etc
- `S3` Bootloader Version. Cannot be downgraded
- `C` A=first major Android OS update for device, B=second major OS update, C=third, etc...
- `W` P=2016, Q=2017, R=2018, S=2019, T=2020, U=2021, V=2022, W=2023, X=2024, Y=2025, Z=2026
- `F` A=Jan, B=Feb, C=Mar, D=Apr, E=May, F=Jun, G=Jul, H=Aug, I=Sep, J=Oct, K=Nov, L=Dec
- `1` How many times the firmware has build

# What is KG State ?
- __Prenormal__ Can't Flash Modify Rom / Can Flash Stock Rom
    - The phone was factory reset. Waiting for status check after connecting to the internet
- __Normal__ Can't Flash Modify Rom / Can Flash Stock Rom
    - No contract or not due payment
- __Blink__ Can't Flash Modify Rom / Can Flash Stock Rom
    - due to pay service fee (sending bill)
- __Locked__ Can't Flash Modify Rom / Can't Flash Stock Rom
    - overdue payment of service fees beyond the specified period
- __Completed__ Can Flash Modify Rom / Can Flash Stock Rom
    - Not attached to any contract
- __Broken__ Can Flash Modify Rom / Can Flash Stock Rom
    - Modified ROM status that may have usage problems such as the camera cannot be opened.
- __Checking__ Can Flash Modify Rom / Can Flash Stock Rom
    - Occurs when the Internet connection status is found. No contracts from Prenormal or caused by Knox blocking rom mods (beware of flashing).
- __No KG State__ Can Flash Modify Rom / Can Flash Stock Rom
    - Similar to Checking, but without connecting to the Internet, it deletes KG in various ways and installs ROMs, modifies or the server is being changed by the administrator.


# What is OEM (Bootloader) ?
- `OEM = On (L)` = OEM Settings Off / OEM Locked
- `OEM = On (U)` = OEM Settings On / OEM Locked
- `OEM = Off (L)` = OEM Settings Off / OEM Unlocked
- `OEM = Off (U)` = OEM Settings On / OEM Unlocked

# Unlocking the Bootloader

- Make sure OEM Unlock and USB debugging is ON in developer settings
- Turn off the phone
- Use vol down + vol up + USB cable plugged to a pc to start the phone in download mode
- Long press vol up, then confirm you want to unlock bootloader (this is needed one time only)
- ___Please be aware all your data will be erased including internal storage and phone will reboot!!___
- Let the phone boot normally, pass the setup and connect to internet and turn on developer options and make sure OEM Unlock is enabled and greyed out in order to unlock RMM ;)

# Reboot Guide

__THUMBRULE__:
- Keep USB plugged-in into your laptop
- __DOWNLOAD MODE__ usb + volup + voldown
- __RECOVERY MODE__ usb + power + volup
- __RESTART__ power + voldown 

From OneUI3, you need to keep your phone connected to a PC or a TV or another phone to be able to boot to recovery or download mode. If you have magisk installed, the easiest way would be to reboot using the Magisk app. If you're in Android 10 you can skip inserting a USB to reboot to Download mode and Recovery. Alternatively, you can use "adb reboot recovery" or "adb reboot download" from cmd or a terminal instead.

- Force Rebooting
    - Hold Volume Down and Power buttons
- Force Shutdown
    - Connect a charger (insert USB)
    - Hold Volume Down and Power buttons
    - Do not let go of the buttons till the charging animation appears
- Rebooting to Download Mode
    - When stuck in a bootloop or when booted
        - Keep USB connected
        - Hold Volume Down and Power buttons
        - When screen turns off, hold Volume Up and Volume Down buttons
    - When phone is turned off
        - Hold Volume Up and Volume Down buttons
        - Insert USB
- Rebooting to Recovery
    - When stuck in a bootloop or when booted
        - Keep USB connected
        - Hold Volume Down and Power buttons
        - When the screen turns off, hold Volume Up and Power buttons
    - When phone is turned off
        - Insert USB
        - Hold Volume Up and Power buttons

# Only Official Released Binaries Are Allowed To Be Flashed" Error

First Boot to download mode (boot to it using the button combo, rebooting to download mode with magisk or using the ADB command won't show all details)

Check the value of "kg state". If it is "checking" you are fine and something else is your issue.

__If it is "prenormal" do as follows:__

Boot your device normally, enable developer options and connect to your internet and check if OEM Unlock says "bootloader already unlocked"

Reboot to download mode, enjoy :D

__If that doesn't work,__

- Flash Stock Rom
- Set it up normally
- Connect to the internet
- Enable Developer Options
- Wait for OEM Unlock to appear greyed out in developer options
- Maybe enable USB Debugging too (dunno if this helps)
- Once it appears, boot to download mode and check kg state
- Try flashing whatever you were trying to before, it should work if it is checking

If it's still showing prenormal, maybe wait a little more before trying all this again


# GSI Naming

Some information you should know about what type of gsi you need

- `<ARCH>_xyZ`
- `<ARCH>` can either be arm(32bit), a64(32bit for 64bit CPUs) or arm64(64bit)

###
- `x` can either be `a` or `b`
- `y` can either be `v`, `o`, `g` or `f`
- `z` can be `n` or `s`

###
- `b` = `a`/`b`
- `a` = `a` only

###
- `g` = gapps
- `o` = gapps-go
- `v` = vanilla (no gapps included)
- `f` = floss (free & open source apps instead gapps)

###
- `N` = no superuser
- `S` = superuser included

> M21 and M31 needs `ARM64` `AB` ( When downloading, `B` usually means `AB` )  

###
Generally you'll want to get `ARM64bgn`:
- ARM64 - 64bit
- `b` - AB
- `g` - GApps
- `n` - No SuperSU


# Flasing GSI
- Prerequisites
    - The GSI image
    - Optional
        - Magisk, Magisk fix for A11,
        - Multi Disabler
        - DM Verity Disabler
- NOTES
    - Download the GSI image you need, refer GSI Naming and download links in #gsi
    - Generally you'll want "arm64bgn"
    - If this is a .xz file, extract it to get the .img file
    - Format/wipe data, and wipe cache and dalvik-cache before changing Roms/GSIs
    - Now if you haven't disabled encryption and dm-verity, it's a good idea to do it now, refer #multi_disabler and #dmverity_disabler
    - If you cannot root with Magisk in Android 11, you'll need to flash #magisk_fix_a11_gsi before flashing Magisk
- USING RECOVERY
    - If you are on android 11 or above, flash the latest TWRP or any other recovery, and flash the gsi.img directly to system.
    - For OrangeFox recovery, PBRP or for Android 10 recovery, flash /dynapatch and reboot to recovery, then you'll be able to flash the img directly to system.
    - You can also try using the TWRP Terminal: _(This will only work with Soulr344's TWRP build 3.5.0 v1.1 and above)_
        - Download the GSI image
        - Put it in internal storage (in root, not inside any folder)
        - Reboot to TWRP, go into TWRP's terminal
        - Enter "super flash system /sdcard/<name>.img"
        - ("/sdcard" is the internal storage, don't get confused)
        - Check the troubleshooting section
- USING GSI FLASHER
    - Download #gsi_flasher
    - Extract the zip file
    - Put the GSI (.img) in the gsi folder
    - Repack the folders (gsi, META-INF, and scripts) into a zip
    - Flash the zip file in TWRP
    - Check the video for steps
    - check the troubleshooting section
- TROUBLESHOOTING
    - For flashing through TWRP terminal
        - Use "/external_sd" instead of "/sdcard" in the TWRP terminal to flash from external sdcard in case your internal is encrypted, or you just want to use your sdcard
        - Make sure that you have enough space in /sdcard (internal storage)
    - General Stuff
        - If the phone is bootlooping,
            - Reflash the gsi
            - Format/Wipe data
            - Flash #multi_disabler (don't flash if you wiped instead of formating data)
            - Flash a different kernel (optional, might help)
            - Flash Magisk; if you don't want to root, flash #dmverity_disabler
        - Some GSIs are permissive, so you might have to flash permissiver and a kernel that supports it.
    - Flashing GAPPS
        - If you try to flash gapps after flashing the GSI, and it gives you an error saying there isn't enough space, flash #system_resizer from recovery and try again.
    - Not all GSIs will work


# Flashing Magisk
- Prerequisites:
    - Unlock Your Bootloader First
    - Magisk
- From Recovery
    - Flash a custom recovery if you don't have one (guide below)
    - Flash the Magisk zip/apk from recovery
- From ODIN / Patching Manually
    - You could patch the boot image from magisk manually and then flash the boot image from ODIN or recovery, but... why...?
    - If you still want to do that, Extract AP***.tar.md5 from stock rom (ideally the one you're on right now)
    - Extract boot.img.lz4 from AP***.tar.md5
    - Extract the boot.img.lz4 archive [lz4 for windows](https://github.com/lz4/lz4/releases)
    - You can skip the above and download the latest boot image from #stock_files, or if you know how to dump boot image using something like termux you can do that.
    - Install the magisk app
    - Press install and patch the boot image
    - Flash it to boot using recovery
    - OR, rename it to boot.img and compress it to a tar archive, boot to Download Mode and flash it to AP with Odin
    - If your phone bootloops, flash #null_vbmeta to AP with Odin _(Not always necessary, but if you flash it, you might have to wipe data, or you'll face weird bugs)_

# Flasing Recovery
- Prerequisites:
    - Unlock Your Bootloader First
    - Recovery Image Compressed to .tar, or Flashable Zip (#recovery)
    - Multi Disabler, DM-Verity Disabler (or Magisk)
    - ODIN or a Recovery
    - (check notes for files)
- Flashing From ODIN
    - You'll be needing a tar archive with the recovery image in it _(The recovery image should be named recovery.img inside the tar archive)_
    - Reboot to Download Mode and connect USB
    - Open ODIN and untick everything in the options tab
    - Select the tar file in AP
    - Press Start
    - Wait for the flashing to complete
    - Common instructions below [READ THEM]
- Flashing From Recovery
    - Just flash the .img file to recovery or flash the zip file
    - Common instructions below
- Common Instructions for flashing recovery
    - You obviously don't need to do these if you're already using another recovery and have done this before
    - After flashing the recovery, keep the USB connected, DO NOT boot to system
    - Keep USB connected, hold volume down and power, when screen turns off, quickly switch to volume up and power, you should boot to recovery
    - Format Data (not wipe, format) and reboot to recovery, not system, if you boot into system, format it again _(you can skip the format and multi disabler if you want to keep your internal encrypted, but then the recovery would be almost useless)_
    - Copy the necessary files to flash from your PC to internal storage or sdcard
    - Flash Multi Disabler
    - Flash DM-Verity Disabler (or Magisk if you are planning to root)
    - Flash [TWRP Bootlogo Patcher](https://github.com/corsicanu/TWRP_Bootlogo_patcher/releases) to hide the annoying warning at boot
    - Reboot


# Flashing Stock ROM
- Requirements
    - PC
    - Odin
    - Stock Firmware
    - Samsung USB Drivers
    - Backup All Important Data
    - A Working Brain and Courage
    - Download paitience from YouTube
- Steps:
    - Download the Rom
    - Install Odin and Samsung Drivers and reboot your PC
    - Turn off the phone
    - Press volume up + volume down and insert USB cable again to enter download mode
    - If you're stuck in a bootloop refer to the reboot guide in #guides
    - Open Odin
    - You will see that phone is detected by Odin
    - Untick all boxes in options [for safety]
    - Extract firmware and u will get 5 files
    - Just select the tab
        - AP = AP.tar.md5
        - BL = BL.tar.md5
        - CP = CP.tar.md5
        - CSC = CSC.tar.md5
    - If you want to save data
        - CSC = HOME_CSC.tar.md5
    - Click on flash to start flashing
    - If it says pass, then it worked
    - Press and hold power + volume down to reboot



# Multi disabler for m31 and m21
- It disables these services
    - FBE (File Based Encryption)
    - Vaultkeeper
    - Process authentication
    - Stock recovery auto-restoration
    - wsm
    - extra services
- How to flash __Multi disabler for m31 and m21__
    - Flash twrp.
    - Then format data.
    - Flash multi_disabler.
    - Reboot ur device.
    - Enter twrp again.
    - Then format data again.
    - Remove /data/knox folder.
    - Reboot ur device.
    - Ur device has been unlocked completely.


# Firmware Extraction
- Download firmware
- Extract firmware zip file
- You will get 5 types of files
    - `AP_XXXXX.tar.md5`
    - `BL_XXXXX.tar.md5`
    - `CP_XXXXX.tar.md5`
    - `CSC_XXXXX.tar.md5`
    - `CSC_HOME_XXXXX.tar.md5`
- You can remove `.md5` extension without any worry and it also saves time when you select these files in odin
- Extract `AP` file, ignore warning: There are some data after the end of the payload data.
- After 100% extract you can close 7zip window
- You will get some .lz4 files
- Use `lz4_win64_v1_9_3.zip` to convert them to normal `.img` file
- Just drag `.lz4` file over `lz4.exe` to convert them
- Now you can get `super.img` with this method
- To open `super.img` _right click on it_ > `7-Zip` > `Open archive as #`
- You will get
    - `x.ext / (system)`
    - `x.ext vendor`
    - `x.ext product`
    - `x.ext odm`
- Drag these files on desktop
- These are the RAW .ext image files, these represents the real partitions with actual data, filled with zeros at the end.
- You can rename them from .ext to .img and use them to flash through twrp
-Because these partitions are huge in size, so android has came up with sparse image format (simg)
- Example of sparse image format is "super.img" which combines different RAW ext partitions, but compresses them by removing the ending zeros
- They provide the tools to convert these images
    - `simg2img`
    - `img2simg`
- I don't know if these original `.exe` files are provided by android, but i got hands on to some, from other publishers:
    - `simg2img.zip` (people are complaining. when i tested, the output file size was differ from 7zip method, so dont use it)
    - `simg2img_win.zip` (works exactly like the procedure done with 7zip# process. the sizes of the images matches exactly with 7zip# process, so 7zip works perfectly as this software)
 
# Using ODIN
- Download Samsung Usb Mobile Drivers
- Download Odin 3.14.4
- When using odin goto `Options` and uncheck `Auto Reboot` checkbox
    - BL
    - AP
    - CP
    - CSC (use CSC or use CSC_HOME file to prevent data partition loss)
    - USERDATA (leave empty)

# Terminologies
- __VBMETA__ - 
- __DM-VERIFY__ - something related to kernel, which also detects modified things
- __boot__ - RAMDISK, KERNEL, MAGISK
- __dtbo__ - 
- __odm__ - 
- __omr__ - 
- __optics__ - 
- __prism__ - 
- __product__ - 
- __recovery__ - stock/twrp
- __super__ - containes system, vendor, product, odm
- __system__ - GSI is system partition
- __userdata__ - DATA partition
- __vbmeta__ - detects any modified package used for flashing
- __vbmeta_samsung__ - 
- __vendor__ - manufacturer related important stuff like, wifi/bluetooth/camera drivers
