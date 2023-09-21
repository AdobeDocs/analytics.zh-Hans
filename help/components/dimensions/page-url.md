---
title: 页面 URL
description: 页面的 URL。
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 95%

---

# 页面 URL

“页面URL” [维度](overview.md) 列出了您网站上的URL。

>[!IMPORTANT]
>
>此维度只能在 Data warehouse 中使用。如果您要在其他 Analytics 解决方案中使用 URL 维度，请考虑在每次点击时将该值复制到 [eVar](evar.md) 中。

## 使用数据填充此维度

此维度从[页面查看调用 (`t()`)](/help/implement/vars/functions/t-method.md)](/help/implement/validate/query-parameters.md) 中的 [`g` 和 `-g` 查询字符串检索数据。[链接跟踪调用 (`tl()`)](/help/implement/vars/functions/tl-method.md) 始终剥离此维度，即使存在 `g` 查询字符串。

有时 URL 的长度会大于 255 字节。AppMeasurement 对图像请求中 URL 的前 255 字节使用 `g` 查询字符串参数。如果 URL 的长度大于 255 字节，则 URL 的其余部分会存储在 `-g` 查询字符串参数中。URL 中的协议和查询字符串均包含在此变量中。

AppMeasurement 基于页面的 URL 自动收集此数据。您可以使用 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 变量覆盖收集的值。

## 使用 URL 填充 eVar

Adobe 建议将 eVar 设置为串联字符串 `window.location.hostname + window.location.pathname`。此字符串的效果通常比 `window.location.href` 更好，因为它忽略了协议、查询字符串和锚点标签。

如果您希望 eVar 与 Data Warehouse 中的“页面 URL”维度完全匹配，则可以使用[动态变量](/help/implement/vars/page-vars/dynamic-variables.md)并在每次点击时将 eVar 设置为 `D=g`。

## 维度项目

维度项目包括网站上页面的 URL。
