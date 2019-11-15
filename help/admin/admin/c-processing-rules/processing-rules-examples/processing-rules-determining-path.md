---
description: 您可以将 eVar 的值复制到一个属性来启用路径分析。
solution: Analytics
subtopic: Processing rules
title: 通过将 eVar 值复制到 prop 来确定路径
topic: Admin tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 通过将 eVar 值复制到 prop 来确定路径

您可以将 eVar 的值复制到一个属性来启用路径分析。

在设置值时，左侧的变量接收来自右侧变量的值（即使是空值）。

| 规则集 | 数值 |
|---|---|
| 条件 | 无（始终执行） |
| 操作 | 使用 eVar1 覆盖 Prop1 的值 |

仅在 Prop1 未包含值时，才可以修改此规则来设置 Prop1 的值，如下所示：

| 规则集 | 数值 |
|---|---|
| 条件 | 未设置 Prop1 时 |
| 操作 | 使用 eVar1 覆盖 Prop1 的值 |

例如：

![](assets/overwrite-empty-prop.png)

