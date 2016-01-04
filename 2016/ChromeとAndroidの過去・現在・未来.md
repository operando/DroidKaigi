

## Chrome for Android

* Chrome (Stable)
 * https://play.google.com/store/apps/details?id=com.android.chrome
* Chrome Beta
 * https://play.google.com/store/apps/details?id=com.chrome.beta
* Chrome Dev
 * https://play.google.com/store/apps/details?id=com.chrome.dev


## Chrome Beta

* Preview the latest features: Try out the newest features. (Sometimes these may be a little rough around the edges.)


## Chrome Dev

* Live on the bleeding edge: Try out our latest features. (They'll be rough around the edges!)

## Chrome Releases Information

* http://googlechromereleases.blogspot.jp/


## Chrome Releases Information

* Stable Info
 * http://googlechromereleases.blogspot.jp/search/label/Chrome%20for%20Android

* Beta Info
 * http://googlechromereleases.blogspot.jp/search/label/Chrome%20Beta%20for%20Android

* Dev Info(Update stop)
 * http://googlechromereleases.blogspot.jp/search/label/Chrome%20Dev%20for%20Android 


## WebView History

* Android 1.x 〜 Android 4.3.x
 * Based on the WebKit
 * Google I/O 2012 - Android WebView
  * https://android.googlesource.com/platform/external/chromium_org/+/kitkat-mr2-release/chrome/VERSION
* Android 4.4.x
 * Chromemise Based WebView
 * KK MR1 Chrome M30
  * http://tools.oesf.biz/android-4.4.0_r1.0/xref/external/chromium_org/chrome/VERSION
 * KK MR3 Chrome M33
  * https://android.googlesource.com/platform/external/chromium_org/+/kitkat-mr2-release/chrome/VERSION
  * このバージョンごとのChrome Update作業は、Lの途中までは行われていたっぽい。L PreviewならChrome M37だった
* Android 5.x 〜
 * Android System WebView
 * In Android 5.0 (Lollipop), the WebView has moved to an APK so it can be updated seperately to the Android platform. 
 * https://play.google.com/store/apps/details?id=com.google.android.webview

## WebView

* http://developer.android.com/reference/android/webkit/WebView.html
* It uses the WebKit rendering engine to display web pages and includes methods to navigate forward and backward through a history, zoom in and out, perform text searches and more.

## What is "Android Browser"

* 忘れてくれ...

### 概要

```
概要：
ChromeとAndoridは、お互いにバージョンが新しくなるごとに互いの親和性が高くなってきています。
WebコンテンツとAndroidアプリの両方を作っている場合、Chrome for Android(Android版のChrome)というのはWebとアプリを繋げる上で非常に重要な役割を果たしています。
今後さらに、ChromeとAndroidの関係性は重要になっていくと思います。

本セッションではChromeを活用したAndroidアプリ開発について話します。
はじめにChrome for Androidの概要、AndroidにおけるWebViewの変化などを話します。
次にChromeの技術の中でも、とくにAndroidアプリへ活用できそうな機能などを話します。
最後にChromeとAndroidの今後について、興味深い動き・考え方について話します。

内容案：
* Chrome for Androidの種類
* WebViewの変化
* Chrome Custom Tabs
* Web App Manifest
* Service WorkersとPush Notifications
* App Stream ※1
* Progressive Web Apps
* ChromeとAndroidの今後について(個人的主観)

対象者：
* WebコンテンツとAndroidアプリの両方を運用している会社 or 人
* ChromeとAndroidの親和性を有効的に活用したい人
* アプリ内でWebViewを使っている人 or 使いたいと思ってる人

※1 参考:http://insidesearch.blogspot.ca/2015/11/new-ways-to-find-and-stream-app-content.html
```
