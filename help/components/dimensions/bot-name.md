---
title: 机器人名称
description: 与机器人规则匹配的机器人的名称。
source-git-commit: d7d9bbf9bf43509eb756408f772be870c3854aa5
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# 机器人名称

“机器人名称”维度显示使用 [机器人规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). 这些规则可以是默认的IAB规则，也可以是您的组织配置的自定义机器人规则。 当您想要进一步了解哪些机器人正在访问您的网站，或哪些机器人生成的流量最多时，此功能非常有用。

匹配的点击 [!UICONTROL 机器人规则] 会自动从所有Analytics报表中过滤出来，但此维度除外， [机器人发生次数](../metrics/bot-occurrences.md)和 [机器人页面查看次数](../metrics/bot-page-views.md). 您可以使用此维度及这两个量度来查看从其余报表中排除的机器人数据。

由于机器人报表与报表包的其余数据是分开的，因此此维度仅支持以下维度和量度：

* [页面](page.md)
* 基于时间的维度(例如， [日](day.md), [周](week.md)或 [月](month.md))
* [机器人发生次数](../metrics/bot-occurrences.md)
* [机器人页面查看次数](../metrics/bot-page-views.md)

将任何其他维度或量度与此维度一起使用不会返回数据。

## 使用数据填充此维度

如果已启用 [机器人规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)，则此维度会自动收集数据。 如果尚未启用 [!UICONTROL 机器人规则]，则此维度不会显示在Analysis Workspace中。

## 维度项

每个维度项目都列出与IAB或自定义机器人规则条件匹配的机器人的名称。
