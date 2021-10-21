---
title: 人员
description: 通常使用多个设备的独特个人的数量。
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 639897682c9a28df7dc642dd7c68ad992fde40a9
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 80%

---

# 人员

“人员”指标有以下两个版本。

对于那些未使用[跨设备分析](../cda/overview.md)的 [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=zh-Hans) 成员，“人员”指标是指报告中用来表示人数的统计推算计数。它不仅指“Device Co-op”识别的访客 ID 数量，还包括未经“Device Co-op”识别的设备数量。

在 [Cross-Device Analytics](../cda/overview.md) 虚拟报表包中，“人员”指标不是统计推导。而是在报表中识别的个人与属于某人的未识别的设备数之和。

如果访客在访问中被识别，则该访客可以计为2人（1个未识别人员和1个已识别人员）。 [重播](/help/components/cda/replay.md) 根据报告时间范围、重播频率和成功率缓解此重复计数。 有关详细信息，请参阅[独特设备](unique-devices.md)。
