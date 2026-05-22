---
description: 用于在 Report Builder 中配置量度的字段说明。
title: 修改量度 — 字段定义
uuid: 5b82f4f7-f9d2-41c3-b5cb-eefcc2c1d3a6
feature: Report Builder
role: User, Admin
exl-id: 3d2ebd3f-9090-4de6-8da9-50a2640ffaf2
TQID: https://experienceleague.adobe.com/ThbgB8Hrdqsdo7E7EjVDkDC1q-OVn7BYHwEqGl2Cjh4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 65%

---

# 修改量度 — 字段定义

{{legacy-arb}}

用于在 Report Builder 中配置量度的字段说明。

| 字段 | 定义 |
|--- |--- |
| 小计（此请求） | 从服务器收到的响应的小计。 这意味着，它会提供根据您指定的元素选择的日期范围内行项目量度的项目总数。 单击此选项时，总计通过指定起始排名和条目数确定的所有项目的数据。  仅在您选择的量度可汇总时，此选项才可用。 提供的小计还取决于在请求向导的第 2 步中设置的其他所有条件或过滤器。 建议结合使用小计（此请求）和筛选功能。 |
| 平均 | 按日、周或月平均项目。 您还可以指定“无”。  例如，如果选择“路径”量度并将路径名称映射到电子表格，则可以选择将给定时段内内容路径的访问次数显示为原始数据（实际访问次数/时段）或者每天、每周或每月的平均数据（访问次数/时段）。 |
| 前置文本 | 在单元格中添加前缀（数字或字符串值）。 |
| 后置文本 | 在单元格中附加数字或字符串值。 |
