# ADB命令卸载内置软件

<br>

### 一、下载`android_sdk/platform-tools`

- 这是`Android`官网的调试`SDK`，支持很多功能，不仅仅局限于`adb`命令。
- [官网SDK下载地址](https://developer.android.com/studio/command-line/adb)   `需要翻墙`
- [蓝奏云SDK下载地址](https://dashan3.lanzoui.com/i76VVpjnylc)   `最新`
- [官网三星驱动下载地址](https://developer.samsung.com/mobile/android-usb-driver.html)
- [蓝奏云三星驱动下载地址 ](https://dashan3.lanzoui.com/ipInbpl4dsb)   `最新`

<br>

<br>

<br>

### 二、解压文件到任意位置，推荐解压到`D：`盘

![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_1.png)

![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_2.png)

<br>

<br>

<br>

### 三、配置环境变量

![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_3.png)

![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_4.png)![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_5.png)![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_6.png)![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_7.png)![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_8.png)![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_9.png)![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_10.png)![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_11.png)

<br><br>

```shell
打开cmd窗口输入：

//查看adb版本 
adb version

//看到下图说明你的环境变量已经配置好了，可以开始使用adb命令来调试手机
```

![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_12.png)

<br><br>

```
连接电脑：  
1.手机必须进入开发者模式。 
2.手机必须打开USB调试模式（当然卸载完成后这些都是可以关闭的）。 
3.电脑必须安装手机的驱动。
	手机用数据线链接电脑，如果手机有弹窗则一直点击【是✓】就好了。  有一个弹窗一定要注意，【是否允许该电脑调试手机】点击【一直允许】 
4.手机连接电脑完成后关闭cmd窗口，重新用管理员模式打开cmd窗
```

<br>

```shell
卸载命令： 
//首先需要执行一条命令，进入交互模式。 
adb shell

//保留数据卸载软件命令 
pm uninstall -k --user 0 软件包名

//不保留数据卸载软件命令（推荐) 
pm uninstall --user 0 软件包名

//完整命令如：卸载搜狗输入法三星版 
pm uninstall -k --user 0 com.sohu.inputmethod.sogou.samsung  


软件包名：  
//三星游戏中心推荐卸载 com.samsung.android.game.gamehome 
//三星语音输入法推荐卸载 com.samsung.android.svoiceime 
//搜狗输入法三星版推荐卸载 com.sohu.inputmethod.sogou.samsung   

//ADB命令适用于所有安卓手机，不要问我华为可不可以，因为我也不知道！！！
```

![img](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Uninstall_Images/image_13.png) 

<br>

<br>

##### 下面分享一些可以卸载的内置应用：

```
pm uninstall --user 0 com.sohu.inputmethod.sogou.samsung
搜狗输入法三星版

pm uninstall --user 0 com.samsung.android.svoiceime
三星语音输入法

pm uninstall --user 0 com.samsung.android.game.gamehome
三星游戏中心

pm uninstall --user 0 com.samsung.android.app.searchwidget
桌面搜索

pm uninstall --user 0 com.sec.android.yellowpage
黄页

pm uninstall --user 0 com.samsung.android.app.galaxyfinder
搜索

pm uninstall --user 0 com.google.android.apps.pdfviewer
Google PDF查看器

pm uninstall --user 0 com.samsung.android.app.spage
Bixby 主页

pm uninstall --user 0 com.samsung.hongbaoassistant
红包助手

pm uninstall --user 0 com.samsung.android.arzone
AR 区

pm uninstall --user 0 com.samsung.android.video
视频播放器

pm uninstall --user 0 com.sec.android.app.sbrowser
三星浏览器

pm uninstall --user 0 com.samsung.android.aremojieditor
动态萌拍编辑器

pm uninstall --user 0 com.samsung.android.aremoji
动态萌拍

pm uninstall --user 0 com.samsung.android.livestickers
装饰图片

pm uninstall --user 0 com.samsung.app.highlightplayer
创建电影

pm uninstall --user 0 com.sec.android.app.vepreload
视频编辑器

pm uninstall --user 0 com.samsung.app.newtrim
视频剪辑器

pm uninstall --user 0 com.samsung.android.ardrawing
AR 涂鸦

pm uninstall --user 0 com.sec.android.app.shealth
三星健康

pm uninstall --user 0 com.sec.android.app.ve.vebgm
选择背景音乐

pm uninstall --user 0 com.tencent.mm.wxa.sce
微信小程序

pm uninstall --user 0 com.sec.android.mimage.avatarstickers
动态萌拍贴纸

pm uninstall --user 0 com.samsung.android.app.simplesharing
链接分享

pm uninstall --user 0 com.samsung.android.themestore
主题商店

pm uninstall --user 0 com.samsung.android.app.tips
提示

pm uninstall --user 0 com.sec.android.app.magnifier
放大镜

pm uninstall --user 0 com.samsung.android.oneconnect
Samsung Connect

pm uninstall --user 0 com.samsung.android.scloud
三星云

pm uninstall --user 0 com.samsung.android.visionintelligence
Bixby 视觉

pm uninstall --user 0 com.sec.android.app.kidshome
Samsung Kids

pm uninstall --user 0 com.samsung.android.bixbytouch
Bixby 识屏

pm uninstall --user 0 com.samsung.SMT
三星文字转语音引擎

pm uninstall --user 0 com.samsung.android.bixbyvision.framework
BixbyVision Framework

pm uninstall --user 0 com.sec.android.app.desktoplauncher
Samsung DeX 主屏幕

pm uninstall --user 0 com.samsung.desktopsystemui
Samsung DeX 系统 UI

pm uninstall --user 0 com.sec.android.desktopmode.uiservice
Samsung DeX

pm uninstall --user 0 com.sec.android.app.dexonpc
电脑版 DeX

pm uninstall --user 0 com.samsung.android.rubin.app
个性化服务

pm uninstall --user 0 com.google.ar.core
Google Play Services for AR

pm uninstall --user 0 com.google.audio.hearing.visualization.accessibility.scribe
实时转写和声音通知

pm uninstall --user 0 com.samsung.android.cmccbusinesshall
中国移动掌厅

pm uninstall --user 0 com.samsung.knox.securefolder
安全文件夹

pm uninstall --user 0 com.google.android.as
设备个性化服务
```

