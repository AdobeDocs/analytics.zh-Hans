---
title: 页面 URL
description: 页面的 URL。
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 69%

---


# 页面 URL

“页面 URL”维度列出您网站上的 URL。

>[!IMPORTANT]
>
>此维度只能在 Data warehouse 中使用。如果要在其他Analytics解决方案中使用URL维度，请考虑在每次点击时将该值 [复制](evar.md) 到eVar中。

## 使用数据填充此维度

This dimension retrieves data from the [`g` and `-g` query strings](/help/implement/validate/query-parameters.md) in [Page view calls (`t()`)](/help/implement/vars/functions/t-method.md). [链接跟踪调用`tl()`(](/help/implement/vars/functions/tl-method.md) )始终会删除此维，即使存 `g` 在查询字符串。

有时 URL 的长度会大于 255 字节。AppMeasurement 对图像请求中 URL 的前 255 字节使用 `g` 查询字符串参数。如果 URL 的长度大于 255 字节，则 URL 的其余部分会存储在 `-g` 查询字符串参数中。URL 中的协议和查询字符串均包含在此变量中。

AppMeasurement会根据页面的URL自动收集此数据。 您可以使用变量覆盖收集的 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 值。

## 使用 URL 填充 eVar

Adobe 建议将 eVar 设置为串联字符串 `window.location.hostname + window.location.pathname`。此字符串的效果通常比 `window.location.href` 更好，因为它忽略了协议、查询字符串和锚点标签。

如果您希望 eVar 与 Data Warehouse 中的“页面 URL”维度完全匹配，则可以使用[动态变量](/help/implement/vars/page-vars/dynamic-variables.md)并在每次点击时将 eVar 设置为 `D=g`。

## 维度项目

维度项目包括网站上页面的 URL。
