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
```
alias heimdall="/Users/tushar/Setups/heimdall-frontend.app/Contents/MacOS/heimdall"
alias adb="/Users/tushar/Setups/adb/adb"
```

# adb commands
```
./adb -d sideload lineage-22.1-20250111-nightly-gta4xlwifi-signed.zip
./adb -d sideload MindTheGapps-15.0.0-arm64-20240928_150548.zip
./adb push update.zip /storage/sdcard0/
./adb push update.zip /sdcard/0/
./adb reboot bootloader
```

# fastboot commands
```
./fastboot devices
./fastboot getvar version
./fastboot oem unlock 0xKEY
./fastboot oem get_unlock_data
./fastboot flash boot boot.img
./fastboot flash recovery twrp.img
./fastboot reboot

```

# heimdall commands
```
heimdall flash --RECOVERY recovery.img --no-reboot
```

# SMS File Location
`/data/user_de/0/com.android.providers.telephony/databases/mmssms.db`


# Delete Pattern Lock from Recovery
```
/data/system/gatekeeper.password.key
/data/system/gatekeeper.pattern.key
/data/system/locksettings.db
/data/system/locksettings.db-shm
/data/system/locksettings.db-wal
```
