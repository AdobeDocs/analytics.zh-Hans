---
title: 归因常见问题解答
seo-title: 归因常见问题解答
description: 获取有关归因的常见问题解答。
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 归因常见问题解答

**使用归因时，“无”行项目是什么？**

“无”行项目是一个全包项，它表示在回顾窗口中没有任何接触点的情况下发生的所有转换。 尝试在报告窗口中包含更长的时间范围。

**为什么在使用归因模型时，有时会在报告窗口之外看到日期？**

这些额外日期是由于访客报告回顾窗口造成的。 有关 [详细信息，请参阅](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) Analytics KB中报告窗口外显示的数据。 Adobe计划在即将发布的版本中过滤掉这些额外行。

**能否将自定义回顾窗口与归因模型结合使用？**

归因模型当前依赖访客或访问回顾窗口。 通过更改报告日期范围（针对访客回顾）或将自定义访问定义作为虚拟报告套件的一部分来调整这些回顾窗口中的任何一个。 有关更 [多信息，请参阅报告时间](../../../../components/vrs/vrs-report-time-processing.md) （处理）。

**何时应使用访问与访客归因回顾？**

归因回顾的选择取决于您的用例。 如果转换通常比单次访问花费的时间长，则建议访客回顾。 创建具有较长访问定义的虚拟报告套件也是一个潜在的解决方案。

**使用归因时，prop和eVar如何进行比较？**

归因在报表运行时重新计算，因此为了归因建模，prop或eVar（或任何其他维度）之间没有差异。 Prop可以使用任何回顾窗口或归因模型保持不变，并且eVar分配／到期设置会被忽略。

**归因模型是否可用于其他分析功能，如数据源或数据仓库？**

不会。归因模型使用报告时间处理，这仅在Analysis Workspace中可用。 有关更 [多信息，请参阅报告时间](../../../../components/vrs/vrs-report-time-processing.md) （处理）。

**仅当我使用启用了报告时间处理的虚拟报告套件时，归因模型是否可用？**

归因模型在虚拟报表包之外可用。 当他们在后端使用报告时间处理时，归因模型可用于标准报告套件和虚拟报告套件。

**不支持哪些维度和指标？**

归因面板支持所有维度。 不支持的指标包括：

* 独特访客
* 访问
* 发生次数
* 页面查看次数
* A4T 量度
* 逗留时间量度
* 跳出次数
* 跳出率
* 登录
* 退出
* 页面未找到
* 搜索
* 单页面访问量
* 单次存取

**Analysis Workspace中的归因与Data Workbench中的归因有何不同？**

Data Workbench以增量方式提供：

* 在更多访客级别的数据源中进行归因的功能，例如广告展示次数和销售点。
* 算法建模。Analysis Workspace中的归因仅包括基于规则的模型。 请参 [阅《Data Workbench用户指南](https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html) 》中的“最适合建模”。
* 其他可视化图表，例如延时表。请参 [阅《Data Workbench用户指南](https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html) 》中的延迟表。

**归因是否适用于分类？**

是，完全支持分类。

**归因是否可以与数据源一起使用？**

是的，大多数数据源都受支持。 摘要级别数据源不能进行归因，因为它们不与Analytics访客标识符关联。 除非在启用了报告时间处理的虚拟报告套件中使用交易ID数据源，否则也支持这些数据源。

**归因是否可与Advertising Analytics集成一起使用？**

元数据维度（如匹配类型和关键字）与归因结合使用。 但是，指标（包括印象、成本、点击量、平均位置和平均质量分数）使用摘要级别的数据源，因此不兼容。
