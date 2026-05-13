---
description: Power BI 最佳实践。
title: 最佳实践
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
TQID: https://experienceleague.adobe.com/WXvRDft1TRz5qM9R8Psz-Yp2qY-AL-SrrXgXWRx55N0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 31%

---

# 最佳实践

{{legacy-arb}}

## 在 Power BI 可视化效果中保留引用

创建请求后，该请求在Power BI中将始终具有相同的引用。 但是，如果您删除请求，则为同一维度创建的新请求将使用该引用。

如果您在工作簿中删除请求，请确保 Power BI 中没有任何可视化指向该请求，否则，相应可视化将中断。

* 如果可能，请不要删除在Report Builder中创建的请求
* 如果您在Report Builder上确实删除了请求，请务必也删除Power BI中的相应可视化图表。
* 如果您不确定：请删除您不再需要的请求，然后重新发布，然后转到Power BI以查看哪些可视化图表已损坏
