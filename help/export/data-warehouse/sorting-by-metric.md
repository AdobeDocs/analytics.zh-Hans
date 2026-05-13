---
description: 了解按量度排序如何让Data Warehouse报表易于解释和与其他Analytics划分报表视图进行比较。
title: 按量度排序
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
TQID: https://experienceleague.adobe.com/YPqL6i9RWACubLdf2ywm8xuPyeQkZ30L6rO6FAbhpJI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 337
ht-degree: 17%

---

# 按指标排序

在Data Warehouse中提供排名划分报表，这些报表按量度值的降序排序。

按量度排序使您更轻松地解释Data Warehouse报表，并使这些报表更易于与其他Analytics划分报表视图进行比较。

下面显示了启用“量度排序”选项将如何对Data Warehouse报表中的行重新排序。

根据日期粒度、报表维度或量度的配置方式以及是否设置了“最大行数”，Data Warehouse报表可通过四种可能的方式“量度排序”进行组织：

* **布局1**：行项按字典顺序排序（默认）。 如果设置了“最大行数”，则报表中只提供前N行。
* **布局 2**：Data Warehouse 对报表中的所有行应用量度排序。 第一个量度值中的绑定由第二个量度断开，然后由第三个量度断开，依此类推。 当所有量度都绑定时，将应用划分行项目的标准字典排序。
* **布局3**：作为布局2，报告中仅输出前N行（即“最大行数”中设置的数字）。
* **布局4**：作为布局2，但每个日期粒度时段的行项目均分组并在相应的时间范围内排序。

请参阅此表中的“报表布局”列，以确定“量度排序”与其他Data Warehouse报表选项的交互方式。

| 按量度排序? | 具有指标？ | 有划分吗？ | 日期粒度？ | 设置的最大行数？ | 报告布局 |
|---|---|---|---|---|---|
| 否 | “是”或“否” | “是”或“否” | “是”或“否” | “是”或“否” | 1 |
| 是 | 否 | “是”或“否” | “是”或“否” | “是”或“否” | 1 |
| 是 | 是 | 否 | 否 | 不适用 | 1 |
| 是 | 是 | 否 | “是”或“否” | 否 | 1 |
| 是 | 是 | 是 | 否 | 否 | 2 |
| 是 | 是 | 否 | 是 | 是 | 3 |
| 是 | 是 | 是 | “是”或“否” | 是 | 3 |
| 是 | 是 | 是 | 是 | 否 | 4 |
