---
title: campaign
description: 填充“跟踪代码”维。
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# campaign

该变 `campaign` 量专门用于收集您网站上的跟踪代码。 在Adobe Analytics的早期版本中，它具有特殊的处理方式，可用作大多数维度的细分。 在Adobe Analytics的当前版本中，它的作用与eVar相同。

此变量填充“跟踪代码”维。

## Adobe Experience Platform Launch 中的促销活动

您可以在配置Analytics扩展时（全局变量）或根据规则设置营销活动。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到“营 [!UICONTROL 销活动] ”部分。

您可以将系列活动设置为值或查询字符串参数。

## AppMeasurement中的s.campaign和启动自定义代码编辑器

该 `s.campaign` 变量是一个字符串，通常包含营销工作中使用的跟踪代码。 最大长度为255字节；超过100字节的值在发送到Adobe时会自动截断。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
