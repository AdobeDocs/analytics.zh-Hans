---
title: eVar（维度）
description: 可在报告中使用的自定义维度。
feature: Dimensions
exl-id: ce7cc999-281d-4c52-b64d-d44cc320ab2d
TQID: https://experienceleague.adobe.com/id82CsXfjfKjzNiM36Ny97bcZ8a-TR7QDq5-mx7xP7w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 854
ht-degree: 100%

---

# eVar

*此帮助页面介绍 eVar 如何作为[维度](overview.md)使用。 有关如何实施 eVar 的信息，请参阅实施用户指南中的 [eVar](/help/implement/vars/page-vars/evar.md)。*

eVar 是自定义[维度](overview.md)，您可以根据需要随意使用。 如果您有[解决方案设计文档](/help/implement/prepare/solution-design.md)，则您的组织专用的大多数维度最终都将是 [!UICONTROL eVar]。

默认情况下，eVar 在被设置的点击发生后会继续存在。 有关 eVar 的持久性如何在 Adobe 的架构上运行的详细信息，请参阅下面的 [eVar 如何工作](#how-evars-work)以及 [eVar 如何与量度绑定](#how-evars-tie-to-metrics)两个部分。 您可以在[!UICONTROL 报告包设置]中的[转化变量](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)中启用、禁用或自定义其有效期限和分配。 下图显示了转化变量界面中 eVar 定义的一个例子：

![Evar 示例](assets/evars-sample.png)

可用 eVar 的数量取决于您与 Adobe 签署的合同。 如果您与 Adobe 签署的合同支持，则至多有 250 个 eVar 可供使用。

报告中使用的大写或小写基于您在某个给定的日历月中发送的第一个值。 取决于报告窗口以及此时段内首次收集的 eVar 值的情况，大小写可能会发生变化。

## 使用数据填充 eVar

每个 eVar 都从图像请求中的 [`v1` — `v250` 查询字符串](/help/implement/validate/query-parameters.md)中收集数据。 例如，`v1` 查询字符串参数为 eVar1 收集数据，而 `v222` 查询字符串参数为 eVar222 收集数据。

AppMeasurement 将 JavaScript 变量编译到图像请求中以用于数据收集，它使用变量 `eVar1` — `eVar250`。 请参阅实施用户指南中的 [eVar](/help/implement/vars/page-vars/evar.md)，以了解相关实施指南。

## 维度项目

由于 eVar 在您的实施中包含自定义字符串，因此，由您的组织来确定每个 eVar 的维度项目。 请确保在[解决方案设计文档](/help/implement/prepare/solution-design.md)中记录每个 eVar 的用途和典型维度项目。

## eVar 的工作方式

当您将数据发送到 Adobe Analytics 时，数据收集服务器会将点击转换为具有数百列的单行数据。 每个 eVar 具有两个专用列；一个用于直接收集数据，另一个用于保持留值。

* 标准列包含从图像请求发送到 Adobe 的数据。
* “post”列包含永久数据，这取决于 eVar 的有效期限和分配情况。

几乎所有情况下，`post_evar` 列都会在报表中使用。

### eVar 如何与指标绑定

成功事件和 eVar 通常在不同的时期中定义。 `post_evar` 列允许 eVar 值将自己绑定到事件，以显示报告中的数据。 以下列访问为例：

1. 访客来到您主页的网站。
2. 他们使用您网站的内部搜索功能搜索“cat”。 您的实施使用 eVar1 进行内部搜索。
3. 他们查看产品，并完成结帐过程。

原始数据的简化版本类似于：

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` | | | |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` | | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` | | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` | | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` | | `cats` | `purchase` |

* `visitor_id` 列将点击与同一访客绑定。 在实际原始数据中，`visid_high` 连接的值和 `visid_low` 确定访客 ID。
* `pagename` 列填充“页面”维度。
* `evar` 列确定明确设置 eVar1 时的点击量。
* 根据报表包设置下变量的分配和有效期限设置，`post_evar1` 将带有先前的值。
* `event_list` 列包含所有指标数据。 对于此示例，`event1` 为“Searches”，而其他事件是标准购物车指标。 在实际原始数据中，`event_list` 包含一组以逗号分隔的数字，由查找表将这些数字与指标相关联。

### 将数据收集转换为报告

Adobe Analytics 中的工具（如 Analysis Workspace）可以处理此收集的数据。 例如，如果您使用 eVar1 作为维度，使用“订单”作为指标提取报表，则会看到以下类似报表：

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace 使用以下逻辑提取此报表：

* 查看所有 `event_list` 值，挑选出其中所有带 `purchase` 的行。
* 从这些行中显示 `post_evar1` 值。

生成的报告中，左侧显示 `post_evar1` 中包含的每一个不同的值，右侧显示有多少订单归因于这个值。

### 分配和有效期限的重要性

由于分配和有效期限决定了哪些值会保留，因此它们对于充分利用分析实施至关重要。 Adobe 强烈建议您在组织内讨论如何处理（分配）每个 eVar 的多个值以及 eVar 停止保留数据（有效期限）的时间。

* 默认情况下，eVar 使用上一次分配。 新值将覆盖保留值。
* 默认情况下，eVar 使用访问的有效期限。 访问结束后，值将停止在 `post_evar` 列中逐行复制。

您可以在报表包设置的[转换变量](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)下更改 eVar 分配和有效期限情况。

## eVar 与 Prop 的 值比较

Adobe 建议在大多数情况下使用 eVar，原因如下：

* eVar 在报表中具有 255 字节的限制。 而 Prop 具有 100 字节的限制。
* 默认情况下，Prop 不会在设置的点击之外存留。 eVar 具有自定义过期时间，允许您确定 eVar 何时不再获得后续事件的点数。 但是，如果您使用[报表时间处理](/help/components/vrs/vrs-report-time-processing.md)，则 prop 和 eVar 均可使用自定义归因模型。
* Adobe 最多支持 250 个 eVar，仅支持 75 个 Prop。

请参阅 [Prop](prop.md)，了解有关 Prop 和 eVar 之间的更多比较信息。
