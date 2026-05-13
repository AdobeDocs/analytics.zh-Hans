---
title: 计算量度总计
description: 了解Analysis Workspace中的计算量度总计
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
TQID: https://experienceleague.adobe.com/3UJF1Hl3nLqjYAiQuvcE4Jpq26MaTgeba5BmnVfvEps
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e318d41c-1d01-4c1e-9b18-1f61d435ceee
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 149
ht-degree: 94%

---

# 计算量度总计

在 Analysis Workspace 中查看数据时，大多数情况下都会显示计算量度总计。 在某些情况下则无法提供“总计”，例如，当报表行采用混合格式（例如，小数和货币）时。

显示“总计”时，量度通常在服务器端进行计算，这意味着“总计”删除了重复量度（例如，访问或访客）。 在某些情况下，计算量度是在客户端通过表行相加生成，这意味着“总计”不会删除重复量度（例如，访问或访客）。 这种情况出现于：

* 当自由格式表中使用了[静态行](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)，并且选择了&#x200B;**[!UICONTROL 显示为当前行的总和]**￼选项（默认）时。
* 在[圆环可视化图表](/help/analyze/analysis-workspace/visualizations/donut.md)中，这是为了使数字相加总和等于 100%。

有关 Analysis Workspace 中总计的更多信息，请访问 [Workspace 总计](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total)。
