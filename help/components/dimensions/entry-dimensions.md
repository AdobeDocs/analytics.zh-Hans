---
title: 登入维度
description: 列出登入维度及其使用情况。
keywords: 登入页面，登入网站区域，登入服务器，登入自定义洞察
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
TQID: https://experienceleague.adobe.com/6a6Xy8SEqjcnuB1Acbwkesw6OA7Nggld5ppWtjYaj5k
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
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 292
ht-degree: 75%

---

# 登入维度

*此帮助页介绍登入次数如何作为[维度](overview.md)使用。 有关登入次数如何作为量度使用的信息，请参阅[登入次数](../metrics/entries.md)量度。*

登入维度基于[访问](../metrics/visits.md)。 它们记录第一个维度项目，并在该访问的整个过程中保留该值。 登入维度可用于在“报表包”设置中的[流量变量](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)下启用路径的所有变量。

>[!TIP]
>如果您要查看基于访问的首次点击而不是访问中看到的第一个值的数据，则可以使用[区段](/help/components/segmentation/seg-overview.md)。 使用[点击深度](hit-depth.md)等于1的点击容器，然后将该区段与所需变量一起使用。

## 使用数据填充登入维度

给定的条目[维度](overview.md)基于其关联的流量变量。 如果非登入变量包含数据，则其关联的登入维度也包含数据。 如果流量变量包含数据，则不需要对登入维度进行更改。

## 维度项目

由于登入变量通常基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。 给定登入维度中的值与其关联的非登入维度中的维度项目相匹配。 例如，“登入页面”维度中的维度项目包含“页面”维度中的类似维度项目。

## 原始登入页面

“原始登入页面”维度的操作方式与其他登入维度不同。 它不保留给定访问的登入页面，而是保留该访客 Cookie 的整个生命周期中的第一个登入页面。 例如，如果您登陆 `https://example.com/page4` 首次访问该网站，一年后登陆 `https://example.com/store` 时，“原始登入页面”维度会将 `https://example.com/page4` 列为维度项目。
