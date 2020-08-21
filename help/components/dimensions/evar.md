---
title: eVar
description: 可在报告中使用的自定义维度。
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 88%

---


# eVar

*此帮助页介绍 eVar 如何作为维度使用。有关如何实施 eVar 的信息，请参阅实施用户指南中的[eVar](/help/implement/vars/page-vars/evar.md)。*

eVar 是自定义变量，您可以根据需要随意使用。如果您有[解决方案设计文档](/help/implement/prepare/solution-design.md)，则大多数特定于您的组织的维度最终都会成为 eVar。默认情况下，eVar 会在其设置的点击之外继续存在。您可以在报表包设置的[转换变量](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)下自定义其到期和分配情况。

可用 eVar 的数量取决于您与 Adobe 签署的合同。如果您与 Adobe 签署的合同支持，则至多有 250 个 eVar 可供使用。

eVar不区分大小写。 如果在不同情况下（例如，和）发送相同 `"DOG"` 的值 `"Dog"`,Analysis Workspace会将它们组合到同一维度项目中。 使用在报告月开始时看到的第一个值的大小写。 data warehouse显示请求期间遇到的第一个值。

## 使用数据填充 eVar

每个 eVar 都从图像请求中的 [`v1` - `v250` 查询字符串](/help/implement/validate/query-parameters.md)中收集数据。例如，`v1` 查询字符串参数为 eVar1 收集数据，而 `v222` 查询字符串参数为 eVar222 收集数据。

AppMeasurement 将 JavaScript 变量编译到图像请求中以用于数据收集，它使用变量 `eVar1` - `eVar250`。请参阅实施用户指南中的 [eVar](/help/implement/vars/page-vars/evar.md)，以了解相关实施指南。

## Dimension项

由于eVar在您的实施中包含自定义字符串，您的组织将决定每个eVar的维项目。 Make sure you record the purpose of each eVar and typical dimension items in a [solution design document](/help/implement/prepare/solution-design.md).

## eVar 的工作方式

当您将数据发送到 Adobe Analytics 时，数据收集服务器会将点击转换为具有数百列的单行数据。每个 eVar 具有两个专用列；一个用于直接收集数据，另一个用于保持留值。

* 标准列包含从图像请求发送到 Adobe 的数据。
* “post”列包含永久数据，这取决于 eVar 的到期和分配情况。

几乎所有情况下，`post_evar` 列都会在报表中使用。

### eVar 如何与量度绑定

成功事件和 eVar 通常在不同的图像请求中定义。`post_evar` 列允许 eVar 值将自己绑定到事件，以显示报告中的数据。以下列访问为例：

1. 访客来到您主页的网站。
2. 他们使用您网站的内部搜索功能搜索“cat”。您的实施使用 eVar1 进行内部搜索。
3. 他们查看产品，并完成结帐过程。

原始数据的简化版本类似于：

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* `visitor_id` 列将点击与同一访客绑定。在实际原始数据中，`visid_high` 连接的值和 `visid_low` 确定访客 ID。
* `pagename` 列填充“页面”维度。
* `evar` 列确定明确设置 eVar1 时的点击量。
* 根据报表包设置下变量的分配和到期设置，`post_evar1` 将带有先前的值。
* `event_list` 列包含所有量度数据。对于此示例，`event1` 为“Searches”，而其他事件是标准购物车量度。在实际原始数据中，`event_list` 包含一组以逗号分隔的数字，由查找表将这些数字与量度相关联。

### 将数据收集转换为报告

Adobe Analytics 中的工具（如 Analysis Workspace）可以处理此收集的数据。例如，如果您使用 eVar1 作为维度，使用“订单”作为量度提取报表，则会看到以下类似报表：

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace 使用以下逻辑提取此报表：

* 查看所有 `event_list` 值，并挑选其中的所有带 `purchase` 的点击量。
* 除这些这些点击外，还显示 `post_evar1` 值。

### 分配和到期的重要性

由于分配和到期决定了哪些值会保留，因此它们对于充分利用分析实施至关重要。Adobe 强烈建议您在组织内讨论如何处理（分配）每个 eVar 的多个值以及 eVar 停止保留数据（到期）的时间。

* 默认情况下，eVar 使用上一次分配。新值将覆盖保留值。
* 默认情况下，eVar 使用访问的到期时间。访问结束后，值将停止在 `post_evar` 列中逐行复制。

您可以在报表包设置的[转换变量](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)下更改 eVar 分配和到期情况。

## eVar 与 Prop 的 值比较

Adobe 建议在大多数情况下使用 eVar，原因如下：

* eVar 在报表中具有 255 字节的限制。而 Prop 具有 100 字节的限制。
* 默认情况下，Prop 不会在设置的点击之外存留。eVar 具有自定义过期时间，允许您确定 eVar 何时不再获得后续事件的点数。但是，如果您使用[报表时间处理](/help/components/vrs/vrs-report-time-processing.md)，则 prop 和 eVar 均可使用自定义归因模型。
* Adobe 最多支持 250 个 eVar，仅支持 75 个 Prop。

请参阅 [Prop](prop.md)，了解有关 Prop 和 eVar 之间的更多比较信息。
