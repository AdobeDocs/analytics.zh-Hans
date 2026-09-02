---
title: Activity Map 区域
description: 您网站上被点击的区域。
feature: Dimensions
role: User, Admin
exl-id: e262e537-ce73-492a-8ab3-b88cd77cb8c5
TQID: https://experienceleague.adobe.com/mmLp5-dgKGeovIOMPZxliyhfbpUSMLXca-3Qs6QA0SA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 5%

---

# Activity Map 区域

“Activity Map地区”[维度](overview.md)显示您网站上点击次数最多的地区。 当您要比较网站总体区域而不是单个链接的点击量时，此维度很有用。 此外，它对于站点中提供动态内容的区域也很有用。 例如，如果您的头版页面包含旋转的新闻文章，则很难使用[Activity Map链接](activity-map-link.md)维度，因为链接文本会不断变化。 但是，由于这些链接使用相同的区域，因此您可以分析该区域性能，即使单个链接每天可能会发生更改。

## 使用数据填充此维度

此维度从[上下文数据变量](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.region`中检索数据。 如果您的实施使用[Activity Map](/help/analyze/activity-map/overview.md)，则此上下文数据变量会在单击链接时自动收集数据。

对于已单击的给定链接，请检查父DOM元素中的以下内容（按顺序）：

* [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md)设置的属性中的一个值 — 默认设置为`id`属性
* 属性`role="region"`时`aria-label`属性中的值
* 语义元素`<header>`、`<main>`、`<footer>`或`<nav>`（仅限Web SDK）

如果父DOM元素不符合上述任何条件，则搜索将向DOM层次结构中递回地继续进行。 如果未找到匹配的元素，则返回值`BODY`。

## 维度项目

Dimension项目包括您在网站上标记的地区。 特定区域值取决于使用的属性以及是否存在语义HTML元素。
