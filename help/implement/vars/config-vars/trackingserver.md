---
title: trackingServer
description: 确定发送图像请求的位置。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackingServer

Adobe通过接收访客生成的图像请求来收集您网站上的数据。 该变 `trackingServer` 量确定发送图像请求的位置。 如果未正确定义此变量，则您的实施可能会丢失数据。

> [!IMPORTANT] 更改此值可使AppMeasurement在其他位置查找cookie。 当在新位置设置访客Cookie时，唯一访客计数可能会临时在报告中尖峰。

## Adobe Experience Platform Launch中的跟踪服务器

跟踪服务器是配置Adobe Analytics扩展时 [!UICONTROL “常规] ”折叠面板下的字段。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“ [!UICONTROL 常规] ”折叠面板 [!UICONTROL ，该面板显示“跟] 踪服务器”字段。

如果此字段留空，则默认为 `[rsid].112.2o7.net`。

## AppMeasurement中的s.trackingServer和启动自定义代码编辑器

变 `s.trackingServer` 量是一个字符串，其中包含发送数据的位置。

> [!TIP] 某些实现将数据指向 `2o7.net`。 虽然这是一个有效的数据收集域，但它不使用区域数据收集。 使用的实 `2o7.net` 现会看到略高的图像请求响应时间。

## 确定trackingServer的值

此变量的值取决于您是使用第一方Cookie还是第三方Cookie。 Adobe强烈建议在您的实施中使用第一方Cookie。

### 第一方 Cookie

如果您使用第一方Cookie实施，则您组织中的某人可能已经完成了第一方Cookie过程。 有关 [第一方Cookie流程的更多信息，请参阅Experience cloud中](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) “核心服务”用户指南中的第一方Cookie。

最初配置第一方Cookie实现的个人还定义所使用的域和子域。 例如：

```js
s.trackingServer = "data.example.com";
```

通常，CNAME记录已设置并指向 `sc.omtrdc.net`。 该域也 `2o7.net` 是有效的CNAME目标，主要用于Adobe Analytics的早期版本。

### 第三方Cookie

> [!TIP] 现代浏览器中增加的隐私权惯例使第三方Cookie变得不那么可靠。 Adobe建议遵循第一方Cookie工作流程。

如果您使用第三方Cookie实现，则其值 `trackingServer` 为的子域 `sc.omtrdc.net`。 例如：

```js
s.trackingServer = "example.sc.omtrdc.net";
```

挑选您的组织特有的子域，而使用Adobe Analytics的其他组织不太可能挑选出该子域。 确保组织中的所有实施都使用相同的跟踪服务器。 在解决方案设计文档中保留这些信息 [会很有帮助](../../prepare/solution-design.md)。
