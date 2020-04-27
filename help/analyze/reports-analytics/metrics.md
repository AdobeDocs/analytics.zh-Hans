---
description: 量度是报表的基础，可帮助您查看和了解数据关系并启用网站不同数据集的并排比较。量度是有关访客活动的量化信息，包括查看次数、点进次数、重新加载次数、平均逗留时间、件数、订购、收入等。
title: 量度
topic: Reports and analytics
uuid: ae2021eb-8b26-4a98-b7a0-ce36bca46753
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 量度

量度是报表的基础，可帮助您查看和了解数据关系并启用网站不同数据集的并排比较。量度是有关访客活动的量化信息，包括查看次数、点进次数、重新加载次数、平均逗留时间、件数、订购、收入等。

## 量度

量度是报表的基础，可帮助您查看和了解数据关系并启用网站不同数据集的并排比较。量度是有关访客活动的量化信息，包括查看次数、点进次数、重新加载次数、平均逗留时间、件数、订购、收入等。

量度和关联的数据显示在报表的列中。流量量度显示有关访客流量的数据。转化量度显示有关成功事件的数据，如购买、下载或其他任何您希望用户在您网站上进行的操作。

[计算量度](/help/components/c-calcmetrics/cm-overview.md)通过对量度进行组合来创建。

有关定义，请参阅[量度概述](/help/components/c-variables/c-metrics/metricslist.md)

## 选择默认报表量度

描述如何在报表级别选择默认量度的步骤。

<!-- 

t_metrics_set_default.xml

 -->

1. 运行报表。
1.  添加要另存为默认量度的量度。
1. 单击下 **[!UICONTROL Add Metrics]** 拉列表，然后选择 **[!UICONTROL Set as Default]**。

   所选量度将另存为该报表的默认量度。以下信息适用于默认量度：

* 默认量度可在所有用户帐户中应用，但是会依据报表和报表包。例如，查看相同报表包中特定报表的所有用户会使用上述过程显示量度设置。
* 如果在报表间移动，则会保留最近查看的报表中显示的量度。To display default metrics in that new report, click the [!UICONTROL Add Metrics] drop-down list, then click [!UICONTROL Show Defaults].

* Clicking [!UICONTROL Clear Defaults] removes the default metrics for that report and reverts them to the original default metrics for that report ( [!UICONTROL Page Views] for props, and whatever you have set in Admin Tools for eVars).

