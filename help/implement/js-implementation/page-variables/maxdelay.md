---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# maxDelay

s.maxDelay 变量主要用在 Genesis DFA 集成中，用来确定联系 DFA 主机时的超时时间段。如果 Adobe 在变量中设置的指定时段内没有收到来自 DFA 服务器的响应，则连接断开，并照常处理数据。如果您关注的是每个页面上的 DFA 响应时间，则实施此变量。建议使用此值进行试验，以确定最佳的超时时间段。

<!-- 

maxDelay.xml

 -->

**实施示例**

```
s.maxDelay="750";
```

**属性**

* 此变量是一个可选事件量度，通过网站上实施的 JavaScript 填充。
* 如果 DFA 主机未在给定的时间内响应，将运行被指定给超时的事件（通过 Genesis 集成向导指定）。
* 此变量可只包含一个数字值。
* 指定的时间以毫秒为单位计算。
* 增加等待时间会收集到更多的 DFA 数据，但这也会增加 Analytics 点击数据丢失的风险。

   如果用户在 *`s.maxDelay`* 时段离开页面，Analytics 点击数据将会丢失。

* 减少等待时间会降低 Analytics 点击数据丢失的风险，但这也会减少随点击数据发送的 DFA 数据量。

   如果在 *`s.maxDelay`* 时段没有为 DFA 主机提供足够的响应时间，则会丢失 DFA 集成数据。

> [!NOTE]Adobe 不会控制 DFA 的响应时间。如果将最大延迟时段增加到一个合理的时间范围后发现问题依然存在，请咨询贵组织的 DFA 帐户管理员。
