---
title: 层级
description: （已停用）可在报表中使用的自定义维度。
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
TQID: https://experienceleague.adobe.com/7WnYvaE3qCfYGWcX6IuvMZiF0MJq50Izz6i2LNg4h6c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 167
ht-degree: 86%

---

# 层级

>[!IMPORTANT]
>
>此维度已停用，且在Analysis Workspace中不是可用的[维度](overview.md)。 Adobe 建议改用 [eVar](evar.md) 和分类。

层级是自定义变量，您可以根据需要随意使用。 它们不会在设置的点击之外继续存在。 如果您与 Adobe 签署的合同支持，则至多有 5 个层级可供使用。

## 使用数据填充层级

每个层级都从图像请求中的 [`h1` – `h5` 查询字符串](/help/implement/validate/query-parameters.md)中收集数据。 例如，`h1` 查询字符串参数为层级 1 收集数据，而 `h4` 查询字符串参数为层级 4 收集数据。

AppMeasurement 将 JavaScript 变量编译到图像请求中以用于数据收集，它使用变量 `hier1` — `hier5`。 请参阅实施用户指南中的[层级](/help/implement/vars/page-vars/hier.md)，了解相关实施指南。

## 维度项目

由于层级在您的实施中包含自定义字符串，因此，由您的组织来确定每个层级的维度项目。 请确保在[解决方案设计文档](/help/implement/prepare/solution-design.md)中记录每个层级的用途和典型维度项目。
