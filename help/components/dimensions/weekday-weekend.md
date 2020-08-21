---
title: 工作日/周末
description: 确定点击发生在工作日还是周末。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 68%

---


# 工作日/周末

“工作日/周末”维度提供有关点击发生在工作日（星期一至星期五）还是周末（星期六至星期日）的分析。点击时间基于[报表包所在时区](/help/admin/admin/general-acct-settings-admin.md)。

## 使用数据填充此维度

此维度可开箱即用于所有实施。如果报表包包含数据，则此维度有效。

## Dimension项

This dimension always contains exactly two dimension items: `"Weekday"` and `"Weekend"`. The dimension item `"Weekday"` applies to all hits Monday through Friday, while the dimension item `"Weekend"` applies to all hits on Saturday and Sunday.
