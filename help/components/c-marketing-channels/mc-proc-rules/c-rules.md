---
title: 营销渠道的处理规则
description: 营销渠道处理规则决定访客点击是否符合分配到渠道的标准。这些规则处理访客在网站上的每次点击。当规则不符合渠道标准时，或者如果规则配置不正确，系统会将该点击分配到“未识别渠道”。
translation-type: tm+mt
source-git-commit: ea4d9e6c9396032fe323de594cb43eecbf97aa15

---


# 营销渠道的处理规则

营销渠道处理规则决定访客点击是否符合分配到渠道的标准。这些规则处理访客在网站上的每次点击。当规则不符合渠道标准时，或者如果规则配置不正确，系统会将该点击分配到“未识别渠道”。

以下是创建规则的重要指示：

* 将规则按所需处理顺序排序。
* 在列表末尾，纳入一条通用规则，如“其他”。该规则用于识别外部流量而非内部流量。

   请参阅[未识别渠道](/help/components/c-marketing-channels/mc-faq/c-faq.md#no-channel-identified)。

> [!NOTE] 尽管这些规则不会影响营销渠道以外的报表，但却会影响营销渠道数据收集。通过这些规则收集的数据全部为永久性数据，数据收集后再更改的规则不具有可回溯性。It is strongly recommended to review and consider all circumstances before saving [!UICONTROL Marketing Channel Processing Rules] to mitigate data being collected in incorrect channels.

## 先决条件

* 查看营销渠道入 [门中的概念信息](/help/components/c-marketing-channels/getting-started/c-getting-started-mchannel.md)。
* 创建一个或更多渠道，以便您将规则分配给它们。See [Add marketing channels.](/help/components/c-marketing-channels/mark-channel-mgr/c-channels.md)
