---
title: Prop
description: 可在报告中使用的自定义维度。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 26%

---


# Prop

*此帮助页介绍prop如何作为维工作。 For information on how to implement props, see[props](/help/implement/vars/page-vars/prop.md)in the Implement user guide.*

Prop 是自定义变量，您可以根据需要随意使用。它们不会超越它们设定的冲击。

>[!TIP]
>
>Adobe recommends using [eVars](evar.md) in most cases. 在 Adobe Analytics 的早期版本中，prop 和 eVar 各有利弊。但是，Adobe 已改进 eVar，现在几乎可以满足 prop 的所有用例。

如果您有解决 [方案设计文档](/help/implement/prepare/solution-design.md)，则可以将这些自定义维度分配给特定于您的组织的值。 可用Prop的数量取决于您与Adobe的合同。 如果您与Adobe的合同支持，则最多可获得75个Prop。

## 用数据填充prop

每个属性都从图像请 [`c1` 求中 `c75` 的查询](/help/implement/validate/query-parameters.md) 字符串收集数据。 例如，查询字 `c1` 符串参数会收集prop1的，而 `c68` 查询字符串参数会收集prop68的数据。

AppMeasurement将JavaScript变量编译为图像请求以进行数据收集，它使用这些变 `prop1` 量- `prop75`。 有关 [实施指南](/help/implement/vars/page-vars/prop.md) ，请参阅《实施用户指南》中的prop。

## 维项

由于prop在实施中包含自定义字符串，您的组织将决定每个prop的维项目。 确保在解决方案设计文档中记录每个prop和典型维 [度项的用途](/help/implement/prepare/solution-design.md)。

## prop在eVar上的值

 Adobe 建议在大多数情况下使用 eVar。此语句的例外情况如下：

* 您可以在实时报告中使用prop。 eVar至少需要30分钟才能显示在报告中。
* Prop 能够成为列表属性，此类属性可在同一点击中接受多个值。列表变量是单独的变量，并且只有三个列表变量可用。
* 在prop上启用寻路功能后， [进入](entry-dimensions.md)[和退出](exit-dimensions.md) 维度将立即变为可用。 如果要eVar的进入和退出维，可以手动创建区段。

请参 [阅eVar](evar.md) ，了解prop和eVar之间的更多比较。
