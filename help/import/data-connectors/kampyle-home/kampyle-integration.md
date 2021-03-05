---
description: 将Kampyle数据连接器与Adobe Analytics结合使用。
title: 使用集成
uuid: b39c1334-ac0f-431b-a34f-27ff9b068e33
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 96%

---


# 使用集成{#using-the-integration}

部署后，您可以开始使用此集成提供的其他功能。通过执行以下操作，可在 Adobe Analytics 中从此集成获益。

>[!NOTE]
>
> 在 Adobe Analytics 报表中，可能需要 24-48 小时才能开始看到 Kampyle 响应数据。

## 混合反馈和现场行为数据{#mix-feedback-and-onsite-behavior-data}

您可以按反馈维度对 Reports &amp; Analytics 报表进行划分。

使用 Adobe Reports &amp; Analytics，您可以深入了解报表中可用的许多反馈维度。以下报表示例深入展示了特定的反馈类别，然后按反馈描述进行划分。来自 Reports &amp; Analytics 的量度（访问和客户服务查询）与来自 Kampyle 的量度（平均反馈等级）并排显示，以便轻松进行分析。

![](assets/feedback_category_report.png)

## 按反馈维度分段{#segment-by-feedback-dimension}

您可以根据反馈维度来创建区段。

此集成的主要功能是，根据 Kampyle 反馈维度来创建 Adobe Analytics 区段。例如，您可以构建一个仅包含提供的反馈等级为 1 或 2 的访问的区段。您可以将此区段命名为“反馈等级 - 低”。此区段定义将如下所示：

![](assets/segment_feedback.png)

然后，可将此区段应用于几乎任何报表 - 例如，此处显示的“每次访问逗留时间”报表。

![](assets/time_spent_per_visit.png)
