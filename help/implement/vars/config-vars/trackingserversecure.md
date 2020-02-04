---
title: trackingServerSecure
description: 确定在HTTPS页面上发送图像请求的位置。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackingServerSecure

Adobe通过接收访客生成的图像请求来收集您网站上的数据。 该 `trackingServerSecure` 变量确定通过HTTPS发送图像请求的位置。 它还确定存储访客cookie的位置。 如果未正确定义此变量，则您的实施可能会丢失数据。

> [!IMPORTANT] 更改此值可使AppMeasurement在其他位置查找cookie。 当在新位置设置访客Cookie时，唯一访客计数可能会临时在报告中尖峰。

## Adobe Experience Platform Launch中的SSL跟踪服务器

[!UICONTROL SSL Tracking Server] （SSL跟踪服务器）是配置Adobe Analytics扩展时 [!UICONTROL General] accordion（常规折叠式）下的字段。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“ [!UICONTROL 常规] ”折叠面板 [!UICONTROL ，该面板显示“] SSL跟踪服务器”字段。

如果此字段留空，则默认为变量中的 `trackingServer` 值。

## s.trackingServerAppMeasurement中的S.trackingServerSecure和启动自定义代码编辑器

变量 `s.trackingServerSecure` 是一个字符串，其中包含发送图像请求的位置。 它几乎总是您网站的子域。 浏览器中的现代隐私权惯例通常会使第三方cookies不可靠。 如果此变量为空，则使用变量中的 `s.trackingServer` 值。

此变量的值几乎总是第一方域，例如 `data.example.com`。 有关 [第一方Cookie流程的更多信息，请参阅Experience cloud中](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) “核心服务”用户指南中的第一方Cookie。

最初配置第一方Cookie实现的个人还定义所使用的域和子域。 例如：

```js
s.trackingServerSecure = "data.example.com";
```

CNAME记录通常指向上的子域 `ssl.d1.sc.omtrdc.net`。
