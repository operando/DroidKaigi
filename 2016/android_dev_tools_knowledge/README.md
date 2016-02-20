
# Android Dev Tools Knowledge

# 資料

* [SlideShare](http://www.slideshare.net/shinobuokano7/android-dev-tools-knowledge)
* [GradlePluginsSample Project](https://github.com/operando/GradlePluginsSample)
 * セッション中に紹介したGradle Pluginを全部含んだサンプルプロジェクト

# shinobu.apk

+ [shinobu.apk #1 のパネルディスカッション録音データとShow Notesを公開しました！](http://hack-it-iron.hatenablog.com/entry/2016/02/08/142322)

# まったりAndroid Framework Code Reading

* [まったりAndroid Framework Code Reading #2 を開催しました](http://hack-it-iron.hatenablog.com/entry/2015/11/28/185529)

#  はじめに

* 表示のDev Toolの話は少なめかも
* 色んなツールがあることを知ってほしい
* さらにいいツールを作ってほしい
* 俺も頑張る(๑•̀ㅂ•́)و✧
* 知ってて使わないのと、知らないで使わないのは違う
* 機会の損失


#  便利なコマンド

* ※Nexus 5 6.0で動作確認!
* マシュマロマシュマロ！！

#  adb


##  簡単にadbの環境を用意する

* brew install android-sdk

##  まずはadbの環境を向上させる

##  adb-peco

* 複数のAndroid端末を同時繋いでる時に便利
* adb-peco
* alias adb='adbp'
* https://github.com/tomorrowkey/adb-peco


##  感謝っ・・・・！圧倒的感謝っ・・・・！

* ※絵は出せません


##  adb-peco

* 複数のAndroid端末を同時につないで困ってませんか？それadb-pecoで選択できるよ！
* http://techlife.cookpad.com/entry/2014/09/09/172449

##  input text

* adb shell input text droidkaigi


##  dumpsys

* dump system services status
* adb shell dumpsys | grep "DUMP OF SERVICE"

##  dumpsys activity

* adb shell dumpsys activity top
* adb shell dumpsys activity | grep -B 1 "Run ## [0-9]*:"
* adb shell dumpsys activity activities | grep apk


##  dumpsys alarm

* adb shell dumpsys alarm


##  dumpsys dbinfo

* adb shell dumpsys dbinfo


##  Settings

* adb shell settings list [system/global/secure]


##  screenrecord

* adb shell screenrecord --bugreport /sdcard/launch.mp4
* adb shell screenrecord --verbose /sdcard/launch.mp4
* adb pull /sdcard/launch.mp4


##  "unofficial" options

* adb shell screenrecord --show-device-info /sdcard/launch.mp4
* adb shell screenrecord --show-frame-time /sdcard/launch.mp4
* adb shell screenrecord --rotate /sdcard/launch.mp4
* 逆向きに録画
* adb shell screenrecord --output-format [mp4/h264/frames/raw-frames] /sdcard/launch.mp4
* 実行してからファイルができるのでMEDIA_SCANNERにスキャン処理させてる
* http://tools.oesf.biz/android-6.0.0_r1.0/xref/frameworks/av/cmds/screenrecord/screenrecord.cpp## 730


##  Systrace

* The Systrace tool helps analyze the performance of your application by capturing and displaying execution times of your applications processes and other Android system processes
* generate an HTML report
* http://developer.android.com/intl/ja/tools/help/systrace.html

##  Systrace

* python systrace.py
* /sdk/platform-tools/systrace

##  Analyzing UI Performance with Systrace

* Analyzing UI Performance with Systrace
* http://developer.android.com/tools/debugging/systrace.html

##  atrace

* atrace = Android System Trace
* adb shell atrace --list_categories

##  atrace

* adb shell atrace --async_start -a com.kouzoh.mercari  -c -b 16000 res
* adb shell atrace --async_stop -a com.kouzoh.mercari  -c -b 16000 res

##  atrace

* http://tools.oesf.biz/android-6.0.0_r1.0/xref/frameworks/native/cmds/atrace/atrace.cpp
* http://tools.oesf.biz/android-6.0.0_r1.0/xref/cts/hostsidetests/atrace/src/android/atrace/cts/AtraceHostTest.java


##  adb and adb shell etc.

##  正直、話そうと思ったら無限にあるのね...

* それで50分話せるくらい...

##  Android-Command-Note

* Android-Command-Note
* https://github.com/operando/Android-Command-Note

##  AndroidShell

* AndroidShell
* https://github.com/cesards/AndroidShell


# Gradle plugin

* [GradlePluginsSample Project](https://github.com/operando/GradlePluginsSample)

##  dexcount-gradle-plugin

* dexcount-gradle-plugin
* https://github.com/KeepSafe/dexcount-gradle-plugin


##  gradle-versions-plugin

* gradle-versions-plugin
* https://github.com/ben-manes/gradle-versions-plugin


##  build-time-tracker-plugin

* build-time-tracker-plugin
* https://github.com/passy/build-time-tracker-plugin


##  gradle-slack-plugin

* gradle-slack-plugin
* https://github.com/Mindera/gradle-slack-plugin


##  gradle-android-command-plugin

* gradle-android-command-plugin
* https://github.com/novoda/gradle-android-command-plugin


##  gradle-android-ribbonizer-plugin

* gradle-android-ribbonizer-plugin
* https://github.com/gfx/gradle-android-ribbonizer-plugin


#  Android Studio Plugin

##  AndroidWiFiADB

* AndroidWiFiADB
* https://github.com/pedrovgs/AndroidWiFiADB


##  ADB Idea

* ADB Idea
* https://github.com/pbreault/adb-idea


##  Android-DPI-Calculator

* Android-DPI-Calculator
* https://github.com/JerzyPuchalski/Android-DPI-Calculator

##  android-parcelable-intellij-plugin

* android-parcelable-intellij-plugin
* https://github.com/mcharmas/android-parcelable-intellij-plugin


##  AdbCommander for Android

* AdbCommander for Android
* https://plugins.jetbrains.com/plugin/7578


##  Genymotion Plugin

* Genymotion Plugin
* https://plugins.jetbrains.com/plugin/7269?pr=idea
* http://docs.genymotion.com/Content/04_Tools/Genymotion_Plugin_for_Android_Studio/Genymotion_Plugin_for_Android_Studio.htm


##  eventbus-intellij-plugin

* eventbus-intellij-plugin
* https://github.com/kgmyshin/eventbus-intellij-plugin


##  eventbus3-intellij-plugin

* eventbus3-intellij-plugin
* https://github.com/kgmyshin/eventbus3-intellij-plugin

##  android-postfix-plugin

* android-postfix-plugin
* https://github.com/takahirom/android-postfix-plugin


##  Android File Grouping Plugin

* Android File Grouping Plugin
* https://github.com/dmytrodanylyk/folding-plugin


##  GsonFormat(おまけ)

* GsonFormat
* https://github.com/zzz40500/GsonFormat

##  Google Developers color scheme

* Google Developers color scheme
* https://github.com/LouisCAD/GoogleDevelopersColorScheme


# その他開発で便利なツール

## androidtool-mac

* androidtool-mac
* https://github.com/mortenjust/androidtool-mac


## tonkotsu

* tonkotsu
* https://github.com/operando/tonkotsu


## vysor

* vysor
* https://chrome.google.com/webstore/detail/vysor-beta/gidgenkbbabolejbgbpnhbimgjbffefm


## Android SDK Search

* Android SDK Search
* https://chrome.google.com/webstore/detail/android-sdk-search/hgcbffeicehlpmgmnhnkjbjoldkfhoin


## DPI Calculator

* DPI Calculator
* https://chrome.google.com/webstore/detail/dpi-calculator/dldofgjemhkpilajnlenfijjpkabilcg
* http://jennift.com/dpical.html


## Android Resource Navigator

* Android Resource Navigator
* https://chrome.google.com/webstore/detail/android-resource-navigato/agoomkionjjbejegcejiefodgbckeebo


## Material Terminal

* Material Terminal
* https://play.google.com/store/apps/details?id=yarolegovich.materialterminal


## materialdoc.com

* materialdoc.com
* https://play.google.com/store/apps/details?id=com.materialdoc
* http://www.materialdoc.com/
* Material Design化する時に便利!!


## DesignOverlay

* DesignOverlay
* https://github.com/Manabu-GT/DesignOverlay-Android
* https://play.google.com/store/apps/details?id=com.ms_square.android.design.overlay
* Material Design化する時に便利!!
* やばい！神！


## デバッグに便利なライブラリ


## stetho

* stetho
* https://github.com/facebook/stetho


## ViewDebug

* Viewの中身をLogで確認できるViewDebugのdumpCapturedViewが便利
* 使用例
* 出力結果
* http://developer.android.com/intl/ja/reference/android/view/ViewDebug.html


## KLog

* KLog
* timberでも同じことできる？？
* https://github.com/ZhaoKaiQiang/KLog


## IntentLogger

* IntentLogger
* https://github.com/Drivemode/IntentLogger
* 普通に便利（笑）


# どこで情報を集めるのか？

* コードを読む
* Google+
* Twitter
* Github
* などなど
* 詳細に


#  まとめ

* まさかの白紙まとめ！！
