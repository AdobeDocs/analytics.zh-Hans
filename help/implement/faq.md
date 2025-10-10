---
title: 有关实施的常见问题解答
description: 有关实施的常见问题，以及指向更多信息的链接。
feature: Implementation Basics
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
role: Admin, Developer, Leader, User
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 100%

---

# 有关 Analytics 实施的常见问题解答

有关实施的常见问题，以及指向更多信息的链接。

## Experience Cloud 访客 ID 与 Analytics 访客 ID 之间有何区别？

身份标识服务可分配一个唯一的永久标识符，该标识符可以在 Experience Cloud 中的其他解决方案之间共享。而 Analytics 访客 ID 仅供 Analytics 使用。Adobe 建议在您的实施中使用 Experience Cloud 访客 ID 服务。

## 我该如何实施心率视频跟踪？

请参阅[在 Adobe Analytics 中测量音频和视频](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=zh-Hans)。

## Adobe 的服务中断会影响库性能吗？

不会。由于 JavaScript 文件并非是在 Adobe 服务器上托管，因此 Adobe 的故障将不会影响 AppMeasurement 库。如果您使用 Adobe Experience Platform 中的标记，则 JavaScript 文件由 Akamai 托管，或者托管在由贵组织确定的服务器位置上。

## 将来自浏览器的数据发送至 Adobe 服务会降低性能吗？

AppMeasurement 会在 HTML 页面内创建一个图像对象，浏览器随后从 Adobe 数据收集服务器请求该图像对象。如果数据收集服务器变得缓慢或无反应，则处理该请求的线程将被延迟，直至图像返回或发生超时。因为浏览器会通过多线程处理图像，而 Adobe 故障仅占用一个线程，其他线程继续工作，因此对页面加载时间会造成一定的影响，但这个影响极小。

## 如何使 Analytics 实施失效或将其移除？

有时，组织会因合同到期而想要移除实施，或想要减少服务器调用的数量。

* **使用 Adobe Experience Platform 数据收集实施**：在[!UICONTROL 扩展]选项卡中禁用或卸载适用的 Adobe Analytics、Web SDK 或移动 SDK 扩展，然后发布。
* **旧版 AppMeasurement 实施**：使用以下代码行替换 `s_code.js` 文件的全部内容：

```js
var s = new Object();
```

>[!WARNING]
>
>请勿：
>
>* 将报表包更改为无效值，因为它会在 Adobe 服务器上产生不必要的负载。
>* 同时移除 `s_code.js` 文件，除非您还移除了每个页面上对该文件的所有引用。
>* 更改 `trackingServer` 变量使其指向 Adobe 之外的服务器。AppMeasurement 仍会发送图像请求，这会返回 404 错误。

## 我通过代码分析器运行了 AppMeasurement，它将其 `Math.random()` 使用行为标记为潜在安全风险。`Math.random()` 是否用于任何敏感数据？

否。使用 `Math.random()` 的数字不用于屏蔽、发送或接收任何敏感数据。发送到 Adobe 数据收集服务器的数据依赖于基础 HTTPS 连接的安全性。<!-- AN-173590 -->

AppMeasurement 在三个关键领域使用 `Math.random()`：

* **取样**：根据您的实施，可能只会收集您网站的一小部分访客户的一些信息。`Math.random()` 用于确定给定访客是否应该发送数据。大多数实施不使用取样。
* **后备访客 ID**：如果无法从 Cookie 中检索到访客 ID，则会生成随机访客 ID。AppMeasurement 的这部分内容使用两个 `Math.random()` 调用。
* **缓存无效**：在图像请求 URL 末尾添加一个随机数以帮助阻止浏览器缓存。
