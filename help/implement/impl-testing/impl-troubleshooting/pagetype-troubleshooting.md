---
description: pageType 变量仅用于指定 404（页面未找到）错误页面。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 正确设置 PageType 变量
topic: Developer and implementation
uuid: eafaf58e-ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 正确设置 PageType 变量

pageType 变量仅用于指定 404（页面未找到）错误页面。

该变量只有一个可能值：errorPage。

```js
pageType="errorPage"
```

在 404 错误页面上，*`pageName`*&#x200B;变量不应被填充。*`pageType`* 变量只能在指定的 404 错误页面上设置。包含内容的任何页面中的 *`pageType`* 变量绝不应该有值。对于包含内容的页面，可对该变量做如下设置：

```js
pageType=""
```

最好从包含内容的页面中完全删除该变量。建议采用这种做法以避免混淆该变量的用途。
