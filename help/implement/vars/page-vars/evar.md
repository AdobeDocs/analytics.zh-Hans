---
title: eVar
description: 可在实施中使用的自定义变量。
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# eVar

*此帮助页面介绍了如何实施 eVar。有关 eVar 如何用作维度的信息，请参阅组件用户指南中的[eVar](../../../components/c-variables/dimensionslist/reports-conversion.md)。*

eVar 是自定义变量，您可以根据需要随意使用。

>[!TIP] 在大多数情况下，Adobe 建议使用 eVar 而不使用 prop。在 Adobe Analytics 的早期版本中，prop 和 eVar 各有利弊。但是，Adobe 已改进 eVar，现在几乎可以满足 prop 的所有用例。

确保在[解决方案设计文档](../../prepare/solution-design.md)中记录每个 eVar 的使用方式及其逻辑。

## 在报表包设置中设置 eVar

在实施中使用 eVar 之前，请确保在报表包设置中配置每个 eVar。请参阅管理员指南中的[转化变量](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。

## Adobe Experience Platform Launch 中的 eVar

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置 eVar。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到 [!UICONTROL eVar] 部分。

您可以选择 eVar 来设置值或数据元素。您还可以从其他 Analytics 变量复制值。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.eVar1 - s.eVar250

每个 eVar 都是一个字符串，其中包含特定于贵组织的自定义值。这些值的最大长度为 255 字节；超过 255 字节的值在发送到 Adobe 时会自动被截断。

```js
s.eVar1 = "Example custom value";
```

## 计数器 eVar

eVar 值通常包含字符串值。但是，您可以将 eVar 配置为包含计数器。例如，您希望计算购买前进行的内部搜索次数。您可以使用以下语法，而不是设置文本值：

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

如果小数超过两位，则 eVar 计数器舍入为两位小数。eVar 计数器不能包含负数。

>[!IMPORTANT] 必须先在 Admin Console 中将 eVar 配置为“计数器”，然后才能使用计数器 eVar。请参阅管理员指南中的[转化变量](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。

## prop 或 eVar 的独特优势

在 Adobe Analytics 的当前版本中，prop 和 eVar 都是自定义变量，且具有相似功能。但是，它们之间有几个主要区别：

* Prop 中的数据在几分钟内即可显示在报表中。eVar 则要经过 30 多分钟才能显示在报表中。
* Prop 在报表中具有 100 字节的限制。而 eVar 具有 255 字节的限制。
* Prop 能够成为列表属性，此类属性可在同一点击中接受多个值。列表变量是单独的变量，并且只有三个列表变量可用。
* 默认情况下，Prop 不会在设置的点击之外存留。eVar 具有自定义过期时间，允许您确定 eVar 何时不再获得后续事件的点数。但是，如果您使用[报表时间处理](../../../components/vrs/vrs-report-time-processing.md)，则 prop 和 eVar 均可使用自定义归因模型。
