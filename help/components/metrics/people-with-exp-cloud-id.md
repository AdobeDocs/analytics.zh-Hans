---
title: 具有 Experience Cloud ID 的人员
description: Cross-Device Analytics 中具有 Experience Cloud ID 的人数。
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
TQID: https://experienceleague.adobe.com/w85poHKHnDYQ0iTItr2r26q1aRpN50AsdYzg6v82Jpk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 137
ht-degree: 85%

---

# 具有 Experience Cloud ID 的人员

“具有 Experience Cloud ID 的人员”是一个 [Cross-device analytics](../cda/overview.md) 指标，它表示 Adobe 使用 [Experience Cloud ID 服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)识别的[人员](people.md)的数量。

## 如何计算此指标

考虑到每个[人员](people.md)（已识别或未识别），如果点击包含`mid`查询字符串（基于[`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hans) Cookie），则此[指标](overview.md)将增加。

可创建计算指标 `[People with ECID] ÷ [People]` 以使用 ID 服务获取您网站访客所占的百分比。

有关 Experience Cloud ID 的重要性和调试设置的详细信息，请查看等效的非 CDA 指标[具有 Experience Cloud ID 的访客](visitors-with-ecid.md)。
