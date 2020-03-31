---
title: trackingServer
description: 确定发送图像请求的位置。
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# trackingServer

Adobe 通过接收访客生成的图像请求来收集您网站上的数据。`trackingServer` 变量可确定发送图像请求的位置。如果未正确定义此变量，则您的实施可能会丢失数据。

> [!IMPORTANT] 更改此值会使 AppMeasurement 在其他位置查找 Cookie。当在新位置设置访客 Cookie 时，报表中的独特访客计数可能会暂时激增。

## Adobe Experience Platform Launch 中的“跟踪服务器”

Tracking Server is a field under the [!UICONTROL General] accordion when configuring the Adobe Analytics extension.

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展开可 [!UICONTROL General] 折叠面板，以显示 [!UICONTROL Tracking Server] 字段。

如果此字段留空，则默认为 `[rsid].112.2o7.net`。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.trackingServer

`s.trackingServer` 变量是一个字符串，其中包含要发送数据的位置。

> [!TIP] 某些实施将数据指向 `2o7.net`。虽然这是一个有效的数据收集域，但它不使用区域数据收集。对于使用 `2o7.net` 的实施，其图像请求的响应时间会略有延长。

## 确定 trackingServer 的值

此变量的值取决于您是使用第一方 Cookie 还是第三方 Cookie。Adobe 强烈建议在您的实施中使用第一方 Cookie。

### 第一方 Cookie

如果您使用第一方 Cookie 实施，则表示贵组织中的某人可能已经完成了第一方 Cookie 流程。有关第一方 Cookie 流程的更多信息，请参阅核心服务用户指南中的 [Experience Cloud 中的第一方 Cookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html)。

最初配置第一方 Cookie 实施的人员还会定义所使用的域和子域。例如：

```js
s.trackingServer = "data.example.com";
```

通常，CNAME 记录会已设置并指向 `sc.omtrdc.net`。该域 `2o7.net` 也是有效的 CNAME 目标，主要在 Adobe Analytics 的早期版本中使用。

### 第三方 Cookie

> [!TIP] 现代浏览器中增加的隐私惯例使第三方 Cookie 变得不那么可靠。Adobe 建议遵循第一方 Cookie 工作流程。

如果您使用第三方 Cookie 实施，则 `trackingServer` 的值是 `sc.omtrdc.net` 的子域。例如：

```js
s.trackingServer = "example.sc.omtrdc.net";
```

选择贵组织独有而使用 Adobe Analytics 的其他组织不太可能选择的子域。确保贵组织中的所有实施都使用相同的跟踪服务器。在[解决方案设计文档](../../prepare/solution-design.md)中维护此信息可能会有所帮助。

> [!NOTE] 请勿使用任何深于的子域 `example.sc.omtrdc.net`。 例如， `custom.example.sc.omtrdc.net` 不是有效的跟踪服务器。
