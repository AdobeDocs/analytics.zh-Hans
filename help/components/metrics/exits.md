---
title: 退出
description: 访问中最后一个值的实例。
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
TQID: https://experienceleague.adobe.com/KTpLeq4YjWgaFR-xcq1PBENAO5mb-wV-71BODlRGGlM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 88%

---

# 退出

*此帮助页介绍了“退出”如何充当量度。 有关“退出”如何充当维度的信息，请参阅[退出维度](../dimensions/exit-dimensions.md)。*

“退出”[量度](overview.md)显示给定维度项目被捕获为访问中的最后一个值的次数。 当您想进一步了解访客离开网站前最后看到的内容时，此量度非常有用。 查看维度的最后值，有助于您了解和优化访客在离开网站前获得的体验。

## 如何计算此指标

[访问](visits.md)结束后，将最近的维度项目记录为退出。 每次访问的每个维度只存在一个退出。 如果在以前的点击中设置了维度，则它不一定是访问的最后一次点击。 它是一个基于访问的量度；它可追溯应用于访问中的所有点击。

>[!TIP]
>
>如果您根据并非每次访问中均有设置的维度来查看此量度，则可以在 Analysis Workspace 中隐藏“未指定”维度项目。 单击过滤器图标，然后取消选中[!UICONTROL 包含未指定项（无）]。
