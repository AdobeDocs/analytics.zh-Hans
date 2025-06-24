---
title: charSet
description: charSet 变量可确定 Adobe 用于解析图像请求的编码。
feature: Appmeasurement Implementation
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 65%

---

# charSet

Adobe使用`charSet`变量将传入数据转换为UTF-8，以便Analytics进行存储和报告。 大部分网站不需要设置此变量。

只有当您在报表中看到了乱码值 ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) 时才设置此变量。如果您的网站在不同页面上使用不同编码，您可逐页设置此变量。

## Web SDK中的字符集

Web SDK当前仅支持UTF-8，不提供更改编码的选项。

## Adobe Analytics扩展中的“字符集”

在Adobe Experience Platform数据收集中配置Adobe Analytics扩展时，“字符集”是[!UICONTROL 常规]折叠面板下的字段。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 展开[!UICONTROL 常规]折叠面板，这会显示[!UICONTROL 字符集]字段。

您可以使用预设字符集或自定义字符集。除非您在报表中看到乱码值，否则避免更改 `UTF-8` 值。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.charSet

`charSet` 变量是一个字符串。如果您在 Adobe Analytics 中看到乱码值，请将此变量设置为与网站上 `<meta charset="">` HTML 标记相同的值。

```js
s.charSet = "UTF-8";
```
