---
description: Analytics和Audience Manager都使用区段。 但是，Analytics区段与Audience Manager区段不完全相同。 这些差异在一定程度上造成了您在Analytics和Audience Manager报表中看到的差异。 因此，当您开始使用这两个解决方案中的区段时，尝试了解这些差异是重要而有用的。
title: 了解 Analytics 和 Audience Manager 中的区段
feature: Audience Analytics
exl-id: 2bc662e7-7552-41e1-9d4a-bc7aa81b8c1d
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 9%

---

# 了解 Analytics 和 Audience Manager 中的区段

Analytics和Audience Manager都使用区段。 但是，Analytics区段与Audience Manager区段不完全相同。 这些差异在一定程度上造成了您在Analytics和Audience Manager报表中看到的差异。 因此，当您开始使用这两个解决方案中的区段时，尝试了解这些差异是重要而有用的。

## Audience Manager 区段 {#aam-segments}

Audience Manager区段是指一组符合由逻辑规则连接的一组已定义特征的访客（用户ID）。 在Audience Manager中，有四个标准可确定访客（用户ID）是否属于区段：

* 针对区段本身设置的规则以及构成每个区段的特征。 这些规则定义了用户ID必须符合或必须满足哪些条件才能符合区段的资格。
* 算法建模。根据算法建模和分析，符合特定区段资格的用户可能有资格使用其他区段。
* 存留时间(TTL)间隔。 区段成员资格可在设定的间隔后过期或无限期继续。
* 回访间隔和频度。 定义用户进行交互（特征实现）的时间和频率有助于根据网站、区域或特定创意内容的实际（或感知）兴趣级别创建区段。

Audience Manager区段会员资格不稳。 用户可以输入或退出区段，具体取决于他们在当前时间点是否符合区段标准。 这意味着Audience Manager区段的群体可能会随着时间的推移而增加或减少。

Audience Manager区段在Analytics中表示为受众。

有关详细信息，请参阅区段生成器[中的](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=zh-Hans)特征和区段人口数据[信号、特征和区段](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=zh-Hans)。

## Analytics 区段 {#analytics-segments}

Analytics区段是一种对报表数据进行过滤的机制。 不同于在 Audience Manager 区段上只能执行访客级别的过滤，在 Analytics 区段上，您可以按照访客、访问或点击级别进行过滤。将Analytics区段与Audience Manager区段进行比较时，需要考虑以下几个重要因素：

* Analytics区段运行的数据集与Audience Manager区段的数据集不同。 在数据收集期间，Analytics会对Audience Manager不可用的数据应用许多不同的后处理步骤。 后处理可能包括eVar持久性、处理规则、查找（地理位置、移动设备）、VISTA和许多其他。 Audience Manager通过服务器端转发(或DIL)接收预处理的数据。

  将基于Analytics中永不过期的维度的区段与Audience Manager中的相同维度进行比较时，会出现常见的数据差异。 例如，永不过期的listVar或推销eVar。

  例如，如果 eVar = blue 并在 Analytics 中设置为永不过期，则 Analytics 中任何具有标准“eVar = blue”的区段都将始终包含该访客。而在Audience Manager中，该访客可能会在一段时间后退出类似定义的区段。

* Analytics区段比Adobe Audience Manager区段具有更多的功能。 Audience Manager区段始终在访客级别进行评估。 可以在访客、访问或点击级别（或这些级别的组合）定义Analytics区段。 此外，Analytics支持Audience Manager不具备的高级分段功能，例如顺序分段。

* 如前所述，Audience Manager访客可以进入或退出区段，具体取决于他们当前时间点是否符合区段标准。

  反之，在Analytics中，将根据报表日期范围在区段中包含或排除访客。 例如，上个月一位访客购买了商品。 在Adobe Audience Manager中，该访客将包含在“购买者”区段中，而不考虑日期范围。 在Analytics中，基于当月的报表不会在该区段中包含访客。 但是，基于本月和上个月的报表将包括该区段中的访客。

有关详细信息，请参阅[Analytics分段指南](/help/components/segmentation/seg-home.md)。
