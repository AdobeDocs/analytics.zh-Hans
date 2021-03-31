---
description: 在 Workspace 项目中使用流失可视化。
title: 流失概述
uuid: 2d98899e-e401-4d7a-8af0-de0002f84178
feature: 可视化图表
role: 业务从业者，管理员
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 99%

---


# 流失概述

流失可视化图表为构建流失报表提供了多个选项。流失报表显示访客从何处离开（流失）或继续通过（流过）预定义的页面序列。

流失可视化图表允许您

* 对同一个报表中的两个不同区段执行逐项比较。
* 拖放和重新排列漏斗步骤（接触点）
* 混合和匹配来自不同维度和指标的值
* 创建多维度流失报表
* 识别客户在流失之后马上前往何处

流失显示一个序列中每个步骤或接触点之间的转化和流失率。

例如，您可以跟踪购买过程中的客户流失点。您只需选择一个起始接触点和一个结束接触点，并在其中添加中间接触点，即可创建网站浏览路径。但是，您还可以执行多维度流失.

流失可视化图表有助于分析以下内容：

* 网站上特定过程的转化率（例如购买或注册过程）。
* 一般、更宽范围的流量：显示在查看主页的访客中，有多少人继续进行搜索及有多少人最终查看特定项目。
* 网站上事件之间的关联。显示查看隐私政策后继续购买产品的访客百分比。

[流失可视化视频教程](https://docs.adobe.com/content/help/zh-Hans/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization.html)（4 分 15 秒）

## 分段作为流量和流失的基础{#section_654F37A398C24DDDB1552A543EE29AA9}

应用于 Workspace 面板的区段与应用于 Reports &amp; Analytics 中流失和流量报表的区段在工作方式上略有不同。大多数时间，它们产生的结果完全一致。主要区别是 Reports &amp; Analytics 在序列的每一步应用区段。由于这一区别，产生的结果有时可能会略有不同。

我们以两个步骤的流失分析为例：

![](assets/fallout_segments1.png)

如果您在 Workspace 面板级别应用区段，区段会按以下方式与流失结合使用：

![](assets/fallout_seg.png)

相比之下，当 Reports &amp; Analytics 计算该区段时，按此方式合并该区段：

![](assets/fallout_segments3.png)

Reports &amp; Analytics 每一步都合并该区段。如果容器级别和流失级别（例如访问次数或访客数级别）相同，则结果会与访问次数或访客数相匹配。

但是，如果应用到面板的区段比流失级别（如点击次数级别）低，则区段会因为其在报表中结合使用的方式不同而显示出不同的结果。为了重新迭代，大多数情况下 Analysis Workspace 中的数字都与 Reports &amp; Analytics 中的相同。只有以下情况全部属实，它们才&#x200B;**不**&#x200B;相同：

* 区段和流失不在同一级别。
* 区段存在变数，即一次访问可能有不同的访客数量，或一位访客可能有不同的访问次数。

在极少数情况下，您可能需要使 Analysis Workspace 与 Reports &amp; Analytics 将区段应用到流失/流量的方式保持一致，为此只需将区段拖放到 Workspace 中的每个流失步骤，即可得到相同的结果。
