---
description: 将Dynamic Signal VoiceStorm数据连接器与Adobe Analytics结合使用。
title: 使用集成
uuid: c902a868-20a7-42df-8a79-8e154608f299
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 97%

---


# 使用集成{#using-the-integration}

部署后，您可以开始使用此集成提供的其他功能。

**注意**：在 Adobe Analytics 报表中，可能需要 24-48 小时才能开始看到一些 Dynamic Signal 数据。

通过执行以下操作，可在 Adobe Analytics 中从此集成额外获益。

## 按 Dynamic Signal 维度查看流量和转化量度{#viewing-traffic-and-conversion-metrics-by-dynamic-signal-dimensions}

Adobe Analytics 中的报表示例。

此集成提供了新的维度，这些维度可用于 Adobe Analytics 报表。以下报表是对按“文章标题”划分的“访问量”和转化量度“注册量”进行分析的示例。

![](assets/examplereport.png)

## 按 Dynamic Signal 维度划分{#segmenting-by-dynamic-signal-dimensions}

基于 Dynamic Signal 维度的区段示例。

此集成的主要功能是，根据集成的报表维度来创建 Adobe Analytics 区段。例如，您可以构建一个仅包含来自特定 VoiceStorm 社区的访问的区段。您可以将此区段命名为“由超级粉丝驱动的访问”。此区段定义可能如下所示。

![](assets/segment1.png)

![](assets/segment2.png)

## 集成的报表维度{#integrated-reporting-dimensions}

列出此集成中包含的 Dynamic Signal 报表维度。

| 维度 | 描述 |
|---|---|
| 渠道类型 | 用户分享社区帖子的社交网络（或博客平台）。用户可能会在多个渠道上分享帖子。点击量和其他活动将按渠道进行分段。此字段会显示 Facebook、Twitter 等，以便您查看哪种渠道类型有助于提升活动效果。 |
| 文章 ID | 文章 ID 唯一标识 Dynamic Signal 社区中的每一条内容。 |
| 源类型 | 此字段指示帖子是由“会员”还是“品牌”创建的。请注意，无论哪种情况，均可在应用程序中手动创建内容或从外部馈送中导入内容。 |
| 用户名 | 在社交网络上分享帖子，从而生成对您网站的点进次数的用户。 |
| 源 ID | 源 ID 唯一标识所分享帖子的创建者（或作者）。通常是特定会员或外部馈送。 |
| 用户 ID | 用户 ID 唯一标识 Dynamic Signal 社区中的用户（即会员）。在这种情况下，用户是在社交网络上分享帖子的分享者。 |
| 源名称 | 源是所分享帖子的创建者（或作者）。大多数情况下是社区会员或外部馈送。 |
| 文章标题 | 生成对您网站的点击量的所分享帖子的标题。 |
| 社区名称 | 您的 Dynamic Signal 社区的名称。 |

