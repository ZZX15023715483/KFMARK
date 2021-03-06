![KFMARK logo](https://user-images.githubusercontent.com/5908006/47543804-847b9680-d916-11e8-9861-c0c7b2d39c56.png)

[中文说明](https://github.com/Septillion/KFMARK/blob/master/README-CN.md)

Please note that this app is in its early stages of development. Although we plan to release KFMARK as a free app on Google Play, KFMARK is still a commercial project, thus there is currently no plan to open-source it. FView Technology owns the rights to this app and any unlicensed modification, distribution or reverse-engineering is strictly prohibited.

## Get up and running

Please download BOTH of the following files on the [Release page](https://github.com/Septillion/KFMARK/releases).

- KFMARK Beta Android APK
- KFMARK PC Assistant

After installing the base APK on your phone, you have to enable `Developer Mode` (please search online for how to do that on your model) and enable `USB Debugging`. Then connect your phone to a Windows PC and use KFMARK PC Assistant to activate the background `daemon` used to measure FPS and other factors. Every time you restart your device, you have to run KFMARK PC Assistant again. 

For Mac and Linux users, please download only the KFMARK Beta APK and `daemon`. Then download `adb` from [Android Developers Website](https://developer.android.com/studio/releases/platform-tools). Enable `Developer Mode` on your device. Put `daemon` in the same folder as the `adb`, and manually run the following commands using Terminal in the unzipped directory:

	./adb push daemon /data/local/tmp
	./adb shell chmod 777 /data/local/tmp/daemon
	./adb shell "./data/local/tmp/daemon &"

## Features

KFMARK will allow you to profile and benchmark 3D games running on Android, and show current FPS on a floating window, giving you a direct indication of how smoothly the game is running on your device.

You can optionally record a gaming session and get a complete history of FPS, CPU Frequency and Battery Drain.

All of the benchmarking history is stored locally on your phone for you to review.

KFMARK is compatible with Android 5 and up.

## Privacy

KFMARK runs locally on your devices and requires only storage permissions. All of your benchmarking data is stored locally on your phone and is not uploaded to any servers. On start up, KFMARK will acquire the Model Number of your device, and compare it against our WeChat Mini App database to retrieve hardware information (SoC Model, GPU Model and Display Resolution). We do not log this request; this data is not stored and cannot be used to identify you.

On crash (force close), KFMARK would send the last couple of lines of Crash Report to our server to identify the cause of crash. This report does not contain any personal information and cannot be used to identify you.

## Known Issues

### App appears unactivated after disconnecting from the PC

On devices from certain manufacturers (e.g. OPPO), once the device is disconnected from the PC, all background debugging will be suspended. Unfortunately that includes the KFMARK background daemon. Therefore on these devices, you have to stay connected to the PC while benchmarking.

### Fortnite Error

Fornite refuses to run when `USB Debugging` is enabled in order to prevent 3rd party cheats or mods. There is currently no way to profile public versions of Fornite due to this situation. We would recommend against further modification to the game in case Epic decided to ban user accounts that do so.

### PC Assistant shows No device connected.

This is due to the restrictions of `adb` which we use to install KFMARK background daemon. `adb` will only work in English folder paths. In this case, drag the PC Assistant folder to any root path and try again.

## Bug Report

Please go to the [Issues page](https://github.com/Septillion/KFMARK/issues) to submit a bug report. Please first search for your bug and see if anyone has already submitted the same bug. 

When submitting a bug, please follow this pattern:

	Device Model:
	Device Android Version:
	Device ROM Version:
	---
	Bug Description:
	---
	Steps to Reproduce:
