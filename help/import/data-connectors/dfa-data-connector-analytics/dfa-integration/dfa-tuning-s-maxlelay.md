---
description: 为成功实现 DFA 实施，需要为您的特定网站优化 s.maxDelay。
keywords: DFA
seo-description: 为成功实现 DFA 实施，需要为您的特定网站优化 s.maxDelay。
seo-title: 调整 s.maxDelay
solution: Analytics
title: 调整 s.maxDelay
topic: Data connectors
uuid: 7640af26-6ac6-427e-9cfc-932c86ccf5ab
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 调整 s.maxDelay{#tuning-s-maxdelay}

为成功实现 DFA 实施，需要为您的特定网站优化 s.maxDelay。

一般来说，提升或降低 *`s.maxDelay`* 的决定涉及到获得更多DFA访客数据并危及收集Adobe访客数据。Increasing *`s.maxDelay`* obtains more DFA visitor data, but (placed excessively high) could endanger the collection of Adobe visitor data. 降低 s.maxDelay 值可确保 Adobe 访客数据的收集，但可能损失 DFA 访客数据。

*`s.maxDelay`*&#x200B;不仅在网络通信中封装时间来联系 DFA，它还表示要触发的浏览器延迟并评估这些通信所基于的 JavaScript。这是因为集成模块在将HTML元素插入DOM后开始计时器 *`s.maxDelay`* ，从DFA Floomight服务器中提取数据。浏览器基于这一新 HTML 元素实际发起 HTTP 请求所花费的时间量，根据同时加载的其他图像或 JavaScript 文件、访客计算机的速度和特定的浏览器实施而有所不同。此外，在从 DFA Floodlight 服务器中检索 JSON 数据时，JavaScript 必须由浏览器评估。它仍然由浏览器完全控制，并在同时运行的 JavaScript 代码量较大或存在大量异步 JavaScript 请求的情况下可将其延迟。

如此一来，*`s.maxDelay`*&#x200B;需要根据登陆页面的复杂性以及 DFA 的网络延迟量进行设置。在某些网站上，一种可用来降低复杂性的方法是在页面加载过程中提早触发 Adobe 收集代码，这样可在请求 Floodlight 服务器时减少浏览器中运行的内容。

超时变量在调整&#x200B;*`s.maxDelay`*&#x200B;因为每次达到s. maxDelay超时都会递增。在决定是否增加或减少 *`s.maxDelay`* 时，我们建议遵循此流程：

1. 将几天的数据收集 *`s.maxDelay`* 到特定值。
1. 运行 [!DNL Daily Unique Visitors Report] 时间范围。
1. Run the [!DNL Timeout Event Report] to check the number of timeouts that are coming through. 请记住，超时只针对每个访客收集一次。

现在有了数据在手，便可计算

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

请注意，超时百分比实际上考虑了所有的网站访客。这其中的某些访客完全不会关联到 DFA，因此该超时具有误导性。To improve this computation, another analysis could consider only unique visitors to pages with the `clickThroughParam` set (for example, `?CID=1`). 这将显示更高的准确性。

如果超时百分比非常低，请考虑降低 *`s.maxDelay`*。如果它非常高，请提高 *`s.maxDelay`*. When decreasing *`s.maxDelay`*, you will want to rerun the [!DNL Timeout Report] to ensure that timeouts have not dramatically increased. When increasing *`s.maxDelay`*, you will want to run a [!DNL Page Views Report] to make sure page views aren’t falling out due to lost data. Each time *`s.maxDelay`* is changed observe the data for several days in order to ensure that the data represents a trend, and not just a day-to-day fluctuation.

The optimal setting for *`s.maxDelay`* is the point at which the timeout percentage is minimized while Page Views do not drop off.

当您转到版本 2.0 的集成时，超时次数预计会因为消除了 302 重定向而减少。使用测试版客户端的初步调查结果显示超时次数持续减少，因此将收集更多的 DFA 数据。
