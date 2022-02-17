---
description: 访客 ID 可通过选择普通（交易 ID）类别来集成。
subtopic: Data sources
title: 访客 ID
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 100%

---

# VisitorID

访客 ID 可以通过选择[!UICONTROL 呼叫中心数据]类别来集成。

请参阅[集成离线数据](/help/import/c-data-sources/datasrc-integrating-offline-data.md)。

## VisitorID 维度

| 列名称 | 描述 |
|--- |--- |
| [!UICONTROL VisitorID] | （必需）唯一值，表示同时位于在线和离线系统中的客户。 |
| [!UICONTROL 日期] | 使用以下日期格式：`MM/DD/YYYY/hh/mm/ss`（例如，07/14/2017/06/00/00） |
| [!UICONTROL 跟踪代码] | 跟踪代码名称。 |
| [!UICONTROL 类别] | 类别名称。如果指定一个类别，则必须还要选择一个产品。 |
| [!UICONTROL 渠道] | 渠道名称。 |
| [!UICONTROL eVar ]*n* | eVar *n* 名称。*n* 的有效值是 1 - 75 之间的整数。 |
| [!UICONTROL 产品] | 产品名称。 |
| [!UICONTROL 省/州] | 省/州名。 |
| [!UICONTROL Zip] | 邮政编码名称。 |

## 访客 ID 量度

| 列名称 | 描述 |
| --- | --- |
| [!UICONTROL 点进率] | 跟踪代码查看次数。 |
| [!UICONTROL 购物车加货次数] | 购物车加货次数。 |
| [!UICONTROL 购物车打开次数] | 购物车打开次数。 |
| [!UICONTROL 购物车减货次数] | 购物车减货次数。 |
| [!UICONTROL 购物车查看] | 购物车查看次数。 |
| [!UICONTROL 结账] | 结账次数。 |
| *事件 n* | 事件 *n* 发生的次数。n 的有效值是 1 - 100 之间的整数。如果您指定[!UICONTROL 查看]事件，则还必须指定对应的数据维度 (eVar)。例如，如果要包含 eVar2 查看，则必须列出一个带值的 eVar2。 |
| [!UICONTROL eVar ]*n* 查看 | eVar *n* 查看次数。*n* 的有效值是 1 - 75 之间的整数。 |
| [!UICONTROL 价格] | 产品价格。 |
| [!UICONTROL 订单数] | 订购次数。 |
| [!UICONTROL 产品查看次数] | 产品查看次数。 |
| [!UICONTROL 数量] | 售出件数。 |
