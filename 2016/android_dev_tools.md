

## adb cmds

* http://tools.oesf.biz/android-6.0.0_r1.0/xref/frameworks/base/cmds/

## adb native

* http://tools.oesf.biz/android-6.0.0_r1.0/xref/frameworks/native/cmds/

## top

* adb shell top | grep com.kouzoh.mercari
* top -t | grep com.kouzoh.mercari
* top -d 2 -t | grep com.kouzoh.mercari

# dumpsys

* adb shell  dumpsys | grep "DUMP OF SERVICE"


## dumpsys activity

* adb shell dumpsys activity | grep -B 1 "Run #[0-9]*:"
* adb shell dumpsys activity top


## dumpsys alarm

* adb shell dumpsys alarm

## dumpsys dbinfo

* adb shell dumpsys dbinfo


## adb shell atrace


* http://tools.oesf.biz/android-6.0.0_r1.0/xref/frameworks/native/cmds/atrace/atrace.cpp
* http://tools.oesf.biz/android-6.0.0_r1.0/xref/cts/hostsidetests/atrace/src/android/atrace/cts/AtraceHostTest.java

### adb shell atrace --list_categories

```
gfx - Graphics
input - Input
view - View System
webview - WebView
 wm - Window Manager
 am - Activity Manager
 sm - Sync Manager
audio - Audio
video - Video
camera - Camera
hal - Hardware Modules
app - Application
res - Resource Loading
dalvik - Dalvik VM
 rs - RenderScript
bionic - Bionic C Library
power - Power Management
sched - CPU Scheduling
freq - CPU Frequency
idle - CPU Idle
load - CPU Load
```


* adb shell atrace --async_start -a com.kouzoh.mercari  -c -b 16000 res
* adb shell atrace --async_stop -a com.kouzoh.mercari  -c -b 16000 res
