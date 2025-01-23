# [Goto - Samsung M21](samsung-m21/readme.md)


# Downloads
- [ADB Official Page](https://developer.android.com/tools/releases/platform-tools)
- [ADB Tools for Windows](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)
- [ADB tools for MacOS](https://dl.google.com/android/repository/platform-tools-latest-darwin.zip)
- [Heimdall (Odin for Macos)](https://github.com/fathonix/heimdall-osx-arm64/releases/download/heimdall-2.0.2/heimdall-2.0.2-macos-arm64.tar.xz)
- [Samsung Drivers](https://downloads.corsicanu.ro/samsung/)
- [Samsung Firmware Download](https://samfw.com/firmware/SM-M215F/INS)
- [Samsung Firmware Check Latest Version](https://doc.samsungmobile.com/SM-M215F/012739200617/wel.html)
- [M21 TWRP XDA Thread](https://forum.xda-developers.com/t/recovery-unofficial-3-5-2-twrp-for-galaxy-m21.4212799/)
- [M21 TWRP Download](https://github.com/soulr344/android_device_samsung_m21/releases)
- [TWRP BootLogoPatcher](https://github.com/corsicanu/TWRP_Bootlogo_patcher/releases)
- [TWRP BluetoothPatch](https://github.com/3arthur6/BluetoothLibraryPatcher/releases)
- [Magisk Download apk and zip (just rename)](https://github.com/topjohnwu/Magisk/releases)
- [Magisk Addon BypassBankingApps](https://github.com/kdrag0n/safetynet-fix/releases)
- [Magisk Addon Skvalex Call Recorder](https://github.com/Magisk-Modules-Repo/callrecorder-skvalex/releases)
- [LZ4](https://github.com/lz4/lz4/releases)


# `.zprofile`
```sh
alias heimdall="/Users/tushar/Setups/heimdall-frontend.app/Contents/MacOS/heimdall"
alias adb="/Users/tushar/Setups/adb/adb"
```

# adb commands
- `adb help` Shows ADB Help Documentation.
- `adb devices` Lists all the Android Devices connected via ADB.
- `adb reboot` Reboots your Android Device.
- `adb reboot bootloader` Reboots your Android Device into Fastboot/Bootloader Mode.
- `adb reboot recovery` Reboots your Android device into Recovery Mode.
- `adb install` Helps you install an APK File on your Android Device.
- `adb install filename.apk` Install the APK File.
- `adb install -r filename.apk` Re-installs or updates an App.
- `adb install -s filename.apk` Installs the APK File in SD Card (if the App supports).
- `adb uninstall` Helps you install an App File on your Android Device.
- `adb uninstall com.facebook.katana` Simply uninstalls the App.
- `adb uninstall -k com.facebook.katana` Keeps the Data and Cache Folder after the App is uninstalled.
- `adb logcat` Displays the Log Data onto the Screen.
- `adb bugreport` Displays the Dumpsys, Dumpstate and Logcat Data on the Screen.
- `adb jdwp` Lists the JDWP (Java Debug Wire Protocol) Processes on the Device.
- `adb get-serialno` Shows the adb instance Serial Number String with the Device.
- `adb get-state` Displays the Device Status.
- `adb wait-for-device` Used to set a Delay before the next Command is issued. It executes when the Device is online but it can be programmed to wait till another Process is done.
- `adb start-server` Starts the ADB Server Process.
- `adb kill-server` Stops the ADB Server Process.
- `adb sideload <filename.zip>` Used to flash a Zip File in Recovery Mode when the Zip File is available in the Computer.
- `adb -d sideload lineage-22.1-20250111-nightly-gta4xlwifi-signed.zip`
- `adb -d sideload MindTheGapps-15.0.0-arm64-20240928_150548.zip`
- `adb pull </path/filename` Pulls any File from your Device and saves it on your Computer.
- `adb push <source-path> <target-path` Used to push a File into your Android Device.
- `adb push update.zip /storage/sdcard0/`
- `adb push update.zip /sdcard/0/`

# fastboot commands
- `fastboot boot filename.img` Instead of flashing the File, this Command simply boots it (if the File is bootable).
- `fastboot devices` List all the Android Devices that are connected in Fastboot Mode to your Computer.
- `fastboot flash` Used to flash Files on your Android Device.
- `fastboot flash boot boot.img` Flashes boot Image on your Android Device's Boot Partition.
- `fastboot flash recovery twrp.img` Flashes Recovery Image on your Android Device's Recovery Partition.
- `fastboot getvar version`
- `fastboot oem get_unlock_data`
- `fastboot oem lock` Relocks the Bootloader on your Android Device.
- `fastboot oem unlock` Unlocks the Bootloader on your Android Device (if the OEM allows).
- `fastboot reboot bootloader` Reboots your Device into Fastboot/Bootloader Mode.
- `fastboot reboot`

# adb shell
- `adb shell` Starts the Remote Shell Command Console in the Device.
- `adb shell pm uninstall -k –user 0 package.name.com` Helps you uninstall a System App from your Android Device. Replace package.name.com with the actual Package Name.
- `adb shell dumpsys` Dumps all System Data about your Android Device's Dardware and Software Configuration
- `adb shell dumpsys display` Displays all the Hardware and Software Configuration about your Display.
- `adb shell dumpsys battery` Displays all the Hardware and Software Configuration about your Battery.
- `adb shell dumpsys batterystats` Displays all the Info about your Battery Statistics.
- `adb shell wm density` Helps you change the Pixel Density on your Android Device.
- `adb shell pm list packages` Lists all the Apps installed on your Device as Package Names.
- `adb shell pm list packages -s` Lists all the System Apps installed on your Device as Package Names.
- `adb shell pm list packages -3` Lists all the 3rd Party Apps installed on your Device as Package Names.
- `adb shell pm list packages -d` Lists all the disabled Apps on your Device as Package Names.
- `adb shell pm list packages -e` Lists all the enabled Apps on your Device as Package Names.
- `adb shell pm list packages -u` Lists all the uninstalled Apps with installed Pages on your Device as Package Names.
- `adb shell screencap /sdcard/screenshot.png` Takes a Screenshot of your Device Screen and saves it in SDCARD with the name "screenshot.png".
- `adb shell screenrecord /sdcard/screenrecord.mp4` Starts recording your Device Screen and saves the Video in SDCARD with the name "screenrecord.mp4". The default Record Time is 180 Seconds (Maximum). You can press CTRL + C to stop the recording any Time.
- `adb shell screenrecord –size 1920×1080 /sdcard/screenrecord.mp4` Screen recording with custom Width and Height for the Video.
- `adb shell screenrecord –time-limit 120 /sdcard/screenrecord.mp4` Screen recording with custom Time Limit for the Video. Max value is 180 Seconds.
- `adb shell screenrecord –bit-rate 4000000 /sdcard/screenrecord.mp4` Screen Recording with custom Bit Rate for the Video. The Value "4000000" sets the Bitrate to 4Mbmps.


# adb shell (enter)
> type `adb shell` then, hit Enter and then execute any of the following commands:
- `cd /system` Changes the Directory to "/system".
- `rm -f /sdcard/<filename.zip>` Deletes a File from your Android Device.
- `crm -d /sdcard/example` Deletes a Folder from your Android Device.
- `mkdir /sdcard/Android` Creates a new Folder named "Android" under "/sdcard"
- `cp /sdcard/filename.apk /sdcard/FolderName/` To copy a File.
- `mv /sdcard/filename.apk /sdcard/FolderName/` To move a File.
- `mv /sdcard/filename.apk /sdcard/anotherfilename.apk` To rename a File.
- `netstat` To check the Network Statistics of your Android Device.
- `ip -f inet addr show wlan0` Displays your Phone's Wi-Fi IP Address.
- `top` Displays top CPU Processes running on your Android Device.
- `getprop ro.build.version.sdk` Used to get the Properties of your Android's build.prop Configuration.
- `setprop net.dns1 1.2.3.4` Used to set Values to the Properties present in your Android's build.prop Configuration.


# heimdall commands
```sh
heimdall flash --RECOVERY recovery.img --no-reboot
```

# SMS File Location
```sh
/data/user_de/0/com.android.providers.telephony/databases/mmssms.db`
```


# Delete Pattern Lock from Recovery
```sh
/data/system/gatekeeper.password.key
/data/system/gatekeeper.pattern.key
/data/system/locksettings.db
/data/system/locksettings.db-shm
/data/system/locksettings.db-wal
```
