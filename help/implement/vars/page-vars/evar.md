---
title: eVar（变量）
description: 可在实施中使用的自定义变量。
feature: Appmeasurement Implementation
exl-id: f89457b2-4186-4276-8637-9992070e3a73
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 92%

---

# eVar

*此帮助页面介绍了如何实施 eVar。有关 eVar 如何用作维度的信息，请参阅《组件用户指南》中的 [eVar](/help/components/dimensions/evar.md)。*

eVar 是自定义变量，您可以根据需要随意使用。如果您有[解决方案设计文档](/help/implement/prepare/solution-design.md)，则大多数特定于您的组织的维度最终都会成为 eVar。默认情况下，eVar 会在其设置的点击之外继续存在。您可以在报告包设置的[转换变量](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)下自定义其有效期限和分配情况。

可用 eVar 的数量取决于您与 Adobe 签署的合同。如果您与 Adobe 签署的合同支持，则至多有 250 个 eVar 可供使用。

## 在报告包设置中设置 eVar

在实施中使用 eVar 之前，请确保在报告包设置中配置每个 eVar。 请参阅管理员指南中的[转化变量](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)。

## 使用 Web SDK 的 eVar

eVar映射到以下变量：

* [XDM对象](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm._experience.analytics.customDimensions.eVars.eVar1`到`xdm._experience.analytics.customDimensions.eVars.eVar250`
* [数据对象](/help/implement/aep-edge/data-var-mapping.md)：`data.__adobe.analytics.eVar1`到`data.__adobe.analytics.eVar250`；或`data.__adobe.analytics.v1`到`data.__adobe.analytics.v250`

## 使用 Adobe Analytics 扩展的 eVar

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置 eVar。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到 [!UICONTROL eVar] 部分。

您可以将 eVar 设置为一个值或一个数据元素。您还可以从其他 Analytics 变量复制值。

## AppMeasurement 和 Analytics 扩展代码编辑器中的 s.eVar1 - s.eVar250

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

>[!IMPORTANT]
>
>必须先在 Admin Console 中将 eVar 配置为“计数器”，然后才能使用计数器 eVar。请参阅《管理员指南》中的[转化变量](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)。
