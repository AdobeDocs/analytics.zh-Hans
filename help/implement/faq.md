---
title: 实施常见问题解答
description: 有关实施的常见问题，以及指向更多信息的链接。
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 67%

---


# 有关 Analytics 实施的常见问题解答

有关实施的常见问题，以及指向更多信息的链接。

## Experience Cloud 访客 ID 与 Analytics 访客 ID 之间有何区别？

Identity Service 可分配一个唯一的永久标识符，该标识符可以在 Experience Cloud 中的其他解决方案之间共享。而 Analytics 访客 ID 仅供 Analytics 使用。Adobe 建议在您的实施中使用 Experience Cloud 访客 ID 服务。

## 我该如何实施心率视频跟踪？

请参阅[在 Adobe Analytics 中测量音频和视频](https://docs.adobe.com/content/help/zh-Hans/media-analytics/using/media-overview.html)。

## Adobe 的服务中断会影响库性能吗？

不会。由于 JavaScript 文件并非是在 Adobe 服务器上托管，因此 Adobe 的故障将不会影响 AppMeasurement 库。如果您使用 Adobe Experience Platform Launch，则 JavaScript 文件由 Akamai 托管，或者托管在由贵组织确定的服务器位置上。

## 将来自浏览器的数据发送至 Adobe 服务会降低性能吗？

AppMeasurement 会在 HTML 页面内创建一个图像对象，浏览器随后从 Adobe 数据收集服务器请求该图像对象。如果数据收集服务器变得缓慢或无反应，则处理该请求的线程将被延迟，直至图像返回或发生超时。因为浏览器会通过多线程处理图像，而 Adobe 故障仅占用一个线程，其他线程继续工作，因此对页面加载时间会造成一定的影响，但这个影响极小。

## 如何使Analytics实施失效或删除？

有时，组织会因合同到期而删除实施或减少服务器调用数。

* **使用Launch的实施**:在“扩展”选项卡中禁用或卸载 [!UICONTROL Adobe Analytics] 扩展，然后发布。
* **旧版AppMeasurement实施**:将文件的整 `s_code.js` 个内容替换为以下代码行：

```js
var s = new Object();
```

>[!WARNING]
>
>不要：
>
>* 将报表包更改为无效值，因为它会在Adobe的服务器上产生不必要的负载。
>* 完全删 `s_code.js` 除文件，除非同时删除每个页面上对文件的所有引用。
>* 更改变 `trackingServer` 量以指向远离Adobe。 AppMeasurement仍会发送图像请求，这会返回404个错误。

