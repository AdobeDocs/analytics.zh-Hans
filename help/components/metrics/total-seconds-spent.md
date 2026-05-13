---
title: 所用总秒数
description: 在维度项目上花费的总时间（秒）。
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
TQID: https://experienceleague.adobe.com/FQ5FGTOKnJph7C0jWwbcAHA31yUwz7ewQRPykUD6R0E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 90%

---

# 所用总秒数

“所用总秒数”[指标](overview.md)显示访客在给定维度项目上所花费的总时间（秒）。 当您希望了解在给定维度项目上所花费的原始时间，而不是像其他逗留时间量度提供的平均值时，此量度非常有用。

在 Report Builder 中，此量度称为“总逗留时间”。

## 如何计算此指标

此量度会使用以下步骤来衡量计算：

1. 对于给定点击，请查看时间戳。
2. 对比访问中此次点击与下一次点击的时间戳。 页面查看和链接跟踪点击都非常重要。
3. 两次点击之间经过的秒数，对维度项目有贡献。

持久化变量（例如 [eVar](../dimensions/evar.md)）计入总逗留时间（秒）。 流量变量（例如 [prop](../dimensions/prop.md)）包括后续链接跟踪调用所花费的秒数。

>[!TIP]
>
>不会测量访问的最后一次点击期间的逗留时间，因为没有后续的图像请求来测量经过的时间。 此概念还适用于包含单次点击（跳出）的访问。

有关逗留时间的更多常规信息，请参阅[逗留时间概述](time-spent.md)。
