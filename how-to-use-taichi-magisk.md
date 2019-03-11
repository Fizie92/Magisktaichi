# The Hitchhiker's Guide to Magisk Taichi

[中文漫游指北](TaiChi-Magisk-Guide-zh_CN)

**Please read through the documentations carefully. Modding can be risky, proceed with extreme caution. The hardware can be valued whereas the data are priceless.**

## Before we get started

Magisk TaiChi made a wild assumption that you already have Magisk installed and that you UNDERSTAND how to use Magisk, if you don't, you should first check out the Magisk section on XDA

### See resources at the end of this document

## [Getting ready](https://github.com/taichi-framework/TaiChi/wiki/%E5%87%86%E5%A4%87%E4%BA%8B%E9%A1%B9)

### Backup

1. Back up your damn data! Modding is risky, and for Jesus Christ the lord's sake, back up your damn data!
2. You must(**MUST!!!!!**) uninstall all app created using the normal TaiChi before flashing Magisk TaiChi

### Recovery

In any unforeseen scenarios of malfunctioning, you can recover through the following methods.

#### MM *(Recommended)*

You must install this module in Magisk prior, or flash it using TWRP in case of unable to boot
Usage:
1.Boot into recovery (TWRP is recommended)
2.Start the built in terminal in your recovery
3.Enter /data/media/mm, select u in the first menu and then type in taichi and press enter twice.

***:Alternatively, you can connect your device to your computer, open command prompt/terminal and enter 'adb shell'**

#### Built in recovery mechanism (TaiChi)

1.Boot into recovery (TWRP is recommended)
2.Start the built in terminal in your recovery*
3.Type in rm -rf /data/taichi && rm -rf /data/system/taichi and press enter
4.Reboot

***:Alternatively, you can connect your device to your computer, open command prompt/terminal and enter 'adb shell'**

### Warnings

TaiChi-Magisk is fully tested on Android Pie but it only has a few tests on Android O, it is **not tested at all** below Android O. If your device is below Android O, stop using TaiChi-Magisk!!
 
> TaiChi non-root mode supports Android L~P, but magisk mode only supports Android O ~ P. Magisk mode may run well below Android O in some devices, but i won't fix any bug if it occurs (on Android N or lower devices)

## [Installation](https://github.com/taichi-framework/TaiChi/wiki/%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8)

1. Install latest TaiChi
2. Flash the TaiChi-Magisk module in Magisk Manager or in Recovery mode.
4. Open Taichi and add the apps you need to use with Xposed modules
5. Go to module management and check the checkboxes next to the module you'd like to use
6. Force close the app you are working with
7. Reopen the app and the modules should work well.

**Note: There are certain differences between Magisk Taichi and actual Xposed**

1. Xposed modules only works given that you added the app in Taichi
2. Non-systemwide modules does not need reboot to take effect
3. Reinstalling module will require re-checking the checkbox in module management

## Resources and references

[**Official Website**](https://taichi.cool)
