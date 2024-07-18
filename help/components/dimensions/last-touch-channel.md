---
title: 最近联系渠道
description: 访客参与到期期间的最新营销渠道。
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 90%

---

# 最近联系渠道

“最近联系渠道”[维度](overview.md)报告访客在该访客的参与期（默认为30天）内与之匹配的最新营销渠道。 在了解哪些营销渠道可将流量引到您的网站并促成转化，从而使您将营销工作重点放在最有效的领域方面，此维度具有重要价值。

## 使用数据填充此维度

此维度直接引用您在[营销渠道管理器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)中定义的渠道名称。

发送到 Adobe 数据收集服务器的每次点击均通过报表包的营销渠道处理规则运行。它按数字顺序遍历每个规则，直到找到匹配项为止，在该匹配项中，营销渠道与点击关联。最近联系渠道会随着访客一直保留，直到访客不访问网站的时间超过访客参与期（默认为 30 天）为止。

如果要将此维度设置为特定值，必须执行以下步骤：

* 在报表包设置下的“营销渠道管理器”中，将所需的维度项目设置为渠道。
* 设置包含点击所需条件的营销渠道处理规则。
* 访客对网站的点击，必须符合营销渠道处理规则中所述的条件。

## 维度项目

维度项目包括营销渠道管理器中的任何渠道名称。默认情况下，这些值包括 `"Paid search"`、`"Natural search"`、`"Display"`、`"Email"`、`"Affiliate"`、`"Direct"`、`"Internal"`、`"Social networks"` 和 `"Referring domains"`。您可以在营销渠道管理器中添加或删除渠道，但这会影响此维度的值。
