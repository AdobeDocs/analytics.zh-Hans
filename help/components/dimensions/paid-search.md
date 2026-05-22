---
title: 付费搜索
description: 从付费搜索与免费搜索方面区分量度。
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
TQID: https://experienceleague.adobe.com/s9jhjGeXaOCo-Wz-Jyof951NZdRWfz-9tjrVrjHvTS0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 87%

---

# 付费搜索

“付费搜索”[维度](overview.md)允许您查看任何量度，并在付费搜索与免费搜索之间进行比较。 搜索引擎以外的所有其他点击将会被忽略。 此维度有助于您了解付费搜索与免费搜索的对比情况。

## 使用数据填充此维度

此维度正常使用的唯一要求是：在报表包设置中正确配置[付费搜索检测](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)。 如果付费搜索检测配置正确且报表包包含数据，则此维度始终有效。

## 维度项目

维度项目包括两个静态值：`"Natural"` 和 `"Paid"`。 如果访问与搜索引擎的条件匹配并且与付费搜索检测也匹配，则它属于 `"Paid"` 维度项目。 如果访问与搜索引擎的条件匹配但与付费搜索检测&#x200B;*不*&#x200B;匹配，则它属于 `"Natural"` 维度项目。
