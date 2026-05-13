---
title: 机器人名称
description: 与机器人规则匹配的机器人的名称。
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
TQID: https://experienceleague.adobe.com/lJn65s1JtcJf7WobPEeouvwlk7G5qd8XtgxvGLY-zu8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 7%

---

# 机器人名称

“机器人名称”[维度](overview.md)显示使用[机器人规则](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)检测到的机器人的名称。 这些规则可以是默认的IAB规则，也可以是您的组织配置的自定义机器人规则。 如果您希望详细了解哪些机器人访问了您的网站，或者哪些机器人产生的流量最多，则此功能非常有用。

将自动从所有Analytics报表中过滤符合[!UICONTROL 机器人规则]的点击，但此维度、[机器人发生次数](../metrics/bot-occurrences.md)和[机器人页面查看次数](../metrics/bot-page-views.md)除外。 您可以使用此维度和这两个量度来查看从其余报表中排除的机器人数据。

由于机器人报表与报表包的其他数据是分开的，因此此维度仅支持以下维度和量度：

* [页面](page.md)
* 基于时间的维度（例如，[Day](day.md)、[Week](week.md)或[Month](month.md)）
* [机器人发生次数](../metrics/bot-occurrences.md)
* [机器人页面查看次数](../metrics/bot-page-views.md)

将任何其他维度或量度与此维度一起使用不会返回数据。

## 使用数据填充此维度

如果您已启用[机器人规则](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)，则此维度会自动收集数据。 如果您尚未启用[!UICONTROL 机器人规则]，则此维度不会出现在Analysis Workspace中。

## 维度项目

每个维度项都列出与IAB或自定义机器人规则条件匹配的机器人的名称。
