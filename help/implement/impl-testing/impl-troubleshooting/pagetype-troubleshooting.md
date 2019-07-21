---
description: pageType 变量仅用于指定 404（页面未找到）错误页面。
keywords: Analytics 实施
seo-description: pageType 变量仅用于指定 404（页面未找到）错误页面。
seo-title: 正确设置pageType变量
solution: Analytics
subtopic: 故障诊断
title: 正确设置pageType变量
topic: 开发人员和实施
uuid: eafafa58e-ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 正确设置pageType变量

pageType 变量仅用于指定 404（页面未找到）错误页面。

该变量只有一个可能值：errorPage。

```js
pageType="errorPage"
```

在 404 错误页面上，*`pageName`*&#x200B;变量不应被填充。*`pageType`* 该变量只应在指定的404错误页面上设置。Any page containing content should never have a value in the *`pageType`* variable. 对于包含内容的页面，可对该变量做如下设置：

```js
pageType=""
```

最好从包含内容的页面中完全删除该变量。建议采用这种做法以避免混淆该变量的用途。
