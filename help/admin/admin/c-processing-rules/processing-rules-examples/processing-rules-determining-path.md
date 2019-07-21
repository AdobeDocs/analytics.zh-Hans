---
description: 您可以将 eVar 的值复制到一个属性来启用路径分析。
seo-description: 您可以将 eVar 的值复制到一个属性来启用路径分析。
seo-title: 通过将eVar值复制到prop来确定路径
solution: Analytics
subtopic: 处理规则
title: 通过将eVar值复制到prop来确定路径
topic: 管理工具
uuid: 8d7647c7-aa91-466b-8d31-fb4 dce83 f04 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 通过将eVar值复制到prop来确定路径

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

