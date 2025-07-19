---
title: 重新载入
description: 重新加载页面的次数。
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
source-git-commit: c9b7c32adfb44a04ab792d12ca049106b3009710
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 21%

---

# 重新载入

“重新加载”[量度](overview.md)显示重新加载期间维度项存在的次数。 访客刷新其浏览器是触发重新载入的最常见方式。

## 如何计算此量度

此量度计算[页面](../dimensions/page.md)维度包含与上一次点击相同的值的点击数。

重新加载的概念适用于页面维度，无论您在报表中使用哪个维度。 例如，如果您使用[eVar1](../dimensions/evar.md)作为维度，使用“重新加载”作为量度，则该表会显示重新加载过程中每个eVar值（两个连续的页面值）出现的次数。 它不显示两个连续eVar1值存在的次数。
