# Samsung A7-T505 (gta4l) or S6-lite (gta4xlwifi)

- For `adb` and `fastboot`, download [platform tools](https://developer.android.com/tools/releases/platform-tools) extract and setup below path in zprofile
    ```sh
    alias adb="/Users/tushar/Setups/adb/adb"
    ```
- You can find most of the instructions of how to flash using `heimdall` on macos, here on [lineageos website](https://wiki.lineageos.org/devices/gta4xlwifi/install).
- You will also need to require `heimdall`. There are few different places from where you can get it. I have used the first option.
    1. Get `app` from [github](https://github.com/fathonix/heimdall-osx-arm64/releases/download/heimdall-2.0.2/heimdall-2.0.2-macos-arm64.tar.xz).
        - Either copy binary from
            ```sh
            heimdall-frontend.app/Contents/MacOS/heimdall
            ```
        - Or set below path in zprofile
            ```sh
            alias heimdall="/Users/tushar/Setups/heimdall-frontend.app/Contents/MacOS/heimdall"
            ```
    2. Get `binary` from lineage [website](https://blob.lineageos.org/downloads/heimdall/Heimdall-macOS-v2.2.2-120625.dmg).
        - Either open dmg and drag binary to below path
            ```sh
            usr/local/bin
            ```
        - Or just copy the binary and set path in zprofile.
            ```sh
            alias heimdall="/Users/tushar/Setups/heimdall-frontend.app/Contents/MacOS/heimdall"
            ```
    3. Get `dmg` from official [website](https://glassechidna.com.au/heimdall/#downloads), but it didn't install for me.
- Check heimdall
    ```sh
    heimdall version
    heimdall print-pit
    ```
- Download Gapps https://github.com/MindTheGapps/15.0.0-arm64/releases
- flash vbmeta or recovery
    ```sh
    heimdall flash --VBMETA vbmeta.img
    heimdall flash --RECOVERY recovery.img --no-reboot
    ```
- flash rom
    ```sh
    adb -d sideload lineage-22.2-20250615-nightly-gta4l-signed.zip
    ```
    - the output will stop at 47%. Wait till it displays "Total xfer: 1.00x" in the terminal
- flash Gapps
    ```sh
    adb -d sideload MindTheGapps-15.0.0-arm64-20250214_082511.zip
    ```
    - To be flashed just after installing rom, don't reboot device after flashing rom.
    - After some delay you have to select "Yes" on the device.
