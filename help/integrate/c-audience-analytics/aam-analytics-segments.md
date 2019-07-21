---
description: Analytics 和 Audience Manager 均使用区段。但是，Analytics 区段和 Audience Manager 区段并不完全一样。这些区别在某种程度上造成了 Analytics 和 Audience Manager 报表之间的差异。因此，当您开始使用这两种解决方案中的区段时，尝试了解这些差异是非常重要和有用的。
seo-description: Analytics 和 Audience Manager 均使用区段。但是，Analytics 区段和 Audience Manager 区段并不完全一样。这些区别在某种程度上造成了 Analytics 和 Audience Manager 报表之间的差异。因此，当您开始使用这两种解决方案中的区段时，尝试了解这些差异是非常重要和有用的。
seo-title: 了解Analytics和Audience Manager中的细分
title: 了解Analytics和Audience Manager中的细分
uuid: 13f7d1d7-3a3f-42f1-822e-8d3523999efa
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 了解Analytics和Audience Manager中的细分

Analytics 和 Audience Manager 均使用区段。但是，Analytics 区段和 Audience Manager 区段并不完全一样。这些区别在某种程度上造成了 Analytics 和 Audience Manager 报表之间的差异。因此，当您开始使用这两种解决方案中的区段时，尝试了解这些差异是非常重要和有用的。

## Audience Manager 区段 {#section_417DC4B5648547778A27E42CE1D09900}

Audience Manager 区段是一组符合由各个逻辑规则联结在一起的既定特征集的访客（用户 ID）。可通过四个标准来确定访客（用户 ID）是否属于 Audience Manager 中的某个区段：

* 针对区段本身设置的规则和构成每个区段的特征。这些规则定义用户 ID 必须符合或展示出他有资格访问区段的条件。
* 算法建模。根据算法建模和分析，有资格访问特定区段的用户可能也有资格访问其他区段。
* 生存时间 (TTL) 间隔。区段成员资格可能在设定的间隔后过期，也可以无限期延续下去。
* 回访间隔和频度。定义用户发生交互（特征实现）的时间和频度可帮助在站点、区域或特殊创作中基于真实（或虚构）兴趣级别创建区段。

Audience Manager 区段成员资格不是固定不变。用户可以进入或退出区段，具体取决于他们在当前时间点是否符合区段标准。这意味着 Audience Manager 区段的人口可能随时增加或减少。

Audience Manager 区段在 Analytics 中以受众的形式表示。

有关详细信息，请参阅[区段生成器中的特征和区段人口数据](https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html)和[信号、特征和区段](https://marketing.adobe.com/resources/help/en_US/aam/c_signal_trait_segment.html)。

## Analytics 区段 {#section_62EC584BB7134E10923BCBA7F9BD89A8}

Analytics 区段是一种对报表数据进行过滤的机制。过滤可能会在访客、访问或点击级别发生，而不是严格按照Audience Manager中的访客级别进行过滤。在比较 Analytics 区段和 Audience Manager 区段时须考虑以下几个重要因素：

* Analytics 区段所处理的数据不同于 Audience Manager 区段。在数据收集期间，Analytics 会对数据应用许多不同的后期处理步骤，而这些步骤对 Audience Manager 不可用。后期处理可包括 eVar 持久性、处理规则、查找（地理位置、移动设备）、VISTA 及许多其他内容。Audience Manager 通过服务器端转发（或 DIL）接收预处理数据。

   在将 Analytics 中基于永不过期维度的区段与 Audience Manager 中的相同区段进行比较时，常见数据会出现差异。例如，永不过期的 listVar 或促销 eVar。

   例如，如果 eVar = blue 并在 Analytics 中设置为永不过期，则 Analytics 中任何具有标准“eVar = blue”的区段将始终包含该访客。然而，在 Audience Manager 中，该访客在一定的时间段后可能会从具有类似定义的区段中流失。

* Analytics 区段比 AAM 区段具有更多的功能。Audience Manager 区段始终在访客级别进行评估。Analytics 区段可在访客、访问或点击级别（或这些级别的组合）进行定义。此外，Analytics 还支持一些 Audience Manager 没有的高级分段功能，如连续分段。
* 如前所述，Audience Manager 可以进入或退出区段，具体取决于他们在当前时间点是否符合区段标准。

   相反，在 Analytics 中，将根据报告的日期范围在区段中包含或排除访客。例如有一名访客在上月进行了一次购买。在 AAM 中，这名访客将包含在“购买者”区段中，而不考虑日期范围。在 Analytics 中，基于本月的报表将不会在区段中包含该访客。而基于本月和上月的报表将在区段中包含该访客。

有关详细信息，请参阅 [Analytics 分段指南。](https://marketing.adobe.com/resources/help/en_US/analytics/segment/)
