---
title: prop
description: 可在实施中使用的自定义变量。
feature: Appmeasurement Implementation
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 85%

---

# prop

*此帮助页面介绍了如何实施 props。有关 prop 如何用作维度的信息，请参阅《组件用户指南》中的 [prop](/help/components/dimensions/prop.md)。*

Prop 是自定义变量，您可以根据需要随意使用。它们不会在设置的点击之外继续存在。

>[!TIP]
>
>Adobe 建议在大多数情况下使用 [eVar](evar.md)。在 Adobe Analytics 的早期版本中，prop 和 eVar 各有利弊。但是，Adobe已改进eVar，现在它们几乎可以满足prop的所有用例。

如果您有[解决方案设计文档](/help/implement/prepare/solution-design.md)，则可以将这些自定义维度分配给特定于贵组织的值。可用 prop 的数量取决于您与 Adobe 签署的合同。如果您与 Adobe 签署的合同支持，则至多有 75 个 prop 可供使用。

## 使用 Web SDK 的 props 属性

Prop映射到以下变量：

* [XDM对象](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm._experience.analytics.customDimensions.props.prop1` - `xdm._experience.analytics.customDimensions.props.prop75` — 列表属性是在单独的[字段集](#list-props-web-sdk)中指定的。
* [数据对象](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75`；或`data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` — 列表属性包括在这些字段中。

## 使用 Adobe Analytics 扩展的 props

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置 props。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 属性]部分。

您可以将 prop 设置为值或数据元素。您还可以从其他 Analytics 变量复制值。

## AppMeasurement 和 Analytics 扩展自定义代码编辑器中的 s.prop1 - s.prop75

每个 prop 变量都是一个字符串，其中包含特定于贵组织的自定义值。其值的最大长度为 100 字节；超过 100 字节的值在发送到 Adobe 时会自动被截断。

```js
s.prop1 = "Example custom value";
```

## 列表属性

列表属性是应用于 prop 的设置，它允许变量在同一点击中包含多个值。如果未启用此设置，或者如果使用了错误的分隔符，则变量将被视为单个值。

### 配置列表属性

在报表包设置下的[流量变量](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)中启用列表 props。 确保正确配置所需的分隔符。Adobe 不提供默认分隔符。

>[!TIP]
>
>实施中使用的常见分隔符为逗号 (`,`)、冒号 (`:`)、分号 (`;`) 或管道字符 (`|`)。您可以使用最适合您的实施的任何非扩展 ASCII 分隔符。

### 使用 Web SDK 设置列表 props {#list-props-web-sdk}

如果使用&#x200B;[**XDM对象**](/help/implement/aep-edge/xdm-var-mapping.md)，则列表属性将映射到`xdm._experience.analytics.customDimensions.listProps.prop1.values[]` - `xdm._experience.analytics.customDimensions.listProps.prop75.values[]`。 Web SDK 会自动使用报表包设置下列出的正确分隔符。如果您在 XDM 字段中设置分隔符（例如，`xdm._experience.analytics.customDimensions.props.prop1.delimiter`），则会覆盖从报表包设置中自动检索的分隔符，并可能导致错误分析列表 prop 字符串。

如果使用&#x200B;[**数据对象**](/help/implement/aep-edge/data-var-mapping.md)，则列表属性使用与标准属性相同的字段并遵循AppMeasurement语法。

### 使用 Adobe Analytics 扩展和 AppMeasurement 设置列表 props

在报表包设置中使用所需的分隔符配置列表 props 后，除了使用分隔符外，没有任何其他实施差异。

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>列表属性仍受最大长度为 100 字节的限制。列表属性更容易达到此限制并被截断，因为它们可能会包含多个值。如果可能会达到此 100 字节限制，请考虑使用缩写或将值缩短。

如果在列表属性中多次设置相同的值，则会在报表中删除重复值。Analysis Workspace 会计算出现某个值的点击次数，而不是计算某个值在数据中存在的次数。
