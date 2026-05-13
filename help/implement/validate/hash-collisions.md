---
title: 哈希冲突
description: 描述什么是哈希冲突以及它是如何体现的。
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
TQID: https://experienceleague.adobe.com/yjYX-h-8jJA7k-jzRMOJ0l2BxN5-no2kCfySkGYss8w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 539
ht-degree: 5%

---

# 哈希冲突

Adobe Analytics中的维度收集字符串值。 这些字符串有时长达数百个字符，有时则较短。 为了提高性能，在报表时间处理中不会直接使用这些字符串值。 相反，为每个值计算散列，产生大小一致的标识符。 对于大多数字段，该值会在进行哈希处理之前转换为小写，从而减少唯一值的总数。 所有报表都基于这些哈希值运行，这会显着提升其性能。

Adobe Analytics为每个变量维护一个单独的哈希表，并且每个月都会重建每个表。 在这些表中的任一表中，两个不同的源值偶尔会生成相同的哈希，称为&#x200B;*哈希冲突*。

哈希冲突可如下所示显示在报表中：

* 如果您查看一段时间的报表并看到意外的尖峰，则该变量的多个唯一值可能会使用相同的哈希。
* 如果您使用区段并看到意外值，则意外维度项可能会使用与您的区段匹配的其他维度项相同的哈希。

## 哈希冲突发生概率

Adobe Analytics对大多数维度使用32位哈希，这意味着可能有2<sup>32</sup>个哈希组合（约43亿）。 根据唯一值的数量，遇到哈希冲突的大致概率如下。 这些赔率基于单个维度单个月。

| 唯一值 | 赔率 |
| --- | --- |
| 1,000 | 0.01% |
| 10,000 | 1% |
| 50,000 | 26% |
| 100,000 | 71% |

与[生日悖论](https://en.wikipedia.org/wiki/Birthday_problem)类似，哈希冲突出现的可能性随唯一值数量的增加而急剧增加。 至少100万个唯一值，该维度可能至少有100个哈希冲突。

## 缓解哈希冲突

无法完全消除哈希冲突，但可以减轻其对报表的影响。 大多数哈希冲突都发生在两个不常见的值中，这些值对报表没有任何实际影响。 即使哈希与某个通用值和不通用值发生冲突，结果也几乎可以忽略。 但是，在极少数情况下，当两个常用值遇到哈希冲突时，可以清楚地看到其影响。 Adobe建议采取以下操作来降低它在报表中的影响：

* **更改日期范围**：哈希表每月更改。 将日期范围更改为跨越另一个月，可能会为每个值赋予不同的哈希值，而不会产生冲突。 它通常是清除特定报表中可见异常的最快方式。
* **减少唯一值的数量**：您可以调整实施或使用[处理规则](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)来帮助减少维度收集的唯一值的数量。 例如，如果您的维度收集URL，则可以剥离查询字符串或协议。
* **使用[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)或[数据馈送](/help/export/analytics-data-feed/data-feed-overview.md)**：这些工具不依赖哈希表。
* **移动到[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html)**： Customer Journey Analytics没有哈希层，并且[维度没有基数限制](https://experienceleague.adobe.com/docs/analytics-platform/using/components/dimensions/high-cardinality.html)。 如果哈希冲突或[[!UICONTROL 低流量]](/help/technotes/low-traffic.md)经常影响您的报表，请考虑转移到此产品。

>[!MORELIKETHIS]
>
>* Adobe Analytics中的[[!UICONTROL 低流量]值](/help/technotes/low-traffic.md)
>* [处理规则概述](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
