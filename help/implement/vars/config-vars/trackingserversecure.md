---
title: trackingServerSecure
description: 确定在 HTTPS 页面上发送图像请求的位置。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# trackingServerSecure

Adobe 通过接收访客生成的图像请求来收集您网站上的数据。`trackingServerSecure` 变量可确定通过 HTTPS 发送图像请求的位置。它还可确定存储访客 Cookie 的位置。如果未正确定义此变量，则您的实施可能会丢失数据。

>[!IMPORTANT] 更改此值会使 AppMeasurement 在其他位置查找 Cookie。当在新位置设置访客 Cookie 时，报表中的独特访客计数可能会暂时激增。

## Adobe Experience Platform Launch 中的“SSL 跟踪服务器”

[!UICONTROL SSL Tracking Server] 是配置Adobe Analytics扩展 [!UICONTROL General] 时accordion下的字段。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展开可 [!UICONTROL General] 折叠面板，以显示 [!UICONTROL SSL Tracking Server] 字段。

如果此字段留空，则默认为 [`trackingServer`](trackingserver.md) 变量中的值。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.trackingServerSecure

`s.trackingServerSecure` 变量是一个字符串，其中包含发送图像请求的位置。它几乎始终是您网站的子域。浏览器中的现代隐私权惯例通常会使第三方 Cookie 变得不可靠。如果此变量为空，则会使用 `s.trackingServer` 变量中的值。

此变量的值几乎始终是第一方域，例如 `data.example.com`。有关第一方 Cookie 流程的更多信息，请参阅核心服务用户指南中的 [Experience Cloud 中的第一方 Cookie](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/ec-cookies/cookies-first-party.html)。

最初配置第一方 Cookie 实施的人员还会定义所使用的域和子域。例如：

```js
s.trackingServerSecure = "data.example.com";
```

CNAME 记录通常指向 `ssl.d1.sc.omtrdc.net` 上的子域。
