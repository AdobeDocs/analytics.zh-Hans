---
title: Prop
description: 可在报告中使用的自定义维度。
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 63%

---


# Prop

*此帮助页介绍 Prop 如何作为维度使用。有关如何实施 Prop 的信息，请参阅实施用户指南中的[Prop](/help/implement/vars/page-vars/prop.md)。*

Prop 是自定义变量，您可以根据需要随意使用。它们不会在设置的点击之外继续存在。

>[!TIP]
>
>Adobe 建议在大多数情况下使用 [eVar](evar.md)。在 Adobe Analytics 的早期版本中，prop 和 eVar 各有利弊。但是，Adobe 已改进 eVar，现在几乎可以满足 prop 的所有用例。

如果您有[解决方案设计文档](/help/implement/prepare/solution-design.md)，则可以将这些自定义维度分配给特定于贵组织的值。可用 prop 的数量取决于您与 Adobe 签署的合同。如果您与 Adobe 签署的合同支持，则至多有 75 个 prop 可供使用。

## 使用数据填充 Prop

每个 Prop 都从图像请求中的 [`c1` - `c75` 查询字符串](/help/implement/validate/query-parameters.md)中收集数据。例如，`c1` 查询字符串参数为 Prop1 收集数据，而 `c68` 查询字符串参数为 Prop68 收集数据。

AppMeasurement 将 JavaScript 变量编译到图像请求中以用于数据收集，它使用变量 `prop1` - `prop75`。请参阅实施用户指南中的 [Prop](/help/implement/vars/page-vars/prop.md)，以了解相关实施指南。

## Dimension项

由于prop在实施中包含自定义字符串，您的组织将决定每个prop的维项目。 Make sure you record the purpose of each prop and typical dimension items in a [solution design document](/help/implement/prepare/solution-design.md).

## 区分大小写

Prop默认不区分大小写。 如果在不同情况下（例如，和）发送相同 `"DOG"` 的值 `"Dog"`,Analysis Workspace会将它们组合到同一维度项目中。 使用在报告月开始时看到的第一个值的大小写。 data warehouse显示请求期间遇到的第一个值。

您可以区分任何prop大小写。 启用任何prop后，您还可以禁用其区分大小写功能。 联系Adobe客户关怀部门，使用报表包ID和所需的变量来切换区分大小写。

>[!IMPORTANT]
>
>切换大小写敏感性可能会断开维度项目，导致区段出现意外结果，并导致过滤器问题。 Adobe强烈建议在两个主要时间段（如一个月或一年的开始）之间切换此设置。

## Prop 与 eVar 的 值比较

Adobe 建议在大多数情况下使用 eVar。此建议的例外情况如下：

* 您可以在实时报表中使用 Prop。eVar 至少需要 30 分钟才能在报表中显示出来。
* Prop 能够成为列表属性，此类属性可在同一点击中接受多个值。列表变量是单独的变量，并且只有三个列表变量可用。
* 在 Prop 上启用路径后，[登入](entry-dimensions.md)和[退出](exit-dimensions.md)维度将立即变为可用。如果需要 eVar 的登入和退出维度，可以手动创建区段。

请参阅 [eVar](evar.md)，了解有关 Prop 和 eVar 之间的更多比较信息。
