---
title: 2021，该把你的系统换成Linux了
image: /images/try-linux.jpg
imageMeta:
  attribution:
  attributionLink:
featured: true
authors:
  - wenfeng
date: Sun Feb 07 2021 18:08:00 GMT+0800 (CST)
tags:
  - try-linux
---

自从大学开始学习计算机以来，就对Linux各种大佬滚烫的人生无比羡慕，从刚入坑被各种crash折磨，找方案，发issue, 到现在充分磨合，各种软文劝别人换系统。不得不说，Linux确实陪伴了我整个青春，我也见证了Linux用户体验飞速提升的10年。在程序员日常工作中，Linux带来的简洁，低占用，高生产力，已经全面碾压Windows系，Mac系了

## 问题： Linux系统无法使用各种Windows App?

例如： WxWork（企业微信）

## 解决方案： Wine + Winetricks

1. 安装

```
# 官网自取
bash-5.0$ curl WxWork官方包.exe
# Next...  注：咱路径别带空格阿
bash-5.0$ wine WxWork官方包.exe
```

2. 问题及解决方案

```
### 解决中文乱码
# 下载字体
bash-5.0$ curl SimSun.ttf下载链接 > ~/.wine/drive_c/windows/Fonts/
# 注册字体
bash-5.0$ cat zh.reg 
REGEDIT4
[HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\FontSubstitutes]
"Arial"="simsun"
"Arial CE,238"="simsun"
"Arial CYR,204"="simsun"
"Arial Greek,161"="simsun"
"Arial TUR,162"="simsun"
"Courier New"="simsun"
"Courier New CE,238"="simsun"
"Courier New CYR,204"="simsun"
"Courier New Greek,161"="simsun"
"Courier New TUR,162"="simsun"
"FixedSys"="simsun"
"Helv"="simsun"
"Helvetica"="simsun"
"MS Sans Serif"="simsun"
"MS Shell Dlg"="simsun"
"MS Shell Dlg 2"="simsun"
"System"="simsun"
"Tahoma"="simsun"
"Times"="simsun"
"Times New Roman CE,238"="simsun"
"Times New Roman CYR,204"="simsun"
"Times New Roman Greek,161"="simsun"
"Times New Roman TUR,162"="simsun" 
"Tms Rmn"="simsun"

# 有空搞到winetricks中，造福苍生
bash-5.0$ regedit zh.reg

### 解决看不见输入框文字，发送消息崩溃
# 下载慢至少挂个VPN吧
bash-5.0$ winetricks riched20
```

## 上效果图

![效果图](/images/wxwork-wine.jpg)

## 吃上瓜的，别忘记点赞
