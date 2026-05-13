---
title: 所有搜索页面排名
description: 确定访客点击了搜索引擎上的哪个页面进入您的网站。
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
TQID: https://experienceleague.adobe.com/U7WgtQDXInyD1gXeBntncC9Fao1Rdc9W4AHFgx07T4A
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
source-wordcount: 146
ht-degree: 85%

---

# 所有搜索页面排名

“所有搜索页面排名”[维度](overview.md)为insight提供了访客在搜索结果的哪个页面上点击进入您的网站。 例如，如果您的网站出现在搜索引擎的搜索结果的第二页，则此变量的维度项目是“搜索页面 2”。

## 使用数据填充此维度

要使此维度正常工作，只需为您的报表包正确设置[内部 URL 过滤器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)。 AppMeasurement 会自动填充此维度，而无需更改任何实施代码。

## 维度项目

如果访客从搜索引擎点击进入您的网站，则此维度的值为“搜索页面”，后跟他们点击的页码。 如果点击不是来自搜索引擎，则此维度的值为“未指定”。
