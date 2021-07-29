---
title: maxDelay
description: 确定 AppMeasurement 在发送图像请求之前等待 DFA 响应的最长时间。
exl-id: 154f7e34-39e7-4390-ae36-d4fbc998787f
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 92%

---

# maxDelay

`s.maxDelay` 变量用在 DFA Data Connector 中来确定连接 DFA 主机时的超时时间段。如果 Adobe 在此变量中设置的指定时间段内没有收到来自 DFA 服务器的响应，则会断开连接，并正常处理数据。如果您关注每个页面上的 DFA 响应时间，请将此变量包含在实施中。Adobe 建议对此值进行试验，以确定最佳超时时间段。

此变量仅用在使用 DFA Data Connector 的实施中。此变量是可选的，即使对于使用 DFA 的实施也是如此。

## 在Adobe Experience Platform中使用标记的最大延迟

数据收集UI中没有可使用此变量的专用字段。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 自定义代码编辑器中的 s.maxDelay

`s.maxDelay` 变量是一个整数，表示 AppMeasurement 等待 DFA 响应的毫秒数。如果 AppMeasurement 未及时收到来自 DFA 的响应，则会向 Adobe 发送图像请求，而不包含 DFA 数据。

```js
s.maxDelay = 750;
```

## 属性

* 增加等待时间会收集到更多的 DFA 数据，但这也会增加 Analytics 点击数据丢失的风险。如果用户在 `s.maxDelay` 时段离开页面，Analytics 点击数据将会丢失。
* 减少等待时间会降低 Analytics 点击数据丢失的风险，但这也会减少随点击数据发送的 DFA 数据量。
* 如果在 `s.maxDelay` 时段没有为 DFA 主机提供足够的响应时间，则会丢失 DFA 集成数据。

>[!NOTE]
>
>Adobe 不会控制 DFA 的响应时间。如果将最大延迟时段增加到一个合理的时间范围后发现问题依然存在，请咨询贵组织的 DFA 帐户管理员。
