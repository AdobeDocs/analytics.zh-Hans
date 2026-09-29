---
title: Prop
description: 可在报告中使用的自定义维度。
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
TQID: 'https://experienceleague.adobe.com/2WMG5X3GNmogf-9Bbapq78pjVg5ibQQw7Bgb0qNpF1E'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 82%
---
# Prop

>[!BEGINSHADEBOX]

*此帮助页介绍prop如何作为[维度](overview.md)使用。 有关如何实施 Prop 的信息，请参阅实施用户指南中的 [Prop](/help/implement/vars/page-vars/prop.md)。*

>[!ENDSHADEBOX]

Prop 是自定义变量，您可以根据需要随意使用。 它们不会在设置的点击之外继续存在。

>[!TIP]
>
>Adobe 建议在大多数情况下使用 [eVar](evar.md)。 在 Adobe Analytics 的早期版本中，prop 和 eVar 各有利弊。 但是，Adobe 已改进 eVar，现在几乎可以满足 prop 的所有用例。

如果您有[解决方案设计文档](/help/implement/prepare/solution-design.md)，则可以将这些自定义维度分配给特定于贵组织的值。 可用 prop 的数量取决于您与 Adobe 签署的合同。 如果您与 Adobe 签署的合同支持，则至多有 75 个 prop 可供使用。

## 使用数据填充 Prop

每个Prop使用AppMeasurement中对应的[`prop1` - `prop75`](/help/implement/vars/page-vars/prop.md)变量收集数据。 例如，`prop1`变量填充prop1维度，而`prop68`变量填充prop68维度。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | [`prop1` - `prop75`](/help/implement/vars/page-vars/prop.md) |
| **Web SDK / XDM字段** | [`_experience.analytics.customDimensions.props.prop1` - `prop75`](https://experienceleague.adobe.com/cn/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) |
| **查询参数** | [`c1` - `c75`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<prop1>` - `<prop75>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 100字节 |
| **持久性** | 点击 |

## 维度项目

由于 Prop 在您的实施中包含自定义字符串，因此，由您的组织来确定每个 Prop 的维度项目。 请确保在[解决方案设计文档](/help/implement/prepare/solution-design.md)中记录每个Prop的用途和典型维度项目。

## 区分大小写

默认情况下，Prop 不区分大小写。 如果您以不同的大小写发送同一个值（例如，`"DOG"` 和 `"Dog"`），Analysis Workspace 会将它们分组到同一维度项目中。 它会使用在报告月份开始时看到的第一个值的大小写。 Data Warehouse 将显示在请求期间遇到的第一个值。

您可以让任何 Prop 区分大小写。 您还可以在启用 Prop 后，为任何 Prop 禁用区分大小写功能。 请联系 Adobe 客户关怀团队，提供报告包 ID 和所需的变量以切换区分大小写设置。

>[!WARNING]
>
>切换区分大小写设置可能会拆分维度项目，导致区段出现意外结果，并导致过滤器出现问题。 Adobe 强烈建议在两个主要时间段（如在每月或每年开始时）之间切换此设置。

## Prop 与 eVar 的 值比较

Adobe 建议在大多数情况下使用 eVar。 此建议的例外情况如下：

* 您可以在实时报表中使用 Prop。 eVar 至少需要 30 分钟才能在报告中显示出来。
* Prop 能够成为列表属性，此类属性可在同一点击中接受多个值。 列表变量是单独的变量，并且只有三个列表变量可用。
* 在 Prop 上启用路径后，[登入](entry-dimensions.md)和[退出](exit-dimensions.md)维度将立即变为可用。 如果需要 eVar 的进入和退出维度，可以手动创建区段。

请参阅 [eVar](evar.md)，了解有关 Prop 和 eVar 之间的更多比较信息。
