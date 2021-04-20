---
description: 您可以根据常见的错误拼写形式匹配值并更新这些值，以便它们能在报表中正确显示。
subtopic: Processing rules
title: 清理报告中的值
feature: Admin Tools
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
exl-id: 109005a3-2ea4-4b61-a733-d1019218ec56
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 100%

---

# 清理报告中的值

您可以根据常见的错误拼写形式匹配值并更新这些值，以便它们能在报表中正确显示。

为避免意外匹配其他值，请使用最严格的匹配选项。您可以根据变量（下例中的 prop1）运行报表并搜索您选择替换的术语，确保它没有匹配不需要的值。字符串比较区分大小写。

| 规则集 | 值 |
|---|---|
| 条件 | 如果 prop1 以 Shopping 开头 |
| 操作 | 将 prop1 的值覆盖为自定义值 Shopping |

例如：

![](assets/clean-up-values-in-report.png)
