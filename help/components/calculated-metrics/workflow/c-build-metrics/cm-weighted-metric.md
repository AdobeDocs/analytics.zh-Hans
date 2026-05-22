---
description: 了解过滤和加权量度的示例。
title: 过滤和加权量度
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
TQID: https://experienceleague.adobe.com/Euk3sI0-AYtfmpEbL-8gfWU4HcFE6kGO6QGgctZbvig
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 158
ht-degree: 9%

---

# 过滤和加权度量

本文显示了过滤和加权量度的示例。

## 过滤的跳出率

此简单的已过滤量度仅显示访问次数超过100次的页面的跳出率：

![已过滤的跳出率](assets/filtered-bounce-rate.png){zoomable="yes"}

请记住，此公式取决于一致的时间范围。 如果只运行一天报表，则任何超过20次访问的页面都值得查看。 如果将其运行一个月，则可能需要该过滤器包含更多访问。

## 带百分位数的过滤跳出率

此过滤器在按访问量排序时，显示排名前30%页面的跳出率。

![已筛选的跳出率（百分点为](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}）

## 加权跳出率

假设您通常希望按跳出率排序，但访问次数较高的页面在列表中应该排在较高的位置。 您可以创建与如下所示类似的加权跳出率：

![](assets/weighted-bounce-rate.png)
