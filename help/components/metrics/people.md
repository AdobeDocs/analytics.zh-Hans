---
title: 人员
description: 通常使用多个设备的独特个人的数量。
feature: Metrics
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '161'
ht-degree: 100%

---

# 人员

“人员”指标有以下两个版本。

对于那些未使用[跨设备分析](../cda/overview.md)的 [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=zh-Hans) 成员，“人员”指标是指报告中用来表示人数的统计推算计数。它不仅指“Device Co-op”识别的访客 ID 数量，还包括未经“Device Co-op”识别的设备数量。

在 [Cross-Device Analytics](../cda/overview.md) 虚拟报表包中，“人员”指标不是统计推导。而是在报表中识别的个人与属于某人的未识别的设备数之和。

如果在访问中识别了某个访客，则可能会将该访客计为 2 人（1 个未识别的人员和 1 个已识别的人员）。[重放](/help/components/cda/replay.md)根据报告时段、重放频率和成功率来减少这种重复计数。有关详细信息，请参阅[独特设备](unique-devices.md)。
