---
title: channel
description: 填充“网站区域”维度。
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 97%

---


# channel

`channel` 变量通常存储给定页面所在的网站区域。确定最受欢迎的网站组对您很有帮助。此变量可填充“网站区域”维度。

## Adobe Experience Platform Launch 中的“渠道”

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置渠道。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 渠道]部分。

可以将渠道设置为任何字符串值或数据元素。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.channel

`s.channel` 变量是一个字符串，通常包含页面的网站区域。其值的最大长度为 100 字节；超出此长度的值会被截断。

```js
s.channel = "Example site section";
```

如果使用数 `digitalData` 据 [层](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
