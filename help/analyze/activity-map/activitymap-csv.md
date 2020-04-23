---
description: 在标准模式中，将分析数据从活动映射导出到逗号分隔值(CSV)文件。
title: 导出到 CSV 文件
topic: Activity map
uuid: dc6c50c0-57f7-45b8-a4cb-2092a21da529
translation-type: tm+mt
source-git-commit: ee5489798f8c82c563b49b6c96acd1e63a0aa920

---


# 导出到 CSV 文件

在标准模式中，将分析数据从活动映射导出到逗号分隔值(CSV)文件。

作为用户，您可能需要将链接点击数据与其他数据源合并，或执行其他分析（例如，在Excel中）。 CSV导出允许您以易于使用的格式获取给定页面的所有活动图数据。 它允许您将为页面生成的分析数据保存为平面CSV文件，以便导出页面数据上的页面报 [表、页面流报](/help/analyze/activity-map/activitymap-page-flow.md)[表和链接](/help/analyze/activity-map/activitymap-links-report.md) 。 然后，您可以视图为电子表格或文本文件，或将数据导入到其他系统中。

单击“活动图”工具栏上的“导出”图标。

活动图根据Adobe Analytics页面名称生成文件名，并在其中附加一个日期和时间戳：Pagename_DateTime.csv。 该文件将保存在相应浏览器的默认下载目录下。

| 导出信息 | 描述 |
|---|---|
| 页面指标报告 | Analytics中的页面度量数据，包括在页面上停留的时间、在页面上的点击次数和总页面视图。 |
| 页面详细信息报告 | 用于标识内部条目或外部引用的上一页的页面条目和退出信息，以及退出数据。 |
| 页面报告上的链接 | 在“标准”或“实时”模式下，特定页面的链接信息。 |
