---
description: 新的智能警报系统允许对警报进行更多粒度控制，而且还将异常检测与警报系统集成在一起。
title: 智能警报概述
uuid: b9bf75ad-bb6f-49fe-8c55-355ea3c50a71
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 智能警报概述

智能警报允许对警报进行更多粒度控制，而且还将异常检测与警报系统集成在一起。

[YouTube 上的智能警报](https://www.youtube.com/watch?v=UVH9xr_2REA) (5:34)

## 概述

Analysis Workspace 中新增的警报生成器和警报管理器取代了 Reports &amp; Analytics 中现有的警报功能。智能警报允许您：

* 构建基于异常的警报（90%、95%、99%、99.75% 和 99.9% 阈值；% 更改；以上/以下）。
* 预览警报触发的频率
* 通过含链接的电子邮件或短信将警报发送到自动生成的 Analysis Workspace 项目
* 创建可在一个警报中捕获了多个量度的“堆栈式”警报。

可通过四种方式访问警报生成器：

* 直接转到警报生成器：**[!UICONTROL 组件]** &gt; **[!UICONTROL 警报]**
* 在工作区中使用键盘快捷键：`Ctrl + Shift + A` (Windows) 或 `Cmd + Shift + A` (Mac)
* 选择一个或多个自由格式表行项目，右键单击并选择&#x200B;**[!UICONTROL 从选定范围中创建警报]**。此时将打开警报生成器，并预填充从表中应用的相应量度和过滤器。您可以根据需要编辑警报。

   ![从选定范围中创建警报](assets/create-alert-from-selection.png)

* 从 Reports &amp; Analytics 报表中，转到&#x200B;**[!UICONTROL 更多]** &gt; **[!UICONTROL 添加警报]**。此时将打开警报生成器，并预填充从报表中应用的相应量度和过滤器。您可以根据需要编辑警报。

   ![添加警报](assets/add-alert.png)

百分比阈值代表标准偏差。例如，95% 等于 2 个标准偏差，99% 等于 3 标准偏差。根据您选择的时间粒度，将使用[不同的模型](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)来计算每个数据点和标准值之间的间隔时间（标准偏差个数）。设定的阈值越低，异常会越多。例如，同 99.75% 的相比，90% 的阈值会产生更多的异常。

> [!IMPORTANT] 使用带时间戳的数据创建警报可能会导致警报无法正确触发。Adobe 建议对智能警报使用不带时间戳的数据。

## 警报的异常回顾

如果警报使用异常检测，则培训期会根据为警报选择的粒度而有所不同。

* 每月粒度：15 个月及去年的相应日期范围
* 每周粒度：15 周及去年的相应日期范围
* 每天粒度：35 天及去年的相应日期范围
* 每小时粒度：336 小时

请参阅[异常检测中使用的统计技术](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)，以获取更多信息。
