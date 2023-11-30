---
description: 量度是报表的基础，可帮助您查看和了解数据关系并启用网站不同数据集的并排比较。量度是有关访客活动的量化信息，包括查看次数、点进次数、重新加载次数、平均逗留时间、件数、订购、收入等。
title: Reports & Analytics 量度概述
feature: Reports & Analytics Basics
role: User, Admin
exl-id: ea7a59f3-5a5e-48b2-ae0c-ebc5ec34cd63
source-git-commit: fe472efe57f8fb2da7ad6942852cad0301aefe46
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 97%

---

# 量度概述

{{ra-eol}}

量度是报表的基础，可帮助您查看和了解数据关系并启用网站不同数据集的并排比较。量度是有关访客活动的量化信息，包括查看次数、点进次数、重新加载次数、平均逗留时间、件数、订购、收入等。

量度和关联的数据显示在报表的列中。流量量度显示有关访客流量的数据。转化量度显示有关成功事件的数据，如购买、下载或其他任何您希望用户在您网站上进行的操作。

[计算量度](/help/components/c-calcmetrics/cm-overview.md)通过对量度进行组合来创建。

有关完整的量度列表，请参阅组件用户指南中的[量度概述](/help/components/metrics/overview.md)。

## 选择默认报表量度

要在报表级别选择默认量度，请执行以下操作：

<!-- 

t_metrics_set_default.xml

 -->

1. 运行报表。
1.  添加要另存为默认量度的量度。
1. 单击&#x200B;**[!UICONTROL 添加量度]**&#x200B;下拉列表，然后选择&#x200B;**[!UICONTROL 设为默认值]**。

   所选量度将另存为该报表的默认量度。以下信息适用于默认量度：

* 默认量度可在所有用户帐户中应用，但是会依据报表和报表包。例如，查看相同报表包中特定报表的所有用户会使用上述过程显示量度设置。
* 如果在报表间移动，则会保留最近查看的报表中显示的量度。要在该新报表中显示默认量度，请单击“[!UICONTROL 添加量度]”下拉列表，然后单击“[!UICONTROL 显示默认值]”。

* 单击“[!UICONTROL 清除默认值]”会删除该报表的默认量度，并将其还原为该报表的原始默认量度（prop 的[!UICONTROL 页面查看]，无论您在“管理工具”中如何设置 eVar）。
