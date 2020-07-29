---
title: Prop
description: 可在报告中使用的自定义维度。
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 19%

---


# Prop

*此帮助页介绍prop如何作为维工作。 For information on how to implement props, see[props](/help/implement/vars/page-vars/prop.md)in the Implement user guide.*

Prop 是自定义变量，您可以根据需要随意使用。它们不会超越它们设定的冲击。

>[!TIP]
>
>Adobe recommends using [eVars](evar.md) in most cases. 在 Adobe Analytics 的早期版本中，prop 和 eVar 各有利弊。但是，Adobe 已改进 eVar，现在几乎可以满足 prop 的所有用例。

如果您有解决 [方案设计文档](/help/implement/prepare/solution-design.md)，则可以将这些自定义维度分配给特定于您的组织的值。 可用的Prop的数量取决于您与Adobe的合同。 如果您与Adobe的合同支持，则最多可获得75个Prop。

## 用数据填充prop

每个属性都从图像请 [`c1` 求中 `c75` 的查询](/help/implement/validate/query-parameters.md) 字符串收集数据。 例如，查询字 `c1` 符串参数会收集prop1的，而 `c68` 查询字符串参数会收集prop68的数据。

AppMeasurement将JavaScript变量编译为图像请求以进行数据收集，它使用这些变 `prop1` 量- `prop75`。 有关 [实施指南](/help/implement/vars/page-vars/prop.md) ，请参阅《实施用户指南》中的prop。

## Dimension项

由于prop在实施中包含自定义字符串，您的组织将决定每个prop的维项目。 确保在解决方案设计文档中记录每个prop和典型维 [度项的用途](/help/implement/prepare/solution-design.md)。

## 区分大小写

Prop默认不区分大小写。 如果在不同情况下（例如，和）发送相同 `"DOG"` 的值， `"Dog"`Analysis Workspace会将它们组合到同一维度项目中。 使用在报告月开始时看到的第一个值的大小写。 Data warehouse显示请求期间遇到的第一个值。

您可以区分任何prop大小写。 启用任何prop后，您还可以禁用其区分大小写功能。 联系Adobe客户关怀部门，使用报表包ID和所需的变量来切换区分大小写。

>[!IMPORTANT]
>
>切换大小写敏感性可能会断开维度项目，导致区段出现意外结果，并导致过滤器问题。 Adobe强烈建议在两个主要时间段（如一个月或一年的开始）之间切换此设置。

## prop在eVar上的值

 Adobe 建议在大多数情况下使用 eVar。此语句的例外情况如下：

* 您可以在实时报告中使用prop。 eVar至少需要30分钟才能显示在报告中。
* Prop 能够成为列表属性，此类属性可在同一点击中接受多个值。列表变量是单独的变量，并且只有三个列表变量可用。
* 在prop上启用寻路功能后， [进入](entry-dimensions.md)[和退出](exit-dimensions.md) 维度将立即变为可用。 如果要eVar的进入和退出维，可以手动创建区段。

请参 [阅eVar](evar.md) ，了解prop和eVar之间的更多比较。
