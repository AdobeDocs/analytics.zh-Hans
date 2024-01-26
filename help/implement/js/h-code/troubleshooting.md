---
title: H 代码实施疑难解答
description: 了解旧版 JavaScript 实施存在的一些常见问题。
feature: Implementation Basics
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 100%

---

# H 代码实施疑难解答

以下是特定于 H 代码实施的疑难解答步骤。

## 在 Head 标记中置入 Analytics 代码

>[!NOTE]
>
>虽然 H 码实施要求在 `<body>` 标记中引用代码，但其他实施（如使用 Adobe Experience Platform 中的标记的实施）要求在 `<head>` 标记中引用代码。

Analytics 代码可创建不可见的 1x1 像素图像。过去，一种常用的实施做法是将 `s_code.js` 引用放置到 `<head>` 标记中。将代码放置到此处可防止图像以任何方式影响页面布局。此外，Analytics 代码还可以更快执行，从而允许您更有效地计算部分页面加载的页面查看次数。

但是，某些代码元素要求存在 `<body>` 对象。如果 Analytics JavaScript 代码位于 `<head>` 标记中，则该代码会在 `<body>` 对象存在之前先执行。因此，您的实施不会收集 [!UICONTROL ClickMap] 数据、文件下载或退出链接的自动跟踪数据，或连接类型数据。虽然可以将对 `s_code.js` 的脚本引用放置到 `<head>` 标记中，但生成的结果只能是非常受限的 Analytics 版本。

对于格式正确的 HTML 页面，Analytics 代码可置于 `<body>` 标记中的任何位置。Adobe 建议尽量靠近 `<body>` 标记的顶部放置 Analytics 代码。确保在 `s_code.js` 文件加载后再设置任何页面变量。

>[!TIP]
>
>如果您要将 Adobe Analytics 与 Adobe Target 集成，则 JavaScript 包含文件必须置于页面底部。
