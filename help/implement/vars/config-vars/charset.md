---
title: charSet
description: charSet 变量可确定 Adobe 用于解析图像请求的编码。
translation-type: ht
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

Adobe 会使用 charSet 变量将传入数据转换为 UTF-8，以便 Analytics 进行存储和报告。如果您的网站使用的是 charSet 而不是 UTF-8，则此变量允许 Adobe 对您的数据进行正确编码。如果您的网站在不同的页面上使用不同的编码，则可以逐页设置此变量。

## Adobe Experience Platform Launch 中的“字符集”

“字符集”是在配置 Adobe Analytics 扩展时显示在“[!UICONTROL 常规]”折叠面板中的一个字段。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]按钮。
4. 展开[!UICONTROL 常规]折叠面板，这会显示[!UICONTROL 字符集]字段。

您可以使用预设字符集或自定义字符集。此值应与网站上的字符编码相匹配。大多数网站都使用 `UTF-8`。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.charSet

`charSet` 变量是一个字符串。将此变量的值设置为与网站上 `<meta charset="">` HTML 标记相同的值。

```js
s.charSet = "UTF-8";
```
