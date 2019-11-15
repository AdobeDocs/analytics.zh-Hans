---
description: 交易 ID 可通过选择普通（交易 ID）类别来集成。
solution: Analytics
subtopic: Data sources
title: 交易 ID
topic: Developer and implementation
uuid: f3370bb7-3f28-460b-a20d-c9e58d7301d4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 交易 ID

交易 ID 可通过选择普通（交易 ID）类别来集成。

请参 [阅集成脱机数据](/help/import/c-data-sources/datasrc-integrating-offline-data.md)。

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**交易 ID 维度**

| 列名称 | 描述 |
|--- |--- |
| 交易 ID | （必需）唯一值，表示产生离线活动的在线交易。 |
| 页面 | 使用以下日期格式：MM/DD/YYYY/HH/mm/SS（例如 01/01/2015/06/00/00） |
| 跟踪代码 | 跟踪代码名称。 |
| 类别 | 类别名称。如果指定一个类别，则必须还要选择一个产品。 |
| 渠道 | 渠道名称。 |
| eVarN | eVarN名称。 N的有效值是整数1 - 250。 |
| 产品 | 产品名称。 |
| 州 | 州名。 |
| Zip | 邮政编码名称。 |

<p class="head"> <b>交易 ID 量度</b> </p>



| 列名称 | 描述 |
|--- |--- |
| 点进率 | 跟踪代码查看次数。 |
| 购物车加货 | 购物车加货次数。 |
| 购物车打开 | 购物车打开次数。 |
| 购物车减货 | 购物车减货次数。 |
| 购物车查看 | 购物车查看次数。 |
| 结账 | 结账次数。 |
| EventN | eventN发生的次数。 N的有效值是整数1 - 1000。  如果您指定一个查看事件，还必须指定相应的数据维度 (eVar)。例如，如果要包含 eVar2 查看，则必须列出一个带值的 eVar2。 |
| eVarN视图 | 查看eVarN的次数。 N的有效值是整数1 - 250。 |
| 价格 | 产品价格。 |
| 订购 | 订购次数。 |
| 产品查看次数 | 产品查看次数。 |
| 数量 | 售出件数。 |
