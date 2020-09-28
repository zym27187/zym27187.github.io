---
title: "查看Android的appPackage和Activity的便捷方法"
categories: "技术"
time: 2019-7-22 17:09:01
preview_text: 最近在研究Appium的使用，在设置desired_caps百度到的便捷方法
tags: ["Appium"]
preview: https://i.loli.net/2019/08/06/KvP2RkjTQWAUzSH.png
---
1. 清除logcat内容，使用命令adb logcat -c

2. 启动logcat，使用命令adb logcat ActivityManager:I *:s

3. 启动要查看的程序，
![img1](https://img-blog.csdn.net/20171205113129051)
![img2](https://img-blog.csdn.net/20171205113129484)
    * **tips**:一般cmp=**appPackage**/**Activity**这样的结构出现，比如上述appPackage为"**com.cola.ui**",Activity为 ".**ColaBox**"