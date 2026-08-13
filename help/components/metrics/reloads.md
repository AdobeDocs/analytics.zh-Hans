---
title: 重新载入
description: 重新加载页面的次数。
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
TQID: https://experienceleague.adobe.com/Jhm8-usZH-SLOzUvNIC3hdoKDMkm9T5mnCUeeMRga7E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 132
ht-degree: 21%

---

# 重新载入

“重新加载”[量度](overview.md)显示重新加载期间维度项存在的次数。 访客刷新其浏览器是触发重新载入的最常见方式。

## 如何计算此指标

此量度计算[页面](../dimensions/page.md)维度包含与上一次点击相同的值的点击数。

重新加载的概念适用于页面维度，无论您在报表中使用哪个维度。 例如，如果您使用[eVar1](../dimensions/evar.md)作为维度，使用“重新加载”作为量度，则该表会显示重新加载过程中每个eVar值（两个连续的页面值）出现的次数。 它不显示两个连续eVar1值存在的次数。
