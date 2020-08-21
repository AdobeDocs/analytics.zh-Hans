---
title: 页面 URL
description: 页面的 URL。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 92%

---


# 页面 URL

“页面 URL”维度列出您网站上的 URL。

>[!IMPORTANT]
>
>此维度只能在 Data warehouse 中使用。如果要在其他 Analytics 解决方案中使用 URL 维度，请使用 [eVar](evar.md)。

## 使用数据填充此维度

此维度从图像请求中的 [`g` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。AppMeasurement 使用 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 变量收集此数据。

## 使用 URL 填充 eVar

Adobe 建议将 eVar 设置为串联字符串 `window.location.hostname + window.location.pathname`。此字符串的效果通常比 `window.location.href` 更好，因为它忽略了协议、查询字符串和锚点标签。

如果您希望 eVar 与 Data Warehouse 中的“页面 URL”维度完全匹配，则可以使用[动态变量](/help/implement/vars/page-vars/dynamic-variables.md)并在每次点击时将 eVar 设置为 `D=g`。请注意，此方法不适用于自定义链接点击，因为所有 [`tl()`](/help/implement/vars/functions/tl-method.md) 调用均已剥除页面 URL。

## Dimension项

Dimension项包括站点上页面的URL。
