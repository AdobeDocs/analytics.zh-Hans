---
title: charSet
description: charSet变量决定Adobe用于分析图像请求的编码。
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

Adobe使用charSet变量将传入数据转换为UTF-8，以便Analytics进行存储和报告。 如果您的站点使用UTF-8以外的charSet，则此变量允许Adobe对您的数据进行正确编码。 如果您的站点在不同的页面上使用不同的编码，则可以逐页设置此变量。

## Adobe Experience Platform Launch中的字符集

字符集是配置Adobe Analytics扩展时 [!UICONTROL 在] “常规”折叠面板下的字段。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“ [!UICONTROL 常规] ”折叠面板 [!UICONTROL ，该面板显示“] 字符集”字段。

您可以使用预设字符集或自定义字符集。 此值应与站点上的字符编码匹配。 大多数网站都使 `UTF-8`用。

## s.charSet in appMeasurement and Launch自定义代码编辑器

变量 `charSet` 是字符串。 将此变量设置为与站点上的 `<meta charset="">` HTML标记相同的值。

```js
s.charSet = "UTF-8";
```
