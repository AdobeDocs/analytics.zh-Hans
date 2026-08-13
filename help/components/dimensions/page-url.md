---
title: 页面 URL
description: 页面的 URL。
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 95%

---

# 页面 URL

“页面URL”[维度](overview.md)列出了您网站上的URL。

>[!IMPORTANT]
>
>此维度只能在 Data warehouse 中使用。 如果您要在其他 Analytics 解决方案中使用 URL 维度，请考虑在每次点击时将该值复制到 [eVar](evar.md) 中。

## 使用数据填充此维度

此维度从[页面查看调用 (`t()`)](/help/implement/vars/functions/t-method.md) [&#128279;](/help/implement/validate/query-parameters.md) 中的 `g` 和 `-g` 查询字符串检索数据。 [链接跟踪调用 (`tl()`)](/help/implement/vars/functions/tl-method.md) 始终剥离此维度，即使存在 `g` 查询字符串。

有时 URL 的长度会大于 255 字节。 AppMeasurement 对图像请求中 URL 的前 255 字节使用 `g` 查询字符串参数。 如果 URL 的长度大于 255 字节，则 URL 的其余部分会存储在 `-g` 查询字符串参数中。 URL 中的协议和查询字符串均包含在此变量中。

AppMeasurement 基于页面的 URL 自动收集此数据。 您可以使用 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 变量覆盖收集的值。

## 使用 URL 填充 eVar

Adobe 建议将 eVar 设置为串联字符串 `window.location.hostname + window.location.pathname`。 此字符串的效果通常比 `window.location.href` 更好，因为它忽略了协议、查询字符串和锚点标签。

如果您希望 eVar 与 Data Warehouse 中的“页面 URL”维度完全匹配，则可以使用[动态变量](/help/implement/vars/page-vars/dynamic-variables.md)并在每次点击时将 eVar 设置为 `D=g`。

## 维度项目

维度项目包括网站上页面的 URL。
