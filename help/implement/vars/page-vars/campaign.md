---
title: campaign
description: 填充“跟踪代码”维度。
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 88%

---

# campaign

`campaign` 变量专门用于在您的网站上收集跟踪代码。在 Adobe Analytics 的早期版本中，该变量具有特殊用途，可用于划分大多数维度。在 Adobe Analytics 的当前版本中，它的作用与 eVar 相同。

此变量填充[跟踪代码](/help/components/dimensions/tracking-code.md)维度。它一般使用 [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) 实用方法从查询字符串获取其值。但是，由您的组织确定究竟如何设置此变量。

## 使用 Web SDK 的营销活动

Campaign会映射到以下变量：

* [XDM对象](/help/implement/aep-edge/xdm-var-mapping.md)： `marketing.trackingCode`
* [数据对象](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.campaign` 或 `data.__adobe.analytics.v0`

## 使用 Adobe Analytics 扩展的营销活动

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置营销活动。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 设置 [!UICONTROL 扩展名] Adobe Analytics的下拉列表，以及 [!UICONTROL 操作类型] 到 [!UICONTROL 设置变量].
6. 找到[!UICONTROL 促销活动]部分。

您可以将促销活动设置为一个值或一个查询字符串参数。

## AppMeasurement 和 Analytics 扩展自定义代码编辑器中的 s.campaign

`s.campaign` 变量是一个字符串，通常包含营销活动中使用的跟踪代码。其最大长度为 255 字节；超过 255 字节的值在发送到 Adobe 时会自动被截断。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
