# Efficiency with ADB commands
<div align="center">
    

</div>

The Android Debug Bridge (adb) is a powerful command-line tool specifically tailored for mobile device testing. Designed to streamline testing procedures, adb facilitates a wide range of essential tasks required for mobile testing scenarios. Its functionality encompasses everything from installing and debugging apps to capturing logs and interacting with device UI elements.

With adb, testers gain access to a Unix shell, enabling them to execute commands directly on the device. This client-server program comprises three key components:

## Client
Situated on the development machine, the client initiates commands, providing testers with a straightforward interface to interact with mobile devices via simple command-line instructions.

## Daemon 
Running silently in the background on each device, the daemon executes commands issued by the client, ensuring smooth and efficient execution of testing procedures.

## Server
Acting as the intermediary between the client and the daemon, the server manages communication, facilitating seamless transmission of commands and data during the testing process. Operating discreetly in the background on the development machine, the server ensures uninterrupted testing operations.

Included as part of the Android SDK Platform Tools package, adb seamlessly integrates into the testing environment. Testers can easily access adb by downloading the package through the SDK Manager, providing them with the necessary tools to conduct comprehensive mobile testing procedures.

In summary, adb is an indispensable tool for mobile device testing, offering testers the flexibility, efficiency, and reliability required to ensure the quality and performance of mobile applications across a variety of testing scenarios.

## Useful commands
##### Command to uninstall a package
```sh
adb uninstall br.com.namepackage
```

##### Command to filter package on MacOS
```sh
adb shell logcat | grep "ReactNativeJS"
```

##### Command to activate port for [Reactotron](https://github.com/infinitered/reactotron)
```bash
adb reverse tcp:9090 tcp:9090
```

##### Command to filter package on Windows
```sh
adb shell logcat | Select-String -Pattern "ReactNativeJS"
```

##### Command to copy app screen using [scrcpy](https://github.com/Genymobile/scrcpy)
```sh
scrcpy
```

##### Command to list packages
```bash
adb shell pm list packages
```

##### Command to install multiple packages at once on Windows
```bash
Get-ChildItem *.apk | ForEach-Object { adb install -r $_.FullName }
```

##### Command to install multiple packages at once on MacOS 

```sh
for file in *.apk; do
    adb install -r -d "$file"
done
```
#### Command to capture device screen
```sh
adb shell screencap -p /sdcard/screenshot.png
```
#### Command to record device screen
```sh
adb shell screenrecord /sdcard/video.mp4
```
#### Command to disconnect device via TCP/IP
```sh
adb disconnect
```
#### Command to force device reboot
```sh
adb reboot
```
#### Command to simulate device battery unplug
```sh
adb shell dumpsys battery unplug
```
#### Command to simulate touch on device screen
```sh
adb shell input tap <x> <y>
```
#### Command to simulate swipe on device screen
```sh
adb shell input swipe <x1> <y1> <x2> <y2>
```
## Putting ADB to Use in Testing Scenarios 🧪

Now that you're equipped with essential ADB commands, let's explore how you can leverage them in various testing scenarios:

Automated Testing
Integrate ADB commands into your automated testing scripts to perform tasks such as installing and launching apps, capturing logs, and interacting with device UI elements.

Exploratory Testing
Use ADB to quickly install and uninstall apps, capture device logs for analysis, and take screenshots to document issues encountered during exploratory testing sessions.

Performance Testing
Monitor device performance by capturing logs using ADB and analyzing metrics such as CPU and memory usage. You can also simulate user interactions using ADB commands to assess app responsiveness under different conditions.

Compatibility Testing
Utilize ADB to install and test apps across multiple Android devices and versions. Capture logs and screenshots to identify compatibility issues and ensure seamless user experience across devices.
