# コマンドなしでぼくはAndroid開発できない話

## 資料

* [speakerdeck](https://speakerdeck.com/operando/komantonasitehokuhaandroidkai-fa-tekinaihua-1)
* [Android-Command-Note](https://github.com/operando/Android-Command-Note)


## 概要

* Day2 Room4 15:10-
* https://droidkaigi.github.io/2017/timetable.html#session-60


## 注意事項

**資料内のコマンドにpackageName と書かれている部分は アプリのパッケージ名に 置き換えてお試しください！**


## Androidでコマンド？🤔


## Androidでコマンド使えるようになりたーい😆


## できます😊


## 使えるようになるために

* Android SDKまわりにちょっとPathを通すだけ
* 基本、それだけ！

## Android SDK周りのどこにPath通せばいいのか

* sdk/tools
* sdk/tools/bin
* sdk/platform-tools
* sdk/build-tools/<version>
* sdk/platform-tools/systrace (おまけ)


## コマンド使いやすくするぞ💪


## adb-peco

* 複数のAndroid端末を同時繋いでる時に便利
* alias adb='adb-peco'
* https://github.com/tomorrowkey/adb-peco


## adb-peco

* 複数のAndroid端末を同時につないで困ってませんか？それadb-pecoで選択できるよ！
* http://techlife.cookpad.com/entry/2014/09/09/172449


## adb-peco

* adb-pecoを書き直しました by tomorrowkey
* http://tomorrowkey.hatenablog.jp/entry/2016/07/31/adb-peco%E3%82%92%E6%9B%B8%E3%81%8D%E7%9B%B4%E3%81%97%E3%81%BE%E3%81%97%E3%81%9F


## 過去に使ったコマンドをインクリメントに調べて使う

* peco select adb history
* https://gist.github.com/operando/250da59cc97d89c33337fe5b129e09f5



## adb

* Android Debug Bridge


## adb

* https://developer.android.com/studio/command-line/adb.html


## 実機とエミュレータでは実行できるコマンドは違う

* 実機にはないけどエミュレータには入ってるコマンドはそこそこある
* セキュリティ上の理由なのかな？


## ネットワーク越しでコマンドを実行する


* adb shell ip addr show wlan0  | grep 'inet ' | cut -d' ' -f6|cut -d/ -f1
 * ip部分だけ取り出す
* adb tcpip 5555
* adb connect ip:5555


## AndroidWiFiADB

* Android StudioのPlugin
* https://github.com/pedrovgs/AndroidWiFiADB
* まあこっちの方が楽


## input text

* 文字入力めっちゃ簡単になる最強コマンド✨

## input text

* adb shell input text droidkaigi2017


## input keyevent

* Key eventを発行できる


## input keyevent

* adb shell input keyevent KEYCODE_POWER
 * 電源キー押す
* adb shell input keyevent KEYCODE_SLEEP
 * スクリーンOFF

## adb shell inputのコード

http://tools.oesf.biz/android-7.1.1_r1.0/xref/frameworks/base/cmds/input/src/com/android/commands/input/Input.java


## reboot

* 再起動コマンド
* adb shell reboot


## am


## am start

* Activityをスタートさせるもの

## am start

* adb shell am start -a android.intent.action.VIEW -d https://google.com


## am broadcast

* Broadcastを実行するコマンド

## am broadcast

* adb shell am broadcast -a com.android.systemui.BATTERY_LEVEL_TEST
* 電池残量0〜100%の画像をアニメーションで確認できる！
 * 使わないだろー😇


## am hang

* 今やらないようにねｗ
* hangするので
* hangしてどうしようもなくなったらadb shell rebootですよ！


## am Source Code

* http://tools.oesf.biz/android-7.1.1_r1.0/xref/frameworks/base/cmds/am/src/com/android/commands/am/Am.java
* http://tools.oesf.biz/android-7.1.1_r1.0/xref/frameworks/base/services/core/java/com/android/server/am/ActivityManagerShellCommand.java


## pm


## pm

* PackageManager


## pm path

* 指定したパッケージ名のapkの場所を教えてくれる
* adb shell pm path packageName


## pm clear

* アプリケーションのデータをクリアする
* adb shell pm clear packageName



## pm list

* adb shell pm list packages
* adb shell pm list packages -e
* adb shell pm list packages -d
* adb shell pm list packages -s
* adb shell pm list packages -3


## pm source code

* http://tools.oesf.biz/android-7.1.1_r1.0/xref/frameworks/base/cmds/pm/src/com/android/commands/pm/Pm.java
* http://tools.oesf.biz/android-7.1.1_r1.0/xref/frameworks/base/services/core/java/com/android/server/pm/PackageManagerShellCommand.java


## dumpsys

## dumpsys

* システムサービスの状態をダンプ
* 色々含めて動作チェックしたい時にめっちゃ便利

## dumpsys

* adb shell dumpsys -l
 * これでsystem serviceの一覧が見える
 * 気になるSystem Serviceを探す


## adb shell dumpsys activity

* Activityの情報をdumpする
* adb shell dumpsys activity


## adb shell dumpsys activity top

* adb shell dumpsys activity top
* 今表示してるActivityの情報が見える！
* レイアウトの構造も見れる！
* FragmentManagerの情報もdumpされる


## adb shel dumpsys activity top

* 新しいプロジェクトや見知らぬコードを読む時に役立つ
* この画面ってどのActivity? どのFragment? みたいなことを調べるのに最適
* 人様のアプリのViewの構造を調べるのに最適


## dumpsys usagestats

* adb shell dumpsys usagestats


## adb shell dumpsys dbinfo

* adb shell dumpsys dbinfo
* adb shell dumpsys dbinfo packageName
* 実行したSQLとかの履歴が見える
* テーブル構造丸裸問題🙈


## log

## log

* logcatに任意のlogを打ち込む
* shell log DroidKaigi2017やってくぞ！
* とある操作の範囲のlogcatを見たい時などに 操作の始めと終わりにlogを打つとかに便利


## run-as


## run-as

* 実行するプロセスを変える?
* adb shell run-as packageName
* /data/data/packageName配管のファイルを見たい時に便利


## run-as source code

* http://tools.oesf.biz/android-7.1.1_r1.0/xref/system/core/run-as/


## bugreport


## bugreport

* adb bugreport


## bugreportz

* adb shell bugreportz
* bugreportをzip化したものが作れる
 * bugreportはものすごくでかい


## bugreportz

* 以下に書き出される
  * /data/user_de/0/com.android.shell/files/bugreports
* OK:/data/user_de/0/com.android.shell/files/bugreports/bugreport-NPG05D-2017-03-10-07-41-37.zip
* 生成されたらadb pullして取り出す


## bugreportz Source Code

* https://android.googlesource.com/platform/frameworks/native/+/refs/heads/master/cmds/bugreportz/


## adb uninstall

* adb uninstall packageName
* アプリをアンインストールする


## データとキャッシュを残したままアンインストールする

* adb shell cmd package uninstall -k packageName


## その他いっぱいありますよ！


## コマンド応用していくぞ💪


## 特定のアプリのSetting画面をコマンドで一発で出す!!

* shell am start -a android.settings.APPLICATION_DETAILS_SETTINGS -d package:com.souzoh.android.atte



## インストールされているパッケージ名をソートして出す！

* adb shell pm list packages | sed 's@^package\:@@g' | sort


## apk引っこ抜くことに全力を尽くした！

* adb shell dumpsys activity activities | grep apkを改造してpecoと合わせて選択してpullするやつ作る


## apk引っこ抜くことに全力を尽くした！

adb shell dumpsys activity activities | grep apk | sed -e 's/ *baseDir=//g' | peco | xargs adb pull


## apk引っこ抜くことに全力を尽くした！

* dumpsys activity activitiesとpecoでゴニョゴニョして端末からapkを簡単に引っこ抜く
* http://qiita.com/operandoOS/items/6fa77037560e52d11352


## dryrun

* gem install dryrun
* dryrun リポジトリのURL
* https://github.com/cesarferreira/dryrun


## コマンド周りのsource code

* http://tools.oesf.biz/android-7.0.0_r1.0/xref/frameworks/base/cmds/
* http://tools.oesf.biz/android-7.0.0_r1.0/xref/system/core/


## コマンドの実体を調べる方法

* logcatを見る
* コマンドの出力結果から固定値っぽいものを見つけて、それを出力してる処理を探す
 * そこからどんどん掘り下げていく
* ソースコードから頑張って探す！


## コマンドラインツールを色んな言語で作るための素材

* DeviceAPI-Android
 * https://github.com/bbc/device_api-android
 * ruby
* adbkit
 * https://github.com/openstf/adbkit
 * node.js


## Android Command Note

* 紹介したコマンドとかまとめてます！
* https://github.com/operando/Android-Command-Note


## Thanks!!
