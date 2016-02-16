

## adb cmds

* http://tools.oesf.biz/android-6.0.0_r1.0/xref/frameworks/base/cmds/

## adb native

* http://tools.oesf.biz/android-6.0.0_r1.0/xref/frameworks/native/cmds/

## top

* adb shell top | grep com.kouzoh.mercari
* top -t | grep com.kouzoh.mercari
* top -d 2 -t | grep com.kouzoh.mercari

# am

* adb shell am monitor

# pm

* adb shell pm list packages
* adb shell pm install [apk path]

# screenrecord

* adb shell screenrecord --bugreport /sdcard/launch.mp4
* adb shell screenrecord --verbose /sdcard/launch.mp4
* adb pull /sdcard/launch.mp4


# settings

* adb shell settings list [system/global/secure]

## "unofficial" options

* adb shell screenrecord --show-device-info /sdcard/launch.mp4
* adb shell screenrecord --show-frame-time /sdcard/launch.mp4
* adb shell screenrecord --rotate /sdcard/launch.mp4
 * 逆向きに録画
* adb shell screenrecord --output-format [mp4/h264/frames/raw-frames] /sdcard/launch.mp4

* 実行してからファイルができるのでMEDIA_SCANNERにスキャン処理させてる
 * http://tools.oesf.biz/android-6.0.0_r1.0/xref/frameworks/av/cmds/screenrecord/screenrecord.cpp#730

# dumpsys

* adb shell  dumpsys | grep "DUMP OF SERVICE"


## dumpsys activity

* adb shell dumpsys activity | grep -B 1 "Run #[0-9]*:"
* adb shell dumpsys activity top
* adb shell dumpsys activity activities | grep apk

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



#  gradle plugin

## gradle pluginのいいところ
* SDKバーション関係ない。2系対応しているプロジェクトでも導入できる
* gradleのバーションは関係しそう




* dexcount-gradle-plugin
* https://github.com/KeepSafe/dexcount-gradle-plugin

* gradle-versions-plugin
* https://github.com/ben-manes/gradle-versions-plugin

* build-time-tracker-plugin
* https://github.com/passy/build-time-tracker-plugin

* gradle-android-apk-size-plugin
* https://github.com/vanniktech/gradle-android-apk-size-plugin

* gradle-slack-plugin
* https://github.com/Mindera/gradle-slack-plugin


# Tools

# androidtool-mac

* androidtool-mac
* https://github.com/mortenjust/androidtool-mac

* tonkotsu
* https://github.com/operando/tonkotsu

* vysor
* https://chrome.google.com/webstore/detail/vysor-beta/gidgenkbbabolejbgbpnhbimgjbffefm


adb shell wm densityに好きな数字を入れて下さいとか書いているページが結構あるけどDisplayMetricsの定義以外の数字入れたらどうなるんだろう。
怖すぎる。


02-11 22:34:43.858 I/GAv4    (30038): Google Analytics 8.1.15 is starting up. To enable debug logging on a device run:
02-11 22:34:43.858 I/GAv4    (30038):   adb shell setprop log.tag.GAv4 DEBUG
02-11 22:34:43.858 I/GAv4    (30038):   adb logcat -s GAv4


### 概要

```
対象者：
Android開発をする上で便利なツールやコマンド、ライブラリを知りたい人
・ 初心者でも使えるもの多め
・ 一部、動きを理解する上で前提知識が必要なものがあるかもしれませんが使う上では初心者でもOK
・ ツールを使ってガシガシ開発効率上げたい中級者〜にもオススメ

概要：
近年、Android StudioやGradleの登場によって、標準の開発環境が日々向上しています。
Android開発を効率的に行う上で欠かせないデベロッパーツールもたくさんあります。

そんな開発の役立つデベロッパーツール、コマンド、ライブラリなどのナレッジを余すことなくご紹介したいと思います。
実際にツール等を使いながら紹介する部分も用意します。(ワークショップ的に自分の手元で動かしたい人向けにも簡単なもの)
Android SutdioやPluginだけでは物足りない！という方向けに、より深くAndroidを理解する上で役に立つものもご紹介します。
これらを知ることで、今まで以上に開発効率の向上、Android楽しさ・奥深さを知っていただけると嬉しいです。

具体的には以下の様なものを想定しています。
* 便利なコマンド(adb,systrace。adb関連多め) ※1
* Android Studio Plugin
* Gradle Plugin
* デバッグに便利なライブラリ
* その他開発で便利なツール

※ このセッションはADT(Android Developer Tools)だけに関するものではありません
* This session is not about ADT (Android Developer Tools)

※1 参考 https://github.com/operando/Android-Command-Note
```
