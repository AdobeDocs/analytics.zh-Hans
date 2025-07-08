---
description: 了解如何使用警报功能，以实现对通知的精细化控制，并与异常检测集成。
title: 警报概述
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: ht
source-wordcount: '310'
ht-degree: 100%

---

# 警报概述

Adobe Analytics 中的警报允许您根据变化的百分比或特定数据点收到通知。

根据您的 Adobe Analytics 包，您还可以使用基于异常阈值触发的警报。这些警报（也称为“智能警报”）提供与[异常检测](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)集成的粒度控制，在您最需要时触发。

警报允许您：

* 预览警报触发的频率
* 通过含链接的电子邮件或短信将警报发送到自动生成的 Analysis Workspace 项目
* 创建可在一个警报中捕获了多个量度的“堆栈式”警报。
* 根据异常情况生成警报（90%、95%、99%、99.75% 和 99.9% 阈值；% 变化；高于/低于）（仅适用于拥有 Select、Prime 或 Ultimate 包的 Adobe Analytics 客户）

以下视频教程提供了警报的基本概述：[警报](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=zh-Hans)（5:34）

## 警报的异常回顾

>[!NOTE]
>
>只有拥有 Adobe Analytics Prime 或 Ultimate 包的组织才能使用带有异常检测的警报（也称为&#x200B;_智能警报_）。

如果警报使用异常检测，则培训期会根据为警报选择的粒度而有所不同。

* 每月粒度：15 个月及去年的相应日期范围
* 每周粒度：15 周及去年的相应日期范围
* 每天粒度：35 天及去年的相应日期范围
* 每小时粒度：336 小时

有关更多信息，请参阅[异常检测中使用的统计技术](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)。

## 创建警报

有关如何在 Adobe Analytics 中创建警报的信息，请参阅[创建警报](/help/components/c-alerts/alert-builder.md)。

>[!IMPORTANT]
>
>使用带时间戳的数据创建警报可能会导致警报无法正确触发。Adobe 建议对警报使用不带时间戳的数据。

## 管理警报

您可以在警报管理器中管理现有警报。您可以对警报执行各种管理任务，例如标记、重命名、删除等。

有关如何管理 Adobe Analytics 中现有警报的更多信息，请参阅[管理警报](/help/components/c-alerts/alert-manager.md)。
