---
title: 有关实施的常见问题解答
description: 有关实施的常见问题，以及指向更多信息的链接。
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 71%

---

# 有关 Analytics 实施的常见问题解答

有关实施的常见问题，以及指向更多信息的链接。

## Experience Cloud 访客 ID 与 Analytics 访客 ID 之间有何区别？

Identity Service 可分配一个唯一的永久标识符，该标识符可以在 Experience Cloud 中的其他解决方案之间共享。而 Analytics 访客 ID 仅供 Analytics 使用。Adobe 建议在您的实施中使用 Experience Cloud 访客 ID 服务。

## 我该如何实施心率视频跟踪？

请参阅[在 Adobe Analytics 中测量音频和视频](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html)。

## Adobe 的服务中断会影响库性能吗？

不会。由于 JavaScript 文件并非是在 Adobe 服务器上托管，因此 Adobe 的故障将不会影响 AppMeasurement 库。如果您使用 Adobe Experience Platform Launch，则 JavaScript 文件由 Akamai 托管，或者托管在由贵组织确定的服务器位置上。

## 将来自浏览器的数据发送至 Adobe 服务会降低性能吗？

AppMeasurement 会在 HTML 页面内创建一个图像对象，浏览器随后从 Adobe 数据收集服务器请求该图像对象。如果数据收集服务器变得缓慢或无反应，则处理该请求的线程将被延迟，直至图像返回或发生超时。因为浏览器会通过多线程处理图像，而 Adobe 故障仅占用一个线程，其他线程继续工作，因此对页面加载时间会造成一定的影响，但这个影响极小。

## 如何使 Analytics 实施失效或将其移除？

有时，组织会因合同到期而想要移除实施，或想要减少服务器调用的数量。

* **使用 Launch 的实施**：在“[!UICONTROL 扩展]”选项卡中禁用或卸载 Adobe Analytics 扩展，然后发布。
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


## 我通过代码分析器运行AppMeasurement，并将其`Math.random()`的用法标记为潜在的安全风险。 是否将`Math.random()`用于任何敏感数据？

否。使用`Math.random()`的数字不用于掩盖、发送或接收任何敏感数据。 发送到Adobe数据收集服务器的数据依赖于基础HTTPS连接的安全性。<!-- AN-173590 -->

AppMeasurement在以下三个关键方面使用`Math.random()` :

* **采样**:根据您的实施，可能只会为网站的一小部分访客收集一些信息。`Math.random()` 用于确定给定访客是否应发送数据。大多数实施都不使用采样。
* **回退访客ID**:如果无法从Cookie检索访客ID，则会生成一个随机的访客ID。AppMeasurement的这一部分对`Math.random()`使用两个调用。
* **缓存嵌套**:图像请求URL的末尾会添加一个随机数，以帮助防止浏览器缓存。
