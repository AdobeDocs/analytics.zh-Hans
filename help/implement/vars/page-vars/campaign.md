---
title: campaign
description: 填充“跟踪代码”维度。
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '191'
ht-degree: 100%

---

# campaign

`campaign` 变量专门用于在您的网站上收集跟踪代码。在 Adobe Analytics 的早期版本中，该变量具有特殊用途，可用于划分大多数维度。在 Adobe Analytics 的当前版本中，它的作用与 eVar 相同。

此变量会填充“跟踪代码”维度。

## Adobe Experience Platform Launch 中的促销活动

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置促销活动。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 促销活动]部分。

您可以将促销活动设置为一个值或一个查询字符串参数。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.campaign

`s.campaign` 变量是一个字符串，通常包含营销工作中使用的跟踪代码。其最大长度为 255 字节；超过 255 字节的值在发送到 Adobe 时会自动被截断。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
