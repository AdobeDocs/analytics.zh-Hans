---
description: pageType 变量仅用于指定 404（页面未找到）错误页面。
keywords: Analytics 实施
seo-description: pageType 变量仅用于指定 404（页面未找到）错误页面。
seo-title: 正确设置 PageType 变量
solution: Analytics
subtopic: 故障诊断
title: 正确设置 PageType 变量
topic: 开发人员和实施
uuid: eafaf58e-ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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
