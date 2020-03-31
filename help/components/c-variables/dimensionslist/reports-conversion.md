---
title: eVar
description: 可在报告中使用的自定义维。
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# eVar

*此帮助页介绍eVar如何作为维度工作。 有关如何实施eVar的信息，请参[阅实施用户指南](/help/implement/vars/page-vars/evar.md)中的eVar。*

eVar 是自定义变量，您可以根据需要随意使用。如果您有解决 [方案设计文档](/help/implement/prepare/solution-design.md)，则特定于您组织的大多数维度最终都会是eVar。 默认情况下，eVar会在其设置的点击之外继续存在。 您可以在报表包设置的“转换变量”下自 [定义其到期](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) 和分配。

## eVar的工作方式

当您将数据发送到Adobe Analytics时，数据收集服务器会将点击转换为包含数百列的单行数据。 每个eVar都有两列专用；一个用于直接数据收集，另一个用于持久值。

* 标准列包含从图像请求发送到Adobe的数据。
* “post”列包含永久数据，这取决于eVar的过期和分配。

在几乎所有情况下，该 `post_evar` 列都用于报告。

### eVar如何与指标绑定

成功事件和eVar通常在不同的图像请求中定义。 该列 `post_evar` 允许eVar值将自己绑定到事件，以报告显示数据。 例如，以下访问为例：

1. 访客到达您主页的网站。
2. 他们使用您网站的内部搜索搜索“cats”。 实施将eVar1设置为内部搜索。
3. 他们视图产品，然后完成结帐流程。

原始数据的简化版本将类似于以下内容：

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* 该 `visitor_id` 列将点击量绑定到同一访客。 在实际原始数据中，连接的值 `visid_high` 和确 `visid_low` 定访客ID。
* 该列 `pagename` 填充“页面”维。
* 列确 `evar` 定显式设置eVar1时的点击量。
* 根 `post_evar1` 据报表包设置下变量的分配和过期时间设置，该值将带有上一个值。
* 该列 `event_list` 包含所有度量数据。 对于此示例， `event1` 为“搜索”，其他事件为标准购物车量度。 在实际原始数据中， `event_list` 包含一组以逗号分隔的数字，其中查找表将这些数字与度量关联。

### 将数据收集转换为报告

Adobe Analytics中的工具(如分析工作区)可处理此收集的数据。 例如，如果您使用eVar1作为维度，使用“订单”作为度量来提取报表，则您会看到类似于以下内容的报表：

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

分析工作区使用以下逻辑提取此报告：

* 查看所有 `event_list` 值，并挑选其中的所有点 `purchase` 击量。
* 在这些点击中，显示 `post_evar1` 值。

### 分配和到期的重要性

由于分配和过期决定了什么值会保留，因此它们对于从分析实施中获得最大价值至关重要。 Adobe强烈建议您在组织内讨论如何处理（分配）每个eVar的多个值以及eVar停止持久数据（过期）时。

* 默认情况下，eVar使用上次分配。 新值将覆盖保留的值。
* 默认情况下，eVar使用访问到期。 访问结束后，值即停止在列中逐行复 `post_evar` 制。

您可以在报表包设置的“转换变量”下 [更改eVar分配](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) 和过期时间。
