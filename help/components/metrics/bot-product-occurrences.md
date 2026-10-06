---
title: 机器人产品发生次数
description: “机器人产品发生次数”量度显示与机器人规则匹配并从Analytics报表中排除的产品字符串子点击数。
feature: Metrics
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 3ba8d2cce29a1965c85789c3fd0543c23533e3a8
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 5%
---
# 机器人产品发生次数

“机器人产品发生次数”[量度](overview.md)显示与[机器人规则](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)匹配的子点击数。

由于机器人报表与报表包的其他数据是分开的，因此此量度仅适用于以下维度：

* [机器人名称](../dimensions/bot-name.md)
* [产品](../dimensions/product.md)
* 基于时间的维度（例如，[Day](../dimensions/day.md)、[Week](../dimensions/week.md)或[Month](../dimensions/month.md)）

将任何其他维度与此量度一起使用不会返回数据。

## 如何计算此指标

Adobe使用[product string](/help/implement/vars/page-vars/products.md)检查每个子点击，查看它是否与您的组织配置的机器人规则匹配。 如果给定的子点击与机器人规则匹配，则该子点击将从报表中排除，并且此量度将增加1。
