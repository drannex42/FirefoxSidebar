# Android Utils

## Remove empty gesture space below keyboards 
Requires ADB and USB 

``` adb shell wm overscan 0,0,0,-75```

## Fullscreen apps 
This will turn any specific package into a fullscreen app, this eample uses firefox.

```adb shell settings put global policy_control immersive.full=org.mozilla.fenix```
