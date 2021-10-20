Android Framework Code Readingをする上で便利なサイト・ツールなどの紹介で出すものまとめる
サイト : Android Code Search、AOSP
ツール : AIDEGen、Android Debug Bridge (ADB) 、CTS、bugreport




## 話す内容に入れるといいかもしれないネタ

- Android 12が公開されたので読んでみるとか（ACSに出てれば）
Log.isLoggableをみたら propしよう！
ソースコード全部手元に落としてきて確認する方法
repoとかね


## log

I/UninstallerActivity(19960): Uninstalling extras=Bundle[{com.android.packageinstaller.extra.APP_LABEL=DroidKaigi 2021, com.android.packageinstaller.applicationInfo=ApplicationInfo{5f5ccec io.github.droidkaigi.feeder.debug}, android.intent.extra.UNINSTALL_ALL_USERS=false, com.android.packageinstaller.extra.UNINSTALL_ID=-2147483643}]
I/ActivityManager( 1424): Force stopping io.github.droidkaigi.feeder.debug appid=10666 user=0: deletePackageX
I/ActivityManager( 1424): Killing 23256:io.github.droidkaigi.feeder.debug/u0a666 (adj 940): stop io.github.droidkaigi.feeder.debug due to deletePackageX

