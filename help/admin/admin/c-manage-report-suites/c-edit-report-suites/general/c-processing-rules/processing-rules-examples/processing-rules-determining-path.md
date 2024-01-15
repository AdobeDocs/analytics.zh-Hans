---
description: 您可以将 eVar 的值复制到一个属性来启用路径分析。
subtopic: Processing rules
title: 通过将 eVar 值复制到 prop 来确定路径
feature: Admin Tools
role: Admin
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 100%

---

# 通过将 eVar 值复制到 prop 来确定路径

您可以将 eVar 的值复制到一个属性来启用路径分析。

在设置值时，左侧的变量接收来自右侧变量的值（即使是空值）。

| 规则集 | 值 |
|---|---|
| 条件 | 无（始终执行） |
| 操作 | 使用 eVar1 覆盖 Prop1 的值 |

仅在 Prop1 未包含值时，才可以修改此规则来设置 Prop1 的值，如下所示：

| 规则集 | 值 |
|---|---|
| 条件 | 未设置 Prop1 时 |
| 操作 | 使用 eVar1 覆盖 Prop1 的值 |

例如：

![](assets/overwrite-empty-prop.png)
