---
title: 数据源文件格式
description: 正确生成文件以用于数据源。
exl-id: 6632b970-e931-4272-a69b-c1130ad6475f
feature: Data Sources
role: Admin
source-git-commit: cc25fe304d9cab3db3fa2ddd306338ff3bb88a55
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 5%

---

# 数据源文件格式

数据源文件具有以下属性：

* 文件格式为`.txt`。
* 注释的行以“`#`”开头，是可选的。
* 第一个非注释行包含文件的标头。
* 每行的第一个值是日期，该日期使用格式`MM/DD/YYYY`或`MM/DD/YYYY/HH/mm/SS`。
* 每行的值（包括标题）均采用制表符分隔形式。
* 每行必须至少有一个维度和一个量度。

## 评论

任何以“`#`”开头的行都是注释。 下载数据源模板文件时，前两行是注释。

* 第一个注释指示您为数据源配置的模板类型、创建数据源的后端用户ID以及数据源ID。
* 第二个注释为模板文件中包含的每个标头提供友好名称。

处理文件时，Adobe会忽略所有注释行，因此您可以移除模板注释或在整个文件中添加自己的注释。 只能注释整个行；不能注释掉单个字段或部分行。

## 标头

上传数据源文件时，需要列标题。 这些列标题不区分大小写，但需要空格（例如，`eVar1`是无效的标题，而`EVAR 1`有效）。 列标题适用于所有报表包。 请使用下表确保正确设置了数据源文件中的每个标头。

>[!TIP]
>
>如果数据源文件中包含正确的标头，则可以从头开始创建数据源文件。 单个文件中可以包含的标头数量没有限制；但是，每行最多只能包含4096字节。

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

维度和量度进入相同的标题行。

| 量度 | 数据源标题 |
| --- | --- |
| [购物车加货](/help/components/metrics/cart-additions.md) | `Cart Adds` |
| [购物车减货](/help/components/metrics/cart-removals.md) | `Cart Removes` |
| [购物车查看](/help/components/metrics/cart-views.md) | `Cart Views` |
| [购物车](/help/components/metrics/carts.md) | `Cart Opens` |
| [结账](/help/components/metrics/checkouts.md) | `Checkouts` |
| [自定义事件](/help/components/metrics/custom-events.md) | `Event 1` — `Event 1000` |
| [订单数](/help/components/metrics/orders.md) | `Orders` |
| [收入](/help/components/metrics/revenue.md) | `Price` |
| [单位](/help/components/metrics/units.md) | `Quantity` |

{style="table-layout:auto"}

Adobe不支持任何其他维度或指标的数据源。 如果要求以上表中列出的变量以外的变量，请考虑改用[批量数据插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)。

## 日期

每行&#x200B;**中的第一个值必须**&#x200B;为日期。 日期格式必须为以下格式之一：

* **`MM/DD/YYYY/HH/mm/SS`**
* **`MM/DD/YYYY`**

若省略小时/分钟/秒，则会自动将时间戳设置为当天的中午12点。

单个数据源文件最多可支持90个唯一日期。 如果您想在上传中包含90天以上的唯一天数，请将数据拆分为多个文件。

## Dimension和量度数据

每行中日期之后的后续值包含要上传的数据。 每一行对应于相应的时间戳。 确保每行的制表符数量相同。 列可以按任意顺序；确保每行中的数据与顶部的标题一致。 单行可以包含的最大数据量为4096字节。

Dimension数据不能包含分号(`;`)。 包含分号的行将被跳过。

## 后续步骤

[文件上传](file-upload.md)：了解上传数据源文件以供Adobe摄取的流程。
