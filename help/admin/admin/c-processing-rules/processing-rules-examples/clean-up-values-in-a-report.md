---
description: 您可以根据常见的错误拼写形式匹配值并更新这些值，以便它们能在报表中正确显示。
subtopic: Processing rules
title: 清理报告中的值
topic: Admin tools
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: ht
source-wordcount: '113'
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

