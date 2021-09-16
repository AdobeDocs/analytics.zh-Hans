---
title: 具有 Experience Cloud ID 的人员
description: 跨设备分析中具有Experience CloudID的人数。
source-git-commit: eaf0c3b751a5fbdc70ad6bef501dbf9e8400339c
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 21%

---

# 具有 Experience Cloud ID 的人员

“具有Experience CloudID的人员”是一个[跨设备分析](../cda/overview.md)量度，用于显示由Adobe使用[Experience CloudID服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)识别的[人员](people.md)数量。

## 如何计算此量度

考虑到每个[人员](people.md)（已识别或未识别），如果点击包含`mid`查询字符串（基于[`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hans) Cookie），则此量度会增加。

您可以创建计算量度`[People with ECID] ÷ [People]` ，以使用ID服务获取网站访客百分比。

有关Experience CloudID的重要性以及调试设置的详细信息，请参阅等效的非CDA量度[具有Experience CloudID的访客](visitors-with-ecid.md)。
