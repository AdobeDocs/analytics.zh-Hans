---
title: eVar
description: 可在实施中使用的自定义变量。
translation-type: tm+mt
source-git-commit: dcb69257fd29686ae346cf4d0cf50ed041ebcbbc

---


# eVar

eVar是自定义变量，您可以随意使用。

> [!TIP] 在大多数情况下，Adobe建议在prop上使用eVar。 在Adobe Analytics的早期版本中，prop和eVar之间有利有弊。 但是，Adobe已将eVar改进为几乎可满足prop的所有使用案例。

确保在解决方案设计文档中记录每个eVar的使用方 [式及其逻辑](../../prepare/solution-design.md)。

## 在报表包设置中设置eVar

在实施中使用eVar之前，请确保在报表包设置中配置每个eVar。 See [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

## Adobe Experience Platform Launch中的eVar

您可以在配置Analytics扩展时（全局变量）或根据规则设置eVar。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到 [!UICONTROL eVars部分] 。

您可以选择eVar来设置值或数据元素。 您还可以从其他Analytics变量复制值。

## s.eVar1 - s.eVar250 in AppMeasurement and Launch自定义代码编辑器

每个eVar都是一个字符串，其中包含特定于您的组织的自定义值。 最大长度为255字节；超过255字节的值在发送到Adobe时会自动截断。

```js
s.eVar1 = "Example custom value";
```

## 计数器 eVar

eVar值通常包含字符串值。 但是，您可以将eVar配置为包含计数器。 例如，您希望计算购买前进行的内部搜索数。 除了设置文本值，您应使用以下语法：

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

如果小数超过两位，则 eVar 计数器舍入为两位小数。eVar计数器不能包含负数。

> [!IMPORTANT] 必须首先在管理控制台中将eVar配置为“计数器”，然后才能使用计数器eVar。 See [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

## prop或eVar的独有优势

在Adobe Analytics的当前版本中，prop和eVar都是具有类似功能的自定义变量。 但是，它们有几个主要区别：

* Prop中的数据在几分钟内即可在报告中使用。 eVar在报告中可能需要超过30分钟才能显示。
* Prop在报表中具有100字节的限制。 eVar有255字节的限制。
* Prop能够成为列表Prop，它们在同一点击中接受多个值。 列表变量是单独的变量，只有三个列表变量可用。
* 默认情况下，Prop不会在设置的点击之外保留。 eVar具有自定义过期时间，允许您确定eVar何时不再获得后续活动的信用。 但是，如果您使用报 [告时间处理](../../../components/vrs/vrs-report-time-processing.md), prop和eVar都可以使用自定义归因模型。
