---
description: 交易 ID 可通过选择普通（交易 ID）类别来集成。
seo-description: 交易 ID 可通过选择普通（交易 ID）类别来集成。
seo-title: 交易 ID
solution: Analytics
subtopic: 数据源
title: 交易 ID
topic: 开发人员和实施
uuid: f3370bb7-3f28-460b-a20 d-c9 e58 d7301 d4 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 交易 ID

交易 ID 可通过选择普通（交易 ID）类别来集成。

See [Integrating Offline Data](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**交易 ID 维度**

| 列名称 | 描述 |
|--- |--- |
| 交易 ID | （必需）唯一值，表示产生离线活动的在线交易。 |
| 页面 | 使用以下日期格式：MM/DD/YYYY/HH/mm/SS（例如 01/01/2015/06/00/00） |
| 跟踪代码 | 跟踪代码名称。 |
| 类别 | 类别名称。如果指定一个类别，则必须还要选择一个产品。 |
| 渠道 | 渠道名称。 |
| eVarN | eVarN名称。n 的有效值是 1 - 250 之间的整数。 |
| 产品 | 产品名称。 |
| 州 | 州名。 |
| 邮政编码 | 邮政编码名称。 |

<p class="head"> <b>交易 ID 量度</b> </p>



| 列名称 | 描述 |
|--- |--- |
| 点进率 | 跟踪代码查看次数。 |
| 购物车加货 | 购物车加货次数。 |
| 购物车打开 | 购物车打开次数。 |
| 购物车减货 | 购物车减货次数。 |
| 购物车查看 | 购物车查看次数。 |
| 结账 | 结账次数。 |
| 事件 n | 事件 n 发生次数。n 的有效值是 1 - 1000 之间的整数。如果您指定一个查看事件，还必须指定相应的数据维度 (eVar)。例如，如果要包含 eVar2 查看，则必须列出一个带值的 eVar2。 |
| eVarN视图 | eVar n 查看次数。n 的有效值是 1 - 250 之间的整数。 |
| 价格 | 产品价格。 |
| 订购 | 订购次数。 |
| 产品查看 | 产品查看次数。 |
| 数量 | 售出件数。 |