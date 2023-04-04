---
title: 数据源文件格式
description: 正确生成文件以在数据源中使用。
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 7%

---

# 数据源文件格式

数据源文件具有以下属性：

* 文件在 `.txt` 格式。
* 带注释的行以“`#`和是可选的。
* 第一行未加注释的行包含文件的标头。
* 每行的第一个值是日期，日期使用格式 `MM/DD/YYYY` 或 `MM/DD/YYYY/HH/mm/SS`.
* 每行的值（包括标题）均以制表符分隔。
* 每行必须至少包含一个维度和一个量度。

## 评论

以&#39;开头的任何行`#`&#39;是注释。 下载数据源模板文件时，前两行是注释。

* 第一条注释指示您为数据源配置的模板类型、创建数据源的后端用户ID以及数据源ID。
* 第二个注释为模板文件中包含的每个标头提供了友好名称。

处理文件时，Adobe会忽略所有注释行，因此您可以删除模板注释或在整个文件中添加您自己的注释。 只能对完整行进行注释；您无法注释掉单个字段或部分行。

## 标头

上载数据源文件时，需要列标题。 这些列标题不区分大小写，但必须填充必需的空格(例如， `eVar1` 是无效的标头，而 `EVAR 1` 有效)。 列标题适用于所有报表包。 请使用以下表确保数据源文件中的每个标头设置正确。

>[!TIP]
>
>如果在数据源文件中包含正确的标头，则可以从头开始创建数据源文件。 在单个文件中可以包含的标头数量没有限制；但是，每行最多只能有4096字节。

| 维度 | 数据源标题 |
| --- | --- |
| [类别](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` — `Evar 250` |
| [营销渠道](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [营销渠道详细信息](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [产品](/help/components/dimensions/product.md) | `Product` |
| [跟踪代码](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [交易 ID](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [邮政编码](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Dimension和量度进入同一标题行。

| 度量 | 数据源标题 |
| --- | --- |
| [购物车加货](/help/components/metrics/cart-additions.md) | `Cart Adds` |
| [购物车减货](/help/components/metrics/cart-removals.md) | `Cart Removes` |
| [购物车查看](/help/components/metrics/cart-views.md) | `Cart Views` |
| [购物车](/help/components/metrics/carts.md) | `Cart Opens` |
| [结账](/help/components/metrics/checkouts.md) | `Checkouts` |
| [自定义事件](/help/components/metrics/custom-events.md) | `Event 1` — `Event 1000` |
| [订单数](/help/components/metrics/orders.md) | `Orders` |
| [收入](/help/components/metrics/revenue.md) | `Price` |
| [件数](/help/components/metrics/units.md) | `Quantity` |

{style="table-layout:auto"}

Adobe不支持任何其他维度或量度的数据源。 如果需要上表所列变量以外的变量，请考虑使用 [批量数据插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) 中。

## 日期

每行中的第一个值 **必须** 是日期。 日期格式必须采用以下格式之一：

* **`MM/DD/YY/HH/mm/SS`**
* **`MM/DD/YY`**

省略小时/分钟/秒会自动将当天的时间戳设置为中午12点。

单个数据源文件最多支持90个独特日期。 如果您希望在上传中包含90个独特天数，请将数据拆分为多个文件。

## Dimension和量度数据

每行中日期之后的后续值都包含您要上传的数据。 每行都与相应的时间戳相对应。 确保每行都存在相同数量的制表符。 列可以按任意顺序排列；确保每行中的数据与顶部的标题对齐。 一行最多可包含4096字节的数据量。

Dimension数据不能包含分号(`;`)。 跳过包含分号的行。

## 后续步骤

[文件上传](file-upload.md):了解上传数据源文件以按Adobe摄取的过程。
