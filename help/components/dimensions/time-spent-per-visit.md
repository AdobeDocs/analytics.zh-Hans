---
title: 每次访问逗留时间（维度）
description: 访问逗留的总时间。
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
TQID: 'https://experienceleague.adobe.com/jtBAAq-Pe0PyCQJPwvzwnK9eLv14CxTvrVQP4lvWy7k'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 304
ht-degree: 92%

---

# 每次访问逗留时间

*此帮助页介绍“每次访问逗留时间”如何作为各自的[维度使用](overview.md)。 有关更多信息，请参阅[每次访问逗留时间](../metrics/time-spent-per-visit.md)量度。*

“每次访问逗留时间”维度记录访客在整个访问中所花费的时间。 它使用以下步骤来衡量计算：

1. 查看访问的首次点击的时间戳。
2. 对比访问中此次点击与最后一次点击的时间戳。
3. 这两次点击之间经过的时间，即为对应的逗留时间。

当您想要了解访客与您网站交互时长的整体情况时，这些维度很有价值。

>[!TIP]
>
>至少需要一次访问中的两次点击才能衡量逗留时间。 包含单次点击的访问不会显示在此维度中。

此维度基于访问，这意味着该值适用于访问中的每次点击，并且不会更改。 可将此维度与[页面逗留时间](time-spent-on-page.md)进行比较，后者是一个基于点击的维度。

此维度与[网站平均逗留时间](../metrics/average-time-on-site.md)和[每次访问逗留时间](../metrics/time-spent-per-visit.md)量度相关。

## 使用数据填充此维度

这些维度可开箱即用于所有实施。 如果报表包包含数据，则这些维度有效。

## 维度项目

每次访问逗留时间存在多个维度：

* **每次访问逗留时间 - 分段统计**：分段统计时间。 维度项目介于 `"Less than 1 minute"` 到 `"More than 15 hours"` 之间。 访问时间一般不超过 12 小时；但是，如果使用带有时间戳的点击或数据源，访问时间可能超过 12 小时。
* **每次访问逗留时间 - 粒度**：每个秒数都是一个唯一的维度项目。 此维度在Data Warehouse中不可用。

有关逗留时间的更多常规信息，请参阅[逗留时间概述](../metrics/time-spent.md)。
