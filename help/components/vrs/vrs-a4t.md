---
description: 使用 A4T 和 Adobe Analytics 虚拟报表包时的特殊注意事项
title: 虚拟报表包和 Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 100%

---

# 虚拟报表包和 Analytics for Target (A4T)

在 Adobe Target 上下文中使用虚拟报表包时，请考虑以下注意事项：

* 无法直接从 Target 中将数据发送到虚拟报表包，而只能将数据发送到实际报表包。
* 可以在虚拟报表包中报告 A4T 活动。但是，A4T 数据仅限于与虚拟报表包区段（以及应用的任何其他区段）匹配的行。例如，如果您为 EMEA 客户创建了一个虚拟报表包，则该虚拟报表包中的 A4T 数据仅反映 EMEA 客户的 Target 数据。
* 您无法将虚拟报表包中的区段发布回 Target 进行激活。
