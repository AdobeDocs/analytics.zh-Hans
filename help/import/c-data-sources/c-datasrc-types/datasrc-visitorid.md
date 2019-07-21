---
description: 访客 ID 可通过选择普通（交易 ID）类别来集成。
seo-description: 访客 ID 可通过选择普通（交易 ID）类别来集成。
seo-title: 访客 ID
solution: Analytics
subtopic: 数据源
title: 访客 ID
topic: 开发人员和实施
uuid: e9ce675-72c2-42a4-8f2e-25140df19539
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 访客 ID

访客 ID 可通过选择普通（交易 ID）类别来集成。

See [Integrate Offline Data](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

<p class="head"> <b>访客 ID 维度</b> </p>

| 列名称 | 描述 |
|--- |--- |
| 访客 ID | （必需）唯一值，表示同时位于在线和离线系统中的客户。 |
| 页面 | 使用以下日期格式：MM/DD/YYYY/hh/mm/ss（例如 07/14/2017/06/00/00） |
| 跟踪代码 | 跟踪代码名称。 |
| 类别 | 类别名称。如果指定一个类别，则必须还要选择一个产品。 |
| 渠道 | 渠道名称。 |
| eVarN | eVarN名称。n 的有效值是 1 - 75 之间的整数。 |
| 产品 | 产品名称。 |
| 州 | 州名。 |
| 邮政编码 | 邮政编码名称。 |

**访客 ID 量度**

| 列名称 | 描述 |
|--- |--- |
| 点进率 | 跟踪代码查看次数。 |
| 购物车加货 | 购物车加货次数。 |
| 购物车打开 | 购物车打开次数。 |
| 购物车减货 | 购物车减货次数。 |
| 购物车查看 | 购物车查看次数。 |
| 结账 | 结账次数。 |
| 事件 n | 事件 n 发生次数。n 的有效值是 1 - 100 之间的整数。如果您指定一个查看事件，还必须指定相应的数据维度 (eVar)。例如，如果要包含 eVar2 查看，则必须列出一个带值的 eVar2。 |
| eVarN视图 | eVar n 查看次数。n 的有效值是 1 - 75 之间的整数。 |
| 价格 | 产品价格。 |
| 订购 | 订购次数。 |
| 产品查看 | 产品查看次数。 |
| 数量 | 售出件数。 |