---
title: 未找到页面（指标）
description: 包含错误的点击数。
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
TQID: https://experienceleague.adobe.com/V5jVT8wh71qMrchQmmM6c4EMofHPUEI388TmAf7Zf6M
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 38%
---
# 页面未找到

>[!BEGINSHADEBOX]

*此帮助页介绍了“页面未找到”如何作为维度使用。 有关它如何作为维度使用的更多信息，请参阅[页面未找到](../dimensions/pages-not-found.md)维度页面。*

>[!ENDSHADEBOX]

“页面未找到”[量度](overview.md)显示访客遇到错误时设置或保留维度的点击次数。 当您想要查看哪些页面或URL包含错误消息（例如404）时，此量度很有价值。 然后，您可以将此信息传递给Web开发团队，他们可确定错误的原因并进行修复。

## 如何计算此指标

此量度计算 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 变量等于 `"errorPage"` 值的所有点击数。 它是[页面未找到](../dimensions/pages-not-found.md)维度的等效量度。
