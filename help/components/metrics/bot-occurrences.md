---
title: 机器人发生次数
description: 与机器人规则匹配的点击数。
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
TQID: https://experienceleague.adobe.com/LH7eQC-Z6Y3nku1QzI9Yn0N3MRwGA--5R-93lfadT1c
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 9%

---

# 机器人发生次数

“机器人发生次数”[量度](overview.md)显示与[机器人规则](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)匹配的点击数。

由于机器人报表与报表包的其他数据是分开的，因此此量度仅适用于以下维度：

* [机器人名称](../dimensions/bot-name.md)
* [页面](../dimensions/page.md)
* 基于时间的维度（例如，[Day](../dimensions/day.md)、[Week](../dimensions/week.md)或[Month](../dimensions/month.md)）

将任何其他维度与此量度一起使用不会返回数据。

## 如何计算此指标

Adobe检查每次点击，查看它是否与贵组织配置的机器人规则匹配。 如果给定的点击与机器人规则匹配，则该点击将从报表中排除，并且此量度将增加1。 此量度包括页面查看次数([`t()`](/help/implement/vars/functions/t-method.md))和链接跟踪点击([`tl()`](/help/implement/vars/functions/tl-method.md))，而[机器人页面查看次数](bot-page-views.md)不包括链接跟踪点击。
