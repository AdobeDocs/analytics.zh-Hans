---
title: charSet
description: charSet 变量可确定 Adobe 用于解析图像请求的编码。
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 92%

---

# charSet

Adobe 会使用 charSet 变量将传入数据转换为 UTF-8，以便 Analytics 进行存储和报告。大部分网站不需要设置此变量。

只有当您在报表中看到了乱码值 ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) 时才设置此变量。如果您的网站在不同页面上使用不同编码，您可逐页设置此变量。

## Adobe Experience Platform 中的“字符集”

“字符集”是在配置 Adobe Analytics 扩展时显示在“[!UICONTROL 常规]”折叠面板中的一个字段。

1. 使用您的Adobe ID凭据登录到[数据收集UI](https://experience.adobe.com/data-collection)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]按钮。
1. 展开[!UICONTROL 常规]折叠面板，这会显示[!UICONTROL 字符集]字段。

您可以使用预设字符集或自定义字符集。除非您在报表中看到乱码值，否则避免更改 `UTF-8` 值。

## AppMeasurement 和 自定义代码编辑器中的 s.charSet

`charSet` 变量是一个字符串。如果您在 Adobe Analytics 中看到乱码值，请将此变量设置为与网站上 `<meta charset="">` HTML 标记相同的值。

```js
s.charSet = "UTF-8";
```
