---
title: list
description: 在同一点击中包含多个值的自定义变量。
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# list

列表变量是自定义变量，您可以随心所欲地使用。 它们的工作方式与eVar类似，只是它们可以在同一点击中包含多个值。 列表变量没有字符限制。

确保在解决方案设计文档中记录每个列表变量及其逻辑 [的使用方式](../../prepare/solution-design.md)。

> [!NOTE] 列表变量存储每个访客最近250个值。 如果给定访客的唯一值超过250个，则最早的值不会归因于度量。

## 在报表包设置中设置列表变量

请确保在实施中使用报表包设置中的每个列表变量之前，先配置这些变量。 See [Conversion variables](/help/admin/admin/conversion-var-admin/list-var-admin.md) in the Admin guide.

## 在Adobe Experience Platform Launch中列出变量

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## s.list1 - s.list3在AppMeasurement和启动自定义代码编辑器中

每个列表变量都是一个字符串，其中包含特定于您的组织的自定义值。 它们没有最大字节数；但是，每个单个值最大为255字节。 您使用的分隔符是在报表包设置中设置变量时确定的。 在分隔多个项目时不要使用空格。

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

> [!TIP] 如果在同一次点击中设置重复值，Adobe会消除这些值的所有实例的重复。 例如，如果设置， `s.list1 = "Example,Example";`则报表中会计入一个实例。

## 比较列表属性与列表变量

列表属性和列表变量在同一点击中都可以包含多个值。 但是，这两种变量类型之间有几个关键区别。

* 任何prop都可以成为列表prop。 如果每个prop都是列表prop，则实际上最多可以有75个列表prop。 只有3个列表变量可用。
* 列表属性对整个变量具有100字节的限制。 列表变量的每个值限制为255字节，没有总字节限制。
* 列表属性不会在设置的点击之外继续存在。 列表变量具有您需要的任何过期设置。 但是，通过报 [告时间处理](/help/components/vrs/vrs-report-time-processing.md)，您可以将自定义属性应用于列表属性和列表变量。
