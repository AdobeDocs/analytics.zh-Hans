---
title: eVar
description: 可在报告中使用的自定义维度。
translation-type: ht
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# eVar

*此帮助页介绍 eVar 如何作为维度使用。有关如何实施 eVar 的信息，请参阅实施用户指南中的[eVar](/help/implement/vars/page-vars/evar.md)。*

eVar 是自定义变量，您可以根据需要随意使用。如果您有[解决方案设计文档](/help/implement/prepare/solution-design.md)，则大多数特定于您的组织的维度最终都会成为 eVar。默认情况下，eVar 会在其设置的点击之外继续存在。您可以在报表包设置的[转换变量](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)下自定义其到期和分配情况。

## eVar 的工作方式

当您将数据发送到 Adobe Analytics 时，数据收集服务器会将点击转换为具有数百列的单行数据。每个 eVar 具有两个专用列；一个用于直接收集数据，另一个用于保持留值。

* 标准列包含从图像请求发送到 Adobe 的数据。
* “post”列包含永久数据，这取决于 eVar 的到期和分配情况。

几乎所有情况下，`post_evar` 列都会在报表中使用。

### eVar 如何与量度绑定

成功事件和 eVar 通常在不同的图像请求中定义。`post_evar` 列允许 eVar 值将自己绑定到事件，以显示报告中的数据。以下列访问为例：

1. 访客来到您主页的网站。
2. 他们使用您网站的内部搜索功能搜索“cat”。实施将 eVar1 设置为内部搜索。
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
