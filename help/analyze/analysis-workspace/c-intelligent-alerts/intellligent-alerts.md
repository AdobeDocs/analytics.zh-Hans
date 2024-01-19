---
description: 新的智能警报系统允许对警报进行更多粒度控制，而且还将异常检测与警报系统集成在一起。
title: 智能警报概述
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 88%

---

# 智能警报概述

智能警报允许对警报进行更多粒度控制，而且还将异常检测与警报系统集成在一起。

以下是关于[智能警报](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=zh-Hans)的视频教程 (5:34)

## 概述

智能警报允许您：

* 构建基于异常的警报（90%、95%、99%、99.75% 和 99.9% 阈值；% 更改；以上/以下）。
* 预览警报触发的频率
* 通过含链接的电子邮件或短信将警报发送到自动生成的 Analysis Workspace 项目
* 创建可在一个警报中捕获了多个指标的“堆栈式”警报。

可通过三种方式访问警报生成器：

| 方法 | 详细信息 |
| --- | --- |
| 直接转到警报生成器 | **[!UICONTROL 组件]** > **[!UICONTROL 警报]** |
| 在 Workspace 中使用快捷键 | `Ctrl + Shift + A` (Windows) 或 `Cmd + Shift + A` (Mac) |
| 选择一个或多个自由格式表行项 | 单击右键并选择&#x200B;**[!UICONTROL 从所选内容创建警报]**。这样将打开[!UICONTROL 警报生成器]，并预先填充从该表中应用的相应指标和过滤器。可根据需要编辑警报。![从所选内容创建警报](assets/create-alert-from-selection.png) |

百分比阈值代表标准偏差。例如，95% 等于 2 个标准偏差，99% 等于 3 标准偏差。根据您选择的时间粒度， [不同模型](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) 用于计算每个数据点距离标准有多远（多少标准偏差）。 设定的阈值越低，异常会越多。例如，同 99.75% 的相比，90% 的阈值会产生更多的异常。

>[!IMPORTANT]
>
>使用带时间戳的数据创建警报可能会导致警报无法正确触发。Adobe 建议对智能警报使用不带时间戳的数据。

## 警报的异常回顾

如果警报使用异常检测，则培训期会根据为警报选择的粒度而有所不同。

* 每月粒度：15 个月及去年的相应日期范围
* 每周粒度：15 周及去年的相应日期范围
* 每天粒度：35 天及去年的相应日期范围
* 每小时粒度：336 小时

请参阅[异常检测中使用的统计技术](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)，以获取更多信息。
