# TaiChi·Magisk Notice

## Data backup

### System Data

Any way, flash ROMs/zips is dangerous, data is invaluable.

Please **BACKUP ALL YOUR DATA** in system carefully before you flash Magisk/TaiChi-Magisk-modules.

The developer is **not responsible for the data loss**.

### App data created by TaiChi

Before using TaiChi·Magisk, **You need to uninstall all apps created by non-Magisk Taichi**. 

Please backup the app data if necessary.

## How to rescue?

First of all, you must install [Magisk-Manager-Recovery-Tools](https://github.com/Pzqqt/Magisk_Manager_Recovery_Tool) in Magisk before you flash any TaiChi·Magisk modules.

When you encounter bootloop/system crash after flash the TaiChi-magisk modules, follow these steps can recover it:

1. Long press VOLUME_DOWN and POWER key on your device, the device will reboot to bootloader mode after 10 seconds, press VOLUME_DOWN and VOLUME_UP to select recovery mode and reboot.
2. Open the terminal provided by TWRP (or any other Recovery)
3. Input `/data/media/mm`, and enter `e`, then enter `taichi` and hit ENTEY key twice.
4. Reboot the device and may God bless you.