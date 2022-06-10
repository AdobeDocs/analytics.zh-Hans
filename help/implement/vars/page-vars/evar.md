---
title: eVar 变量
description: 可在实施中使用的自定义变量。
feature: Variables
exl-id: f89457b2-4186-4276-8637-9992070e3a73
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 87%

---

# eVar

*此帮助页面介绍了如何实施 eVar。有关 eVar 如何用作维度的信息，请参阅《组件用户指南》中的 [eVar](/help/components/dimensions/evar.md)。*

eVar 是自定义变量，您可以根据需要随意使用。如果您有[解决方案设计文档](/help/implement/prepare/solution-design.md)，则大多数特定于您的组织的维度最终都会成为 eVar。默认情况下，eVar 会在其设置的点击之外继续存在。您可以在报表包设置的[转换变量](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)下自定义其到期和分配情况。

可用 eVar 的数量取决于您与 Adobe 签署的合同。如果您与 Adobe 签署的合同支持，则至多有 250 个 eVar 可供使用。

## 在报表包设置中设置 eVar

在实施中使用 eVar 之前，请确保在报表包设置中配置每个 eVar。请参阅《管理员指南》中的[转化变量](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。

## 使用Web SDK的eVar

eVar为 [已映射Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在XDM字段下 `_experience.analytics.customDimensions.eVars.eVar1` to `_experience.analytics.customDimensions.eVars.eVar250`.

## 使用Adobe Analytics扩展的eVar

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置 eVar。

1. 登录到 [Adobe Experience Platform数据收集](https://experience.adobe.com/data-collection) 使用您的Adobe ID凭据。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到 [!UICONTROL eVar] 部分。

您可以将 eVar 设置为一个值或一个数据元素。您还可以从其他 Analytics 变量复制值。

## AppMeasurement和Analytics扩展中的s.eVar1 - s.eVar250自定义代码编辑器

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
>必须先在 Admin Console 中将 eVar 配置为“计数器”，然后才能使用计数器 eVar。请参阅《管理员指南》中的[转化变量](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。
