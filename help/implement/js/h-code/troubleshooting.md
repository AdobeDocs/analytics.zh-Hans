---
title: H代码实现疑难解答
description: 了解旧版JavaScript实现的一些常见问题。
translation-type: tm+mt
source-git-commit: 69138bdedb42b66449426fee39822520ee4b1198

---


# H代码实现疑难解答

以下是H代码实现的特定疑难解答步骤。

## 在 Head 标记中置入 Analytics 代码

> [!NOTE] 虽然H代码实现要求在标记中引用代码，但其他实现( `<body>` 如使用Adobe Experience Platform Launch)要求在标记中引用代 `<head>` 码。

分析代码可创建不可见的1x1像素图像。 以前，一个常见的实施做法是将引 `s_code.js` 用放在标记 `<head>` 中。 将代码放置到此处可防止图像以任何方式影响页面布局。 它还可以更快地执行，这样您就可以更有效地计算部分页面加载的页面查看次数。

However, certain elements of the code require the existence of the `<body>` object. 如果Analytics javaScript代码在标记中， `<head>` 则该代码会在对象存在前 `<body>` 执行。 As a result, your implementation does not collect [!UICONTROL ClickMap] data, automatic tracking of file downloads or exit links, or connection type data. 将脚本引用放 `s_code.js` 入标 `<head>` 记是有效的，但结果是Analytics的有限版本。

The Analytics code can be placed anywhere inside the `<body>` tag of a well-formed HTML page. Adobe建议将Analytics代码放置到尽可能靠近标 `<body>` 记顶部的位置。 确保在文件加载后设置任何页 `s_code.js` 面变量。

> [!TIP] 如果要将Adobe Analytics与Adobe Target集成，则必须将JavaScript包含文件放在页面底部。
