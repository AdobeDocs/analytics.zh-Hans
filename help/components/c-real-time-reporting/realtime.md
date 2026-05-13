---
description: 实时显示网页流量并对页面查看次数进行排名。 提供制定业务决策所需的可操作数据。
title: 实时报表概述
topic-fix: Reports
feature: Real-time
exl-id: 056235bc-42ea-4118-aa54-bc7666044fe3
TQID: https://experienceleague.adobe.com/2QizNDKGlAUqX7IbHANm-nGMicLXDfKSnl7nYGkETxQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 633
ht-degree: 19%

---

# 实时报表概述

实时报表可实时显示网页流量，并对页面查看次数进行排名。 提供制定业务决策所需的可操作数据。

>[!NOTE]
>
>实时报表不需要额外实施或添加标记。 它利用您现有的Adobe Analytics实施。 要配置实时报表，请参阅[实时报表配置](/help/admin/tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)。

## 访问实时报表

1. 在 Analysis Workspace 中，选择&#x200B;[!UICONTROL **工作区**]&#x200B;选项卡。

1. 在页面左侧的&#x200B;**[!UICONTROL 模板]**&#x200B;下，选择&#x200B;[!UICONTROL **Adobe模板**]。

1. 选择&#x200B;[!UICONTROL **参与**] > **[!UICONTROL 实时]**。

## 了解实时报表

实时回答以下问题：我的网站有何趋势，为什么？ 它使您作为营销人员能够快速响应并主动管理营销内容和营销活动的效果。 所报告的实时数据的延迟时间不到两分钟，并且会逐分钟自动更新。

![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report-realtime.png)

仪表板包括Adobe Analytics高频指标和网站分析，用于直观地报告动态新闻和零售网站的流量和页面查看趋势。 “实时”可了解您的数据在收集的几秒内从分钟到分钟的趋势。 它收集数据并将其流式传输到自动更新UI中，从而实时关联并跟踪内容和某些转化。

其中两种最常见的使用方案包括：出版商希望随着用户活动变化而提升/降低故事的播放量，以及营销人员希望跟踪新产品线的发布情况。

作为管理员，您可以

* 使用现有的维度、分类和量度，为每个报表包创建最多3个实时报表。 使用辅助尺寸与主要尺寸相关联（或划分）。
* 每个报告添加3个维度（或分类）（一个主要和两个次要），以及1个网站范围的量度。
* 使用任意自定义事件、购物车事件或实例。
* 查看长达2小时的历史实时数据并修改此设置：

   * 前15分钟：1分钟粒度
   * 最近30分钟：1分钟粒度
   * 最近1小时：2分钟粒度
   * 最近2小时：4分钟粒度

* 例如，将上周的值与去年的值（以及今天的总数）进行比较。

请记住，不支持eVar（转化量度），因为没有持久性的概念。 虽然您可以选择转化量度，但只有在将这些量度设置为与维度位于同一页面上时，转化量度才有效。 有关详细信息，请参阅[设置实时报表](/help/components/c-real-time-reporting/t-realtime-admin.md)中捕获的警告消息。

设置和查看实时报表仅限管理员或“所有报表访问”和“高级报表”权限组中的任何用户。 但是，实时会尊重权限。 例如，如果您无权查看收入，则将无法查看包含收入数据的实时报表。

## 由A4T配置导致的数据滞后 {#latency-a4t}

在 Adobe [!DNL Target] 中启用 A4T 集成后，您在 Adobe Analytics 中会额外经历 5 至 10 分钟的滞后。 这额外增加的滞后可将 Analytics 和 [!DNL Target] 中的数据存储到同一个点击上，从而允许您按页面和网站区域来细分测试。

这一增长反映在所有Adobe Analytics服务和工具中，包括实时流和实时报表，并适用于以下场景：

* 对于实时流、实时报表和API请求以及流量变量的当前数据，只有具有补充数据ID的点击才会延迟。
* 对于有关转化量度、最终数据和数据馈送的当前数据，所有点击将额外延迟5至7分钟。

请注意，实施身份标识服务之后，即使您还未完全实施 A4T 集成，滞后的时间也会开始增加。
