---
description: 新的智能警报系统允许对警报进行更多粒度控制，而且还将异常检测与警报系统集成在一起。
seo-description: 新的智能警报系统允许对警报进行更多粒度控制，而且还将异常检测与警报系统集成在一起。
seo-title: 智能警报概述
title: 智能警报概述
uuid: b9bf75ad-bb6f-49fe-8c55-355ea3c50a71
translation-type: tm+mt
source-git-commit: ca9f1ed00295b556250894ae4e7fa377ef8a593d

---


# 智能警报概述

智能警报允许对警报进行更精细的控制，并将异常检测与警报系统相集成。

[YouTube上的智能警报](https://www.youtube.com/watch?v=UVH9xr_2REA) (5:34)

## 概述

Analysis Workspace 中新增的警报生成器和警报管理器取代了 Reports &amp; Analytics 中现有的警报功能。智能警报允许您:

* 根据异常（90%、95%、99%、99.75%和99.9%的阈值）建立警报；%变化；上／下)
* 预览警报触发频率
* 通过电子邮件或短信发送警报，其中包含指向自动生成的Analysis Workspace项目的链接
* 创建“堆叠”警报，以捕获单个警报中的多个指标

可通过四种方式访问警报生成器：

* 直接转到警报生成器： “组 **[!UICONTROL 件]** ”&gt;“警 **[!UICONTROL 报”]**
* 使用工作区中的键盘快捷键： `Ctrl + Shift + A` (Windows)或 `Cmd + Shift + A` (Mac)
* Selecting one or more freeform table line item/s, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**. 这将打开警报生成器，并预填充从表中应用的相应度量和过滤器。 您可以根据需要编辑警报。

   ![从选定范围中创建警报](assets/create-alert-from-selection.png)

* From within a Reports &amp; Analytics report, by going to  **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]** . 这将打开警报生成器，并预填充从报表应用的相应度量和过滤器。 您可以根据需要编辑警报。

   ![添加警报](assets/add-alert.png)

百分比阈值是标准偏差。 例如，95% 等于 2 个标准偏差，99% 等于 3 标准偏差。根据您选择的时间粒度，将使用[不同的模型](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)来计算每个数据点和标准值之间的间隔时间（标准偏差个数）。如果设置的阈值较低（如90%），则异常情况比设置的阈值较高(99.75%)时要多。

> [!IMPORTANT] 使用时间戳数据创建警报可能会导致警报触发错误。 Adobe建议对智能警报使用未加盖时间戳的数据。

## 警报的异常回顾

如果警报使用异常检测，则培训期会根据为警报选择的粒度而有所不同。

* 每月粒度：15个月以上，去年同期
* 每周粒度：15周以上，去年相同
* 每日粒度：35天+去年的相同范围
* 每小时粒度：336小时

See [Statistical techniques used in Anomaly Detection](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) for more information.
