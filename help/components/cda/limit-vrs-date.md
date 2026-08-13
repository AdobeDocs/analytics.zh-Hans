---
title: 将虚拟报告包限制在特定日期
description: 了解如何将虚拟报表包日期范围限制为仅关注拼接数据。
exl-id: 421d101d-8c64-47f7-b5a2-da039889f663
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/x7zHG4xkSr1yDLZ2dfosn5PaK4JVxiMWC6xksSTLypE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 41%

---

# 将虚拟报告包限制在特定日期

{{available-existing-customers}}

当我们启用合并时，合并过程在特定日期开始。 我们假设该日期为 6 月 1 日。 CDA虚拟报表包将包含6月1日之前未拼合的数据。 您可能希望在6月1日之前隐藏虚拟报表包中的任何数据，以便分析可以重点关注拼合开始后的日期范围。

您可以通过执行以下操作将虚拟报表包数据限制为特定日期：

## 步骤1：创建具有“每日滚动”日期范围的虚拟报表包

设置虚拟报表包时，在“组件”下，添加具有固定开始日期和“每日滚动”日期范围的日期范围。 固定开始日期应该是开始合并的那一天。

![](assets/rolling-daily.png)

## 第 2 步：创建“排除-排除”区段

接下来，创建将日期范围放入排除容器中的点击区段，该容器位于另一个排除容器中。 这就是“排除 — 排除”。

选择“排除 — 排除”的原因是日期范围旨在覆盖报表的日期范围。 因此，如果您只包括 6 月 1 日之后的日期，这会使报表的日期范围始终为 6 月 1 日以后的日期。 随之会带来不符合要求的结果。 当您“排除 — 排除”时，它会覆盖此行为，而只限制您可从相应日期范围中提取的数据。

![](assets/exclude-exclude.png)

## 步骤3：将此区段应用于您的跨设备分析虚拟报表包

![](assets/apply-segment.png)

## 第 4 步：在报表中查看结果

请注意，报表现在从所需的日期开始，即开始实施合并的同一天：

![](assets/report-limited-dates.png)
