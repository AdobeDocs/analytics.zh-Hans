---
title: Prop
description: 可在报告中使用的自定义维度。
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 93%

---

# Prop

*此帮助页介绍prop如何作为[维度](overview.md)使用。 有关如何实施 Prop 的信息，请参阅实施用户指南中的 [Prop](/help/implement/vars/page-vars/prop.md)。*

Prop 是自定义变量，您可以根据需要随意使用。它们不会在设置的点击之外继续存在。

>[!TIP]
>
>Adobe 建议在大多数情况下使用 [eVar](evar.md)。在 Adobe Analytics 的早期版本中，prop 和 eVar 各有利弊。但是，Adobe 已改进 eVar，现在几乎可以满足 prop 的所有用例。

如果您有[解决方案设计文档](/help/implement/prepare/solution-design.md)，则可以将这些自定义维度分配给特定于贵组织的值。可用 prop 的数量取决于您与 Adobe 签署的合同。如果您与 Adobe 签署的合同支持，则至多有 75 个 prop 可供使用。

## 使用数据填充 Prop

每个 Prop 都从图像请求中的 [`c1` - `c75` 查询字符串](/help/implement/validate/query-parameters.md)中收集数据。例如，`c1` 查询字符串参数为 Prop1 收集数据，而 `c68` 查询字符串参数为 Prop68 收集数据。

AppMeasurement 将 JavaScript 变量编译到图像请求中以用于数据收集，它使用变量 `prop1` - `prop75`。请参阅实施用户指南中的 [Prop](/help/implement/vars/page-vars/prop.md)，以了解相关实施指南。

## 维度项目

由于 Prop 在您的实施中包含自定义字符串，因此，由您的组织来确定每个 Prop 的维度项目。请确保在[解决方案设计文档](/help/implement/prepare/solution-design.md)中记录每个Prop的用途和典型维度项目。

## 区分大小写

默认情况下，Prop 不区分大小写。如果您以不同的大小写发送同一个值（例如，`"DOG"` 和 `"Dog"`），Analysis Workspace 会将它们分组到同一维度项目中。它会使用在报表月份开始时看到的第一个值的大小写。Data Warehouse 将显示在请求期间遇到的第一个值。

您可以让任何 Prop 区分大小写。您还可以在启用 Prop 后，为任何 Prop 禁用区分大小写功能。请联系 Adobe 客户关怀团队，提供报表包 ID 和所需的变量以切换区分大小写设置。

>[!WARNING]
>
>切换区分大小写设置可能会影响维度项目，导致区段出现意外结果，以及导致过滤器出现问题。Adobe 强烈建议在两个主要时间段（如在每月或每年开始时）之间切换此设置。

## Prop 与 eVar 的 值比较

Adobe 建议在大多数情况下使用 eVar。此建议的例外情况如下：

* 您可以在实时报表中使用 Prop。eVar 至少需要 30 分钟才能在报表中显示出来。
* Prop 能够成为列表属性，此类属性可在同一点击中接受多个值。列表变量是单独的变量，并且只有三个列表变量可用。
* 在 Prop 上启用路径后，[登入](entry-dimensions.md)和[退出](exit-dimensions.md)维度将立即变为可用。如果需要 eVar 的登入和退出维度，可以手动创建区段。

请参阅 [eVar](evar.md)，了解有关 Prop 和 eVar 之间的更多比较信息。
