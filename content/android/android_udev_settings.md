# android udev setting

/etc/udev/rules.d/51-android.rules
```
SUBSYSTEM=="usb", ENV{DEVTYPE}=="usb_device", MODE="0666"

# Smartisan T1
SUBSYSTEM=="usb", ATTRS{idVendor}=="29a9", MODE="0660", GROUP="plugdev"
# MI 2
SUBSYSTEM=="usb", ATTRS{idVendor}=="2717", MODE="0660", GROUP="plugdev"
```

~/.android/adb_usb.ini
```
# MI 2
0x2717
```
