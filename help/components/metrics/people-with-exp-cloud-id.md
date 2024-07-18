---
title: 具有 Experience Cloud ID 的人员
description: Cross-Device Analytics 中具有 Experience Cloud ID 的人数。
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 83%

---

# 具有 Experience Cloud ID 的人员

“具有 Experience Cloud ID 的人员”是一个 [Cross-device analytics](../cda/overview.md) 指标，它表示 Adobe 使用 [Experience Cloud ID 服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)识别的[人员](people.md)的数量。

## 如何计算此指标

考虑到每个[人员](people.md)（已识别或未识别），如果点击包含`mid`查询字符串（基于[`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hans) Cookie），则此[指标](overview.md)将增加。

可创建计算指标 `[People with ECID] ÷ [People]` 以使用 ID 服务获取您网站访客所占的百分比。

有关 Experience Cloud ID 的重要性和调试设置的详细信息，请查看等效的非 CDA 指标[具有 Experience Cloud ID 的访客](visitors-with-ecid.md)。
