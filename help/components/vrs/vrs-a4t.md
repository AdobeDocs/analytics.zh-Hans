---
description: 使用 A4T 和 Adobe Analytics 虚拟报表包时的特殊注意事项
title: 虚拟报表包和 Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
TQID: https://experienceleague.adobe.com/SIJbZiyHFtGFUrlno5-Kov3kDP4QOXREW00jyDsIGFI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 137
ht-degree: 100%

---

# 虚拟报表包和 Analytics for Target (A4T)

在 Adobe Target 上下文中使用虚拟报表包时，请考虑以下注意事项：

* 无法直接从 Target 中将数据发送到虚拟报表包，而只能将数据发送到实际报表包。
* 可以在虚拟报表包中报告 A4T 活动。 但是，A4T 数据仅限于与虚拟报表包区段（以及应用的任何其他区段）匹配的行。 例如，如果您为 EMEA 客户创建了一个虚拟报表包，则该虚拟报表包中的 A4T 数据仅反映 EMEA 客户的 Target 数据。
* 您无法将虚拟报表包中的区段发布回 Target 进行激活。
