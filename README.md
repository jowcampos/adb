<div align="center">
    
![](https://github.com/jowcampos/commands-adb/assets/157834890/618a055f-c7db-4d12-9c3d-d60bda091d01)

</div>

The Android Debug Bridge (adb) is a versatile command-line tool that enables communication with a device. The adb command facilitates various device actions, such as installing and debugging apps. adb provides access to a Unix shell that can be used to execute various commands on a device. It is a client-server program with three components:

A client, which sends commands. The client runs on the development machine. You can issue an adb command to invoke the client from a command-line terminal.
A daemon (adbd), which executes commands on a device. The daemon runs as a background process on each device.
A server, which manages communication between the client and the daemon. The server runs as a background process on the development machine.
adb is included in the Android SDK Platform Tools package. Download this package with the SDK Manager, which installs it in android_sdk/platform-tools/.

##### Command to uninstall a package
```sh
adb uninstall br.com.nome.dopackage
```

##### Command to filter package on MacOS
```sh
adb shell logcat | grep "ReactNativeJS"
```

##### Command to activate port for Reactotron
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
