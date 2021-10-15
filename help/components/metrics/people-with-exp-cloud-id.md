---
title: 具有 Experience Cloud ID 的人员
description: Cross-Device Analytics 中具有 Experience Cloud ID 的人数。
source-git-commit: eaf0c3b751a5fbdc70ad6bef501dbf9e8400339c
workflow-type: ht
source-wordcount: '130'
ht-degree: 100%

---

# 具有 Experience Cloud ID 的人员

“具有 Experience Cloud ID 的人员”是一个 [Cross-device analytics](../cda/overview.md) 指标，它表示 Adobe 使用 [Experience Cloud ID 服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)识别的[人员](people.md)的数量。

## 如何计算此指标

其中考虑每个（已识别或未识别）[人员](people.md)，如果点击包含 `mid` 查询字符串（基于 [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hans) Cookie），则此指标增大。

可创建计算指标 `[People with ECID] ÷ [People]` 以使用 ID 服务获取您网站访客所占的百分比。

有关 Experience Cloud ID 的重要性和调试设置的详细信息，请查看等效的非 CDA 指标[具有 Experience Cloud ID 的访客](visitors-with-ecid.md)。
