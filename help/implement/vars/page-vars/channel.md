---
title: channel
description: 填充“网站区域”维度。
feature: Appmeasurement Implementation
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 75%

---

# channel

`channel` 变量通常存储给定页面所在的网站区域。确定最受欢迎的网站组对您很有帮助。此变量可填充“网站区域”维度。

## 使用Web SDK的渠道

渠道已映射到以下变量：

* [XDM对象](/help/implement/aep-edge/xdm-var-mapping.md)： `web.webPageDetails.siteSection`
* [数据对象](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.channel`或`data.__adobe.analytics.ch`

## 使用Adobe Analytics扩展的“渠道”

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置渠道。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 渠道]部分。

可以将渠道设置为任何字符串值或数据元素。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.channel

`s.channel` 变量是一个字符串，通常包含页面的网站区域。其值的最大长度为 100 字节；超出此长度的值会被截断。

```js
s.channel = "Example site section";
```

如果使用`digitalData` [数据层](../../prepare/data-layer.md)：

```js
s.channel = digitalData.page.category.primaryCategory;
```
