---
title: charSet
description: charSet 变量可确定 Adobe 用于解析图像请求的编码。
translation-type: tm+mt
source-git-commit: 70410af433f540764b71bd29a81ff9d8210cb95c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 60%

---


# charSet

Adobe 会使用 charSet 变量将传入数据转换为 UTF-8，以便 Analytics 进行存储和报告。大多数站点无需设置此变量。

仅当在报告中看到乱码值(mojibake)[时](https://en.wikipedia.org/wiki/Mojibake)，才设置此变量。 如果您的站点在不同的页面上使用不同的编码，则可以逐页设置此变量。

## Adobe Experience Platform Launch 中的“字符集”

“字符集”是在配置 Adobe Analytics 扩展时显示在“[!UICONTROL 常规]”折叠面板中的一个字段。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]按钮。
4. 展开[!UICONTROL 常规]折叠面板，这会显示[!UICONTROL 字符集]字段。

您可以使用预设字符集或自定义字符集。避免将值从更改为， `UTF-8` 除非您在报告中看到乱码值。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.charSet

`charSet` 变量是一个字符串。如果您在Adobe Analytics中的值乱码，请将此变量设置为与站点上 `<meta charset="">` 的HTML标签相同的值。

```js
s.charSet = "UTF-8";
```
