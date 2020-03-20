---
title: campaign
description: 填充“跟踪代码”维。
translation-type: tm+mt
source-git-commit: 7220b99268532adb2e425d52744dbc3efb615953

---


# campaign

该变 `campaign` 量专门用于收集您网站上的跟踪代码。 在Adobe Analytics的早期版本中，它具有特殊的处理方式，可用作大多数维度的细分。 在Adobe Analytics的当前版本中，它的作用与eVar相同。

此变量填充“跟踪代码”维。

## Adobe Experience Platform Launch 中的促销活动

您可以在配置Analytics扩展时（全局变量）或根据规则设置营销活动。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到选项卡， [!UICONTROL Rules] 然后单击所需的规则（或创建规则）。
4. 在下 [!UICONTROL Actions]面，单击现有 [!UICONTROL Adobe Analytics - Set Variables] 操作或单击“+”图标。
5. 将下拉 [!UICONTROL Extension] 列表设置为Adobe Analytics，将其设置为 [!UICONTROL Action Type] to [!UICONTROL Set Variables]。
6. Locate the [!UICONTROL Campaign] section.

您可以将系列活动设置为值或查询字符串参数。

## AppMeasurement中的s.campaign和启动自定义代码编辑器

该 `s.campaign` 变量是一个字符串，通常包含营销工作中使用的跟踪代码。 最大长度为255字节；超过255字节的值在发送到Adobe时会自动截断。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
