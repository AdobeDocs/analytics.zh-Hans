---
title: 登录
description: 访问中第一个值的实例。
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
TQID: https://experienceleague.adobe.com/H3LE0wm2uDL3-pILbvOXvccAJQdo5o9X3uHJ4xZe7UU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 89%

---

# 登录

*此帮助页介绍登入次数如何作为维度使用。 有关登入次数如何作为维度使用的信息，请参阅[登入维度](../dimensions/entry-dimensions.md)。*

“登入次数”[量度](overview.md)显示给定维度项目在访问中被捕获为第一个值的次数。 当您想要进一步了解访客对您网站的第一印象时，此量度很有帮助。 查看维度的第一个值可以帮助您了解和优化新访客获得的体验。

## 如何计算此指标

对于给定维度，将访问中看到的第一个维度项目记录为一个条目。 每次访问每个维度只存在一个条目。 如果最初未设置维度，它不一定是访问的第一次点击。 它是一个基于访问的量度；一旦它与某个维度项目关联，就会在访问的其余时间持续。

>[!TIP]
>
>如果您根据并非每次访问中均有设置的维度来查看此量度，则可以在 Analysis Workspace 中隐藏“未指定”维度项目。 单击过滤器图标，然后取消选中[!UICONTROL 包含未指定项（无）]。
