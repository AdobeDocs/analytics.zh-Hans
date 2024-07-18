---
title: trackingServerSecure
description: 确定在 HTTPS 页面上发送图像请求的位置。
feature: Variables
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 66%

---

# trackingServerSecure

Adobe 通过接收访客生成的图像请求来收集您网站上的数据。`trackingServerSecure` 变量可确定通过 HTTPS 发送图像请求的位置。它还可确定存储访客 Cookie 的位置。如果未正确定义此变量，则您的实施可能会丢失数据。

>[!WARNING]
>
>更改此值会使 AppMeasurement 在其他位置查找 Cookie。当在新位置设置访客 Cookie 时，报表中的独特访客计数可能会暂时激增。

## 使用Web SDK扩展的Edge域

Web SDK使用[!UICONTROL Edge域]处理跟踪服务器和安全跟踪服务器。 在配置Web SDK扩展时，您可以设置所需的[!UICONTROL Edge域]值。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL Adobe Experience Platform Web SDK]下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 设置所需的&#x200B;**[!UICONTROL Edge域]**&#x200B;文本字段。

有关详细信息，请参阅Web SDK文档中的[配置Adobe Experience Platform Web SDK扩展](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=zh-Hans)。

>[!TIP]
>
>如果您的组织从AppMeasurement或Analytics扩展实现移至Web SDK，则此字段可以使用`trackingServerSecure`（或`trackingServer`）中包含的相同值。

## Edge域手动实施Web SDK

使用[`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans)配置SDK。 字段是一个字符串，可确定要将数据发送到的域。

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## 使用Adobe Analytics扩展的SSL Tracking Server

[!UICONTROL SSL 跟踪服务器]是配置 Adobe Analytics 扩展时位于[!UICONTROL 常规]折叠面板下的字段。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;]**配置**[!UICONTROL &#x200B;按钮。
4. 展开[!UICONTROL 常规]折叠面板，这会显示[!UICONTROL SSL 跟踪服务器]字段。

如果此字段留空，则默认为 [`trackingServer`](trackingserver.md) 变量中的值。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.trackingServerSecure

`s.trackingServerSecure` 变量是一个字符串，其中包含发送图像请求的位置。它几乎始终是您网站的子域。浏览器中的现代隐私权惯例通常会使第三方 Cookie 变得不可靠。如果此变量为空，则会使用 `s.trackingServer` 变量中的值。

此变量的值几乎始终是第一方域，例如 `data.example.com`。有关第一方 Cookie 流程的更多信息，请参阅《核心服务用户指南》中的 [Experience Cloud 中的第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=zh-Hans)。

最初配置第一方 Cookie 实施的人员还会定义所使用的域和子域。例如：

```js
s.trackingServerSecure = "data.example.com";
```

CNAME 记录通常指向 `data.adobedc.net`、`sc.adobedc.net` 或 `2o7.net` 上的子域。
