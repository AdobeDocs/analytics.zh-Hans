---
title: prop
description: 可在实施中使用的自定义变量。
translation-type: tm+mt
source-git-commit: ddab63a4fe3b8f1a3187893eba1ac3a1eda3bc41

---


# prop

Prop是自定义变量，您可以随心所欲地使用它。

> [!TIP] Adobe建议在大多数情况下使用eVar。 在Adobe Analytics的早期版本中，prop和eVar之间有利有弊。 但是，Adobe已将eVar改进为几乎可满足prop的所有使用案例。 请参 [阅eVar](evar.md) ，了解这两种自定义变量类型之间的功能比较。

如果您的组织使用prop，请确保在解决方案设计文档中记录其使 [用和逻辑](../../prepare/solution-design.md)。

## Adobe Experience Platform Launch中的Prop

您可以在配置Analytics扩展时（全局变量）或在规则下设置prop。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到“ [!UICONTROL Props] ”部分。

您可以选择属性来设置值或数据元素。 您还可以从其他Analytics变量复制值。

## s.prop1 - s.prop75 in appMeasurement and Launch自定义代码编辑器

每个prop变量都是一个字符串，其中包含特定于您的组织的自定义值。 最大长度为100字节；超过100字节的值在发送到Adobe时会自动截断。

```js
s.prop1 = "Example custom value";
```

## 列表属性

列表属性是应用于prop的设置，它允许变量在同一点击中包含多个值。 如果未启用此设置，或者如果使用了错误的分隔符，则变量将被视为单个值。

### 配置列表属性

在报表包设置中启用列表属性。 See [Traffic variables](/help/admin/admin/c-traffic-variables/traffic-var.md) in the Admin user guide. 确保正确配置所需的分隔符。 Adobe不提供默认分隔符。

> [!TIP] 实施中使用的常见分隔符是逗号(`,`)、冒号(`:`)、分号(`;`)或管道(`|`)。 您可以使用最适合您的实施的分隔符。

### 设置列表属性

在报表包设置中使用所需的分隔符配置列表属性后，除了使用分隔符外，没有任何实现差异。

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

> [!IMPORTANT] 列表属性仍受100字节最大长度的限制。 列表属性更容易达到此限制并被截断，因为它们可以包含多个值。 如果可能达到这个100字节限制，请考虑使用缩写或缩短值。
