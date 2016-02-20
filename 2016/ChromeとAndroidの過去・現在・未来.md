

# 過去

# 現在

# 未来


## Chrome??

* とにかく素晴らしいブラウザだ！

## Chrome??

* Web Browser developed by Google
* Blink Rendering Engine
* V8 JavaScript Engine

## Chromium??

* open-source browser project that aims to build a safer, faster, and more stable way for all Internet users to experience the web

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

## Freezing Chrome for Ice Cream Sandwich

* Chrome’s 42nd release, we’ll stop updating Chrome on ICS devices.
* Developing new features on older phones has become increasingly challenging, and supporting ICS takes time away from building new experiences on the devices owned by the vast majority of our users.
* http://blog.chromium.org/2015/03/freezing-chrome-for-ice-cream-sandwich_3.html

## Chrome history

08/09 Chrome Release
08/10 世界初のAndroid搭載スマートフォン、「T-Mobile G1」が出る
12/06/27 Chrome for Android Release
12/01/10 Chrome Beta for Android Release
13/04 レンダリングエンジンがWebKitからBlinkに変わる
4APRIL 29, 2015 Chrome Dev Release

10/12 Android 2.3 Release
11/10 Android 4.0 Release
13/10/31 Android 4.4 Release
15/04 Chrome 42でICS向けのUpdateが終了

????? Chrome 28からレンダリングエンジンがBlinkに変わる

note : AndroidのカンファレンスなのでChromeの振り返りはサックっと終わらせる

Dc4a3a

ffce40

0f9e5a

45873f

https://www.youtube.com/watch?v=0tH-KHvifMk


## WebView History

* Android 1.x 〜 Android 4.3.x
 * Based on the WebKit
 * Google I/O 2012 - Android WebView
  * https://www.youtube.com/watch?v=HbOtn5VhGZU
* Android 4.4.x
 * Chromium Based WebView
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


## Remote Debugging

* Remote debugging on Android with Chrome DevTools
* Remote debugging on WebViews in your native Android apps with Chrome Developer Tools



* On Android 4.4 (KitKat) or later, you can use DevTools to debug WebView content in native Android applications.


* chrome://inspect/#devices


```java
if (BuildConfig.DEBUG && Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
    WebView.setWebContentsDebuggingEnabled(true);
}
```



## Chrome Custom Tabs

* Chrome Beta、Chrome Devを入れている状態でデフォルトをChrome Betaにしてても、Chrome DevでTabが開く
* Chrome Custom Tabsで読み込んだらデータセーバーかかってデータも小さくなったりする？？
* Custom tabs上でService Workers動くのか??
 * 動く。Push有効にできる。ktkr
* Internetパーミッションが不要
* WebViewではIntentが動かなかったけどCustom TabsならChromeだからIntente動くよね？
 * 何かのActionで双方向呼び出しが確実なものになった


+ Webの技術を追っかけた方がなにかといい


```
02-14 14:15:16.629 I/ActivityManager(  782): START u0 {act=android.intent.action.VIEW dat=https://operando.github.io/... pkg=com.chrome.dev cmp=com.chrome.dev/com.google.android.apps.chrome.Main (has extras)} from uid 10122 on display 0
02-14 14:15:16.654 D/ConnectivityService(  782): listenForNetwork for Listen from uid/pid:10118/529 for NetworkRequest [ id=230, legacyType=-1, [ Capabilities: INTERNET&NOT_RESTRICTED&TRUSTED&NOT_VPN] ]
02-14 14:15:16.668 I/ActivityManager(  782): START u0 {act=android.intent.action.VIEW dat=https://operando.github.io/... pkg=com.chrome.dev cmp=com.chrome.dev/org.chromium.chrome.browser.customtabs.CustomTabActivity (has extras)} from uid 10118 on display 0
02-14 14:15:16.735 W/ResourceType(  529): Failure getting entry for 0x7f040059 (t=3 e=89) (error -75)
02-14 14:15:16.770 I/ActivityManager(  782): Start proc 1069:com.chrome.dev:sandboxed_process10/u0i69 for service com.chrome.dev/org.chromium.content.app.SandboxedProcessService10
02-14 14:15:16.832 I/ActivityManager(  782): Displayed com.chrome.dev/org.chromium.chrome.browser.customtabs.CustomTabActivity: +156ms (total +194ms)
```

```
02-14 14:27:15.872 I/ActivityManager(  782): Process com.chrome.dev:sandboxed_process10 (pid 1069) has died
02-14 14:27:15.872 W/ActivityManager(  782): Scheduling restart of crashed service com.chrome.dev/org.chromium.content.app.SandboxedProcessService10 in 1000ms
```

```
02-14 14:28:44.720 I/am_focused_activity(  782): [0,com.chrome.dev/com.google.android.apps.chrome.Main]
02-14 14:28:44.721 I/am_on_paused_called(  688): [0,com.os.operando.chromecustomtabs.starterkit.MainActivity]
02-14 14:28:44.732 I/am_restart_activity(  782): [0,51280859,1176,com.chrome.dev/com.google.android.apps.chrome.Main]
02-14 14:28:44.738 I/force_gc(  782): Binder
02-14 14:28:44.750 I/am_home_stack_moved(  782): [0,0,13,13,sourceStackToFront]
02-14 14:28:44.750 I/wm_task_moved(  782): [1176,1,2]
02-14 14:28:44.752 I/am_create_activity(  782): [0,142672269,1176,com.chrome.dev/org.chromium.chrome.browser.customtabs.CustomTabActivity,android.intent.action.VIEW,NULL,https://operando.github.io/...,0]
02-14 14:28:44.753 I/am_pause_activity(  782): [0,51280859,com.chrome.dev/com.google.android.apps.chrome.Main]
02-14 14:28:44.753 I/am_home_stack_moved(  782): [0,0,13,13,startedActivity setFocusedActivity]
02-14 14:28:44.753 I/wm_task_moved(  782): [1176,1,2]
02-14 14:28:44.755 I/am_focused_activity(  782): [0,com.chrome.dev/org.chromium.chrome.browser.customtabs.CustomTabActivity]
02-14 14:28:44.756 I/am_finish_activity(  782): [0,51280859,1176,com.chrome.dev/com.google.android.apps.chrome.Main,app-request]
02-14 14:28:44.761 I/am_restart_activity(  782): [0,142672269,1176,com.chrome.dev/org.chromium.chrome.browser.customtabs.CustomTabActivity]
02-14 14:28:44.787 I/am_destroy_activity(  782): [0,51280859,1176,com.chrome.dev/com.google.android.apps.chrome.Main,finish-idle]
02-14 14:28:44.801 I/am_proc_start(  782): [0,3543,99070,com.chrome.dev:sandboxed_process11,service,com.chrome.dev/org.chromium.content.app.SandboxedProcessService11]
02-14 14:28:44.802 I/am_on_resume_called(  529): [0,org.chromium.chrome.browser.customtabs.CustomTabActivity]
02-14 14:28:44.837 I/am_proc_bound(  782): [0,3543,com.chrome.dev:sandboxed_process11]
02-14 14:28:44.850 I/am_pss  (  782): [1135,10175,dk.alroe.apps.WallpaperSaverFree,3396608,2850816]
02-14 14:28:44.901 I/am_activity_launch_time(  782): [0,142672269,com.chrome.dev/org.chromium.chrome.browser.customtabs.CustomTabActivity,141,179]
```


```
USER      PID   PPID  VSIZE  RSS   WCHAN            PC  NAME
u0_a122   688   215   902288 50492 sys_epoll_ 00000000 S com.os.operando.chromecustomtabs.starterkit
u0_i70    3543  215   1017832 60236 sys_epoll_ 00000000 S com.chrome.dev:sandboxed_process11
```

* https://chromium.googlesource.com/chromium/src/+/50.0.2650.2/chrome/android/java/src/org/chromium/chrome/browser/document/ChromeLauncherActivity.java
* Custom Tabsで起動すると、まずChrome App側のこのActivityが起動する
* onCreate内でIntentの中身を見てどんな感じで呼びだされたのかを判定したりしてる
* launchCustomTabActivityメソッドでCustomTabActivity起動してる
* CustomTabActivity起動した後はfinishiしてる

## Native App Install Banner

```
TASK com.chrome.dev id=163
  ACTIVITY com.chrome.dev/org.chromium.chrome.browser.ChromeTabbedActivity c6b2a97 pid=18858
    Local FragmentActivity 531ca93 State:
      mCreated=truemResumed=true mStopped=false mReallyStopped=false
      mLoadersStarted=true
    FragmentManager misc state:
      mHost=android.support.v4.app.s@dba8691
      mContainer=android.support.v4.app.s@dba8691
      mCurState=5 mStateSaved=false mDestroyed=false
    View Hierarchy:
      com.android.internal.policy.PhoneWindow$DecorView{291a9f6 V.ED.... ... 0,0-1080,1920}
        android.widget.LinearLayout{41281f7 V.E..... ... 0,0-1080,1776}
          android.view.ViewStub{b84c864 G.E..... ... 0,0-0,0 #10203ab android:id/action_mode_bar_stub}
          android.widget.FrameLayout{deffacd V.E..... ... 0,72-1080,1776}
            android.support.v7.internal.widget.FitWindowsFrameLayout{5266f82 V.E..... ... 0,0-1080,1704 #7f110099 app:id/action_bar_root}
              android.support.v7.internal.widget.ContentFrameLayout{7e34693 V.E..... ... 0,0-1080,1704 #1020002 android:id/content}
                android.widget.LinearLayout{3f806d0 V.E..... ... 0,0-1080,1704}
                  org.chromium.chrome.browser.compositor.CompositorViewHolder{78e76c9 V.E..... ... 0,0-1080,1704 #7f1101ad app:id/compositor_view_holder}
                    org.chromium.chrome.browser.compositor.CompositorView{85001ce V.E..... ... 0,0-1080,1704}
                    android.widget.FrameLayout{df1b8ef V.E..... ... 0,0-1080,1704}
                      org.chromium.content.browser.ContentView$ContentViewApi23{e1ebffc VFE...C. F.. 0,0-1080,1704}
                        android.view.View{60f7140 V.ED.... ... 0,168-0,168}
                      org.chromium.chrome.browser.infobar.InfoBarContainer{a7eb685 V.ED.... ... 0,1235-1080,1704}
                        org.chromium.chrome.browser.infobar.InfoBarContainerLayout{36e6cda V.E..... ... 0,0-1080,469}
                          org.chromium.chrome.browser.infobar.InfoBarWrapper{5caf50b V.E..... ... 0,0-1080,469}
                            org.chromium.chrome.browser.infobar.InfoBarLayout{f95dfe8 V.E..... ... 0,24-1080,469}
                              android.widget.ImageView{2793601 V.ED..C. ... 48,48-192,192}
                              org.chromium.chrome.browser.infobar.InfoBarControlLayout{1d67ca6 V.E...C. ... 240,48-912,193}
                                org.chromium.ui.widget.TextViewWithClickableSpans{b1d6e7 VFED..CL ... 0,0-672,73 #7f11001c app:id/infobar_message}
                                android.widget.FrameLayout{8dd1294 V.E..... ... 0,97-672,145}
                                  android.widget.RatingBar{442313d V.ED.... ... 0,0-240,48 #7f110193 app:id/control_rating}
                              org.chromium.chrome.browser.infobar.InfoBarDualControlLayout{d5dbd32 V.E..... ... 48,289-1032,397}
                                org.chromium.ui.widget.ButtonCompat{73afa83 VFED..C. ... 613,0-984,108 #7f110018 app:id/button_primary}
                                android.widget.ImageView{c2c400 V.ED.... ... 0,23-300,86}
                              android.widget.ImageButton{2a5a439 VFED..C. ... 912,0-1080,168 #7f11001a app:id/infobar_close_button}
                  android.widget.HorizontalScrollView{5a67a7e GFED.... ... 0,0-0,0 #7f1101ae app:id/keyboard_accessory}
                  org.chromium.chrome.browser.widget.FadingShadowView{ca8bbdf G.ED.... ... 0,0-0,0 #7f1101af app:id/bottombar_shadow}
                  android.view.ViewStub{a90202c G.E..... ... 0,0-0,0 #7f1101b0 app:id/bottombar_stub}
                android.view.ViewStub{7334af5 G.E..... ... 0,0-0,0 #7f1101b1 app:id/omnibox_results_container_stub}
                android.view.View{2bc08a G.ED.... ... 0,0-0,0 #7f1101b3 app:id/action_bar_black_background}
                org.chromium.chrome.browser.toolbar.ToolbarControlContainer{c0736fb V.E..... ... 0,0-1080,198 #7f11010d app:id/control_container}
                  org.chromium.chrome.browser.toolbar.ToolbarControlContainer$ToolbarViewResourceFrameLayout{2f51318 V.E..... ... 0,0-1080,198 #7f11010e app:id/toolbar_container}
                    org.chromium.chrome.browser.toolbar.ToolbarPhone{abaa171 V.ED.... ... 0,0-1080,168 #7f11010f app:id/toolbar}
                      org.chromium.chrome.browser.widget.newtab.NewTabButton{d0d5b56 IFED..C. ... 0,0-168,168 #7f110247 app:id/new_tab_button}
                      org.chromium.chrome.browser.widget.TintedImageButton{f52179a GFED..C. ... 0,0-0,0 #7f110248 app:id/return_button}
                      org.chromium.chrome.browser.toolbar.HomePageButton{44128cb GFED..CL ... 0,0-0,0 #7f110249 app:id/home_button}
                      org.chromium.chrome.browser.omnibox.LocationBarPhone{f28c1b7 V.E..... ... 24,0-774,168 #7f11024a app:id/location_bar}
                        android.support.v7.widget.x{b0847d7 G.ED.... ... 0,0-0,0 #7f1101a1 app:id/incognito_badge}
                        android.widget.FrameLayout{fb448c4 V.E..... ... 6,24-114,144 #7f1101a2 app:id/location_bar_icon}
                          android.support.v7.widget.x{986e3ad V.ED..C. ... 0,0-108,120 #7f1101a3 app:id/navigation_button}
                          android.support.v7.widget.v{c9bd6e2 VFED..C. ... 0,0-108,120 #7f110117 app:id/security_button}
                        org.chromium.chrome.browser.omnibox.UrlContainer{e9f8a73 V.E...C. ... 114,33-744,135 #7f1101a4 app:id/url_container}
                          org.chromium.chrome.browser.omnibox.UrlBar{e0f2d30 VFED..CL ... 0,0-630,102 #7f11011a app:id/url_bar}
                          org.chromium.chrome.browser.omnibox.TrailingTextView{f5b0da9 G.ED.... ... 630,0-630,102 #7f110255 app:id/trailing_text}
                        android.widget.FrameLayout{1a47f2e G.E..... ... 0,0-0,0 #7f1101a6 app:id/url_action_container}
                          org.chromium.chrome.browser.widget.TintedImageButton{d5e5acf IF.D..C. ... 0,0-0,0 #7f1101aa app:id/delete_button}
                          org.chromium.chrome.browser.widget.TintedImageButton{bf1ec5c IFED..C. ... 0,0-0,0 #7f1101ab app:id/mic_button}
                      android.widget.LinearLayout{72ddb65 V.E..... ... 798,0-1080,168 #7f11024b app:id/toolbar_buttons}
                        android.widget.Space{c7d603a I.ED.... ... 0,0-12,168}
                        android.support.v7.widget.v{b8fd4eb VFED..CL ... 12,0-156,168 #7f1101a5 app:id/tab_switcher_button}
                        android.widget.FrameLayout{7df7248 V.E..... ... 156,0-282,168 #7f11024c app:id/menu_button_wrapper}
                          org.chromium.chrome.browser.widget.TintedImageButton{aa5c8e1 VFED..C. ... 0,0-126,168 #7f11011c app:id/menu_button}
                          android.support.v7.widget.x{ad14606 I.ED.... ... 52,78-100,126 #7f11024d app:id/menu_badge}
                    android.support.v7.widget.x{d14d4c7 V.ED.... ... 0,168-1080,198 #7f110110 app:id/toolbar_shadow}
                    android.view.ViewStub{39d6af4 G.E..... ... 0,0-0,0 #7f110111 app:id/find_toolbar_stub}
                    android.view.ViewStub{d55121d G.E..... ... 0,0-0,0 #7f110113 app:id/find_toolbar_tablet_stub}
                  org.chromium.chrome.browser.widget.ToolbarProgressBar{82bbc92 I.ED.... ... 0,162-1080,168 #7f11011d app:id/progress}
                android.view.ViewStub{8fff663 G.E..... ... 0,0-0,0 #7f1101b5 app:id/empty_container_stub}
                android.view.View{5a04260 V.ED.... ... 0,1704-0,1704 #7f1101b6 app:id/menu_anchor_stub}
              android.support.v7.internal.widget.ViewStubCompat{fb5b319 G.E..... ... 0,0-0,0 #7f11009a app:id/action_mode_bar_stub}
        android.view.View{b450fde V.ED.... ... 0,0-1080,72 #102002f android:id/statusBarBackground}
        android.view.View{af195bf V.ED.... ... 0,1776-1080,1920 #1020030 android:id/navigationBarBackground}
```

### Dialog

```
TASK com.chrome.dev id=163
  ACTIVITY com.android.vending/com.google.android.finsky.activities.InlineAppDetailsDialog dc65b9d pid=19054
    Local FragmentActivity d549626 State:
      mCreated=truemResumed=true mStopped=false mReallyStopped=false
      mLoadersStarted=true
    Active Fragments in 9bfedcf:
      #0: InlineAppDetailsFragment{e660488 #0 id=0x7f1000e2}
        mFragmentId=#7f1000e2 mContainerId=#7f1000e2 mTag=null
        mState=5 mIndex=0 mWho=android:fragment:0 mBackStackNesting=0
        mAdded=true mRemoving=false mResumed=true mFromLayout=false mInLayout=false
        mHidden=false mDetached=false mMenuVisible=true mHasMenu=false
        mRetainInstance=false mRetaining=false mUserVisibleHint=true
        mFragmentManager=FragmentManager{9bfedcf in HostCallbacks{e47835c}}
        mHost=android.support.v4.app.FragmentActivity$HostCallbacks@e47835c
        mArguments=Bundle[{finsky.PageFragment.dfeAccount=okanoshinobu8@gmail.com}]
        mContainer=android.widget.FrameLayout{3a12665 V.E...... ......ID 0,0-924,1423 #7f1000e2 app:id/content_frame}
        mView=com.google.android.finsky.layout.ContentFrame{c6e4f3a V.E...... ......ID 0,0-924,1423}
        mInnerView=com.google.android.finsky.layout.ContentFrame{c6e4f3a V.E...... ......ID 0,0-924,1423}
        Child FragmentManager{7f797eb in InlineAppDetailsFragment{e660488}}:
          FragmentManager misc state:
            mHost=android.support.v4.app.FragmentActivity$HostCallbacks@e47835c
            mContainer=android.support.v4.app.Fragment$1@f777948
            mParent=InlineAppDetailsFragment{e660488 #0 id=0x7f1000e2}
            mCurState=5 mStateSaved=false mDestroyed=false
    Added Fragments:
      #0: InlineAppDetailsFragment{e660488 #0 id=0x7f1000e2}
    FragmentManager misc state:
      mHost=android.support.v4.app.FragmentActivity$HostCallbacks@e47835c
      mContainer=android.support.v4.app.FragmentActivity$HostCallbacks@e47835c
      mCurState=5 mStateSaved=false mDestroyed=false
    View Hierarchy:
      com.android.internal.policy.PhoneWindow$DecorView{282c3e1 V.E..... ... 0,0-1020,1519}
        android.widget.LinearLayout{a622506 V.E..... ... 48,48-972,1471}
          android.view.ViewStub{bb5c7c7 G.E..... ... 0,0-0,0 #10203ab android:id/action_mode_bar_stub}
          android.widget.FrameLayout{a2ee1f4 V.E..... ... 0,0-924,1423}
            android.support.v7.internal.widget.FitWindowsFrameLayout{586bd1d V.E..... ... 0,0-924,1423 #7f1000b7 app:id/action_bar_root}
              android.support.v7.internal.widget.ContentFrameLayout{96b8b92 V.E..... ... 0,0-924,1423 #1020002 android:id/content}
                android.widget.FrameLayout{3a12665 V.E..... ... 0,0-924,1423 #7f1000e2 app:id/content_frame}
                  android.widget.RelativeLayout{c3d1963 G.E..... ... 0,0-900,582 #7f10010b app:id/placeholder_loading}
                    android.widget.ProgressBar{9522960 V.ED.... ... 378,219-522,363}
                  com.google.android.finsky.layout.SpacerHeightAwareFrameLayout{d70e19 G.E..... ... 0,0-0,0 #7f10010c app:id/placeholder_error}
                    android.widget.LinearLayout{232cede V.E..... ... 0,0-0,0}
                      android.support.v7.widget.AppCompatTextView{85de8bf V.ED.... ... 0,0-0,0 #7f10010a app:id/error_msg}
                      android.support.v7.widget.AppCompatButton{fa07b8c VFED..C. ... 0,0-0,0 #7f1001da app:id/retry_button}
                  com.google.android.finsky.layout.ContentFrame{c6e4f3a V.E..... ... 0,0-924,1423}
                    android.widget.RelativeLayout{74172d5 G.E..... ... 0,0-900,582 #7f100119 app:id/loading_indicator}
                      android.widget.ProgressBar{d98faea V.ED.... ... 378,219-522,363}
                    com.google.android.finsky.layout.SpacerHeightAwareFrameLayout{19251db G.E..... ... 0,0-0,0 #7f10031e app:id/page_error_indicator}
                      android.widget.LinearLayout{a9fc478 V.E..... ... 0,0-0,0}
                        android.support.v7.widget.AppCompatTextView{b36751 V.ED.... ... 0,0-0,0 #7f10010a app:id/error_msg}
                        android.support.v7.widget.AppCompatButton{f83dbb6 VFED..C. ... 0,0-0,0 #7f1001da app:id/retry_button}
                    com.google.android.finsky.layout.ContentFrame{cda30b7 V.E..... ... 0,0-924,1423 #7f100242 app:id/page_content}
                      android.widget.RelativeLayout{848b024 G.E..... ... 0,0-0,0 #7f100119 app:id/loading_indicator}
                        android.widget.ProgressBar{c76278d V.ED.... ... 0,0-0,0}
                      com.google.android.finsky.layout.SpacerHeightAwareFrameLayout{269fd42 G.E..... ... 0,0-0,0 #7f10031e app:id/page_error_indicator}
                        android.widget.LinearLayout{5572153 V.E..... ... 0,0-0,0}
                          android.support.v7.widget.AppCompatTextView{b72aa90 V.ED.... ... 0,0-0,0 #7f10010a app:id/error_msg}
                          android.support.v7.widget.AppCompatButton{b2aaf89 VFED..C. ... 0,0-0,0 #7f1001da app:id/retry_button}
                      android.widget.ScrollView{f9eab8e VFED.V.. ... 0,0-924,1423}
                        com.google.android.finsky.layout.DetailsSectionStack{ca87faf V.ED.... ... 0,0-924,1423}
                          com.google.android.finsky.layout.WarningMessageSection{affdfbc GFE..... ... 0,0-0,0 #7f1001a7 app:id/warning_message_panel}
                            android.support.v7.widget.AppCompatImageView{c85bb45 V.ED.... ... 0,0-0,0 #7f1001a8 app:id/details_warning_info_icon}
                            android.widget.LinearLayout{5df29a V.E..... ... 0,0-0,0}
                              android.support.v7.widget.AppCompatTextView{50767cb V.ED.... ... 0,0-0,0 #7f1001a9 app:id/details_warning_info_first_line}
                              android.support.v7.widget.AppCompatTextView{7c93ba8 V.ED.... ... 0,0-0,0 #7f1001aa app:id/details_warning_info_second_line}
                          android.widget.LinearLayout{ccbc6c1 V.E..... ... 0,0-924,467 #7f100145 app:id/item_details_panel}
                            android.widget.RelativeLayout{3989e66 V.E..... ... 48,48-876,317}
                              com.google.android.play.layout.PlayCardThumbnail{122b5a7 V.E..... ... 0,0-192,192 #7f100194 app:id/title_thumbnail_frame}
                                com.google.android.finsky.layout.DocImageView{54a6a54 V.ED.... ... 0,0-192,192 #7f1000ff app:id/title_thumbnail}
                              com.google.android.finsky.layout.DetailsSummaryWishlistView{e0d0dfd GFED.... ... 0,0-0,0 #7f100182 app:id/title_wishlist_button}
                              android.widget.LinearLayout{4803af2 V.E..... ... 192,0-828,269}
                                com.google.android.play.layout.PlayTextView{5bb0543 V.ED.... .S. 48,0-636,152 #7f1000fe app:id/title_title}
                                android.widget.LinearLayout{10dd7c0 V.E..... ... 48,152-636,215 #7f100183 app:id/title_creator_panel}
                                  com.google.android.finsky.layout.DecoratedTextView{9218cf9 V.ED.... ... 0,0-193,57 #7f100184 app:id/title_creator}
                                android.widget.LinearLayout{dd3143e V.E..... ... 48,215-636,269 #7f100186 app:id/title_content_rating_panel}
                                  com.google.android.play.image.FifeImageView{8feb29f V.ED.... ... 0,0-50,48 #7f100187 app:id/title_content_rating_icon}
                                  com.google.android.finsky.layout.DecoratedTextView{4d8afec G.ED.... ... 0,0-0,0 #7f100188 app:id/title_content_rating}
                            android.widget.RelativeLayout{264ffb5 V.E..... ... 48,341-876,443}
                              android.widget.LinearLayout{5e8364a V.E..... ... 0,53-241,102}
                                android.widget.LinearLayout{ba5d9bb V.E..... ... 0,0-241,49}
                                  com.google.android.play.layout.StarRatingBar{f96ded8 V.ED.... ... 0,12-150,36 #7f100260 app:id/star_rating_bar}
                                  android.support.v7.widget.AppCompatTextView{e32e231 V.ED.... ... 150,0-208,49 #7f100261 app:id/rating_count}
                                  android.support.v7.widget.AppCompatImageView{f7b6d16 V.ED.... ... 217,12-241,36}
                                android.support.v7.widget.AppCompatTextView{7ce5697 G.ED.... ... 0,0-0,0 #7f100257 app:id/title_extra_label_install_notes}
                                android.support.v7.widget.AppCompatTextView{1071084 G.ED.... ... 0,0-0,0 #7f100258 app:id/title_extra_label_in_app_purchase}
                              android.widget.FrameLayout{122706d V.E..... ... 468,0-828,102}
                                com.google.android.play.layout.PlayActionButton{b3944a2 VFED..C. ... 0,0-360,102 #7f100172 app:id/buy_button}
                                com.google.android.play.layout.PlayActionButton{197c533 GFED..C. ... 0,0-0,0 #7f10016e app:id/launch_button}
                          com.google.android.play.layout.PlayTextView{426b0f0 V.ED.... ... 0,467-924,730 #7f100252 app:id/short_description_panel}
                          com.google.android.finsky.layout.ScreenshotGallery{802a669 V.E..... ... 0,730-924,1270 #7f100253 app:id/screenshots_panel}
                            android.view.View{60b08ee V.ED.... ... 0,0-924,540 #7f100180 app:id/strip_background}
                            com.google.android.finsky.layout.HorizontalStrip{57f818f VFED.... ... 0,0-924,540 #7f100181 app:id/strip}
                              com.google.android.finsky.layout.AppScreenshot{45dec1c VFE...C. ... 0,0-304,540}
                                android.support.v7.widget.AppCompatImageView{3964025 V.ED.... ... 0,0-304,540 #7f1000f7 app:id/screenshot}
                                android.support.v7.widget.AppCompatImageView{22c5fa G.ED.... ... 0,0-0,0 #7f1000f8 app:id/download_icon}
                                android.widget.ProgressBar{7ca7ab G.ED.... ... 0,0-0,0 #7f1000f9 app:id/screenshot_small_progress_bar}
                                android.view.View{96bae08 V.ED.... ... 0,0-304,540 #7f1000fa app:id/accessibility_overlay}
                              com.google.android.finsky.layout.AppScreenshot{40fb9a1 VFE...C. ... 316,0-620,540}
                                android.support.v7.widget.AppCompatImageView{8c747c6 V.ED.... ... 0,0-304,540 #7f1000f7 app:id/screenshot}
                                android.support.v7.widget.AppCompatImageView{ddc1387 G.ED.... ... 0,0-0,0 #7f1000f8 app:id/download_icon}
                                android.widget.ProgressBar{611a2b4 G.ED.... ... 0,0-0,0 #7f1000f9 app:id/screenshot_small_progress_bar}
                                android.view.View{4d4edd V.ED.... ... 0,0-304,540 #7f1000fa app:id/accessibility_overlay}
                              com.google.android.finsky.layout.AppScreenshot{ae01a52 VFE...C. ... 632,0-970,540}
                                android.support.v7.widget.AppCompatImageView{6dc6123 V.ED.... ... 0,0-338,540 #7f1000f7 app:id/screenshot}
                                android.support.v7.widget.AppCompatImageView{5803620 G.ED.... ... 0,0-0,0 #7f1000f8 app:id/download_icon}
                                android.widget.ProgressBar{4d4fbd9 G.ED.... ... 0,0-0,0 #7f1000f9 app:id/screenshot_small_progress_bar}
                                android.view.View{641899e V.ED.... ... 0,0-338,540 #7f1000fa app:id/accessibility_overlay}
                              com.google.android.finsky.layout.AppScreenshot{9ec7f VFE...C. ... 982,0-1320,540}
                                android.support.v7.widget.AppCompatImageView{382944c V.ED.... ... 0,0-338,540 #7f1000f7 app:id/screenshot}
                                android.support.v7.widget.AppCompatImageView{6907c95 G.ED.... ... 0,0-0,0 #7f1000f8 app:id/download_icon}
                                android.widget.ProgressBar{1b8a1aa G.ED.... ... 0,0-0,0 #7f1000f9 app:id/screenshot_small_progress_bar}
                                android.view.View{5ad19b V.ED.... ... 0,0-338,540 #7f1000fa app:id/accessibility_overlay}
                            android.widget.RelativeLayout{b6aa938 G.E..... ... 0,0-924,540 #7f100119 app:id/loading_indicator}
                              android.widget.ProgressBar{5494d11 V.ED.... ... 390,198-534,342}
                            android.widget.LinearLayout{1d72e76 G.E..... ... 0,0-0,0 #7f1001db app:id/error_indicator}
                              android.support.v7.widget.AppCompatTextView{e0aec77 V.ED.... ... 0,0-0,0 #7f10010a app:id/error_msg}
                              android.support.v7.widget.AppCompatButton{9bd20e4 VFED..C. ... 0,0-0,0 #7f1001da app:id/retry_button}
                          android.widget.RelativeLayout{9e4a94d V.E..... ... 0,1270-924,1423 #7f1000e0 app:id/footer}
                            android.support.v7.widget.AppCompatTextView{7fbc02 VFED..C. ... 534,24-876,129 #7f100255 app:id/more_details}
                            android.support.v7.widget.AppCompatImageView{d37d913 V.ED.... ... 48,40-348,112 #7f100256 app:id/logo}
              android.support.v7.internal.widget.ViewStubCompat{c9d6750 G.E..... ... 0,0-0,0 #7f1000b8 app:id/action_mode_bar_stub}
```


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

* Chrome Custom Tabs - 7

* Intent and Remote Debugging - 3

* Web App Manifest - 5
 * Service Workers
  * Push Notifications
  * Background Sync
  * こういう使い方もできるよー的な感じで

* App Stream ※1 - 5
 * これまではGoogle Playに飛ばされてアプリをダウンロードしないといけなかった上に、起動直後に検索ワードに合致したコンテンツが出てくる訳では無かったので、ユーザー体験は雲泥の差

* ChromeとAndroidの今後について(個人的主観) - 3
 * WebViewの変化
 * Progressive Web Apps

7 + 3 + 5 + 5 + 3 = 23

# Chrome Custom Tabs can replace the WebView?



対象者：
* WebコンテンツとAndroidアプリの両方を運用している会社 or 人
* ChromeとAndroidの親和性を有効的に活用したい人
* アプリ内でWebViewを使っている人 or 使いたいと思ってる人

※1 参考:http://insidesearch.blogspot.ca/2015/11/new-ways-to-find-and-stream-app-content.html
```
