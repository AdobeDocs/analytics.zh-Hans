---
description: 启用用于移动应用程序跟踪的维度和量度。
title: 应用程序报告
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 13%

---

# 应用程序报告

通过应用程序报表界面，您可以启用专用于移动应用程序跟踪的生命周期维度和量度。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 应用程序管理]** > **[!UICONTROL 应用程序报表]**

>[!IMPORTANT]
>
>一旦启用了其中的任何功能，就无法禁用它们。 启用给定功能后，Analysis Workspace中会永久使用其各自的维度和量度。

## [!UICONTROL 应用程序报表]

[!UICONTROL 应用程序报表]维度和量度用于以下目的：

* **客户获取**：跟踪应用程序下载促销活动的反向链接URL。
* **生命周期**：由每次应用程序启动时发送的测量提供的基础级别报表。
* **应用程序操作**：基于应用程序内操作的报表和路径。
* **生命周期值**：使用应用程序KPI（例如购买、广告查看、视频完成、社交分享、照片上传）了解用户如何随时间累加值。
* **定时事件**：测量关键应用程序操作（如首次购买前的时间）之间经过的时间（应用程序内时间和总时间）。

启用[!UICONTROL 应用程序报表]时，以下维度可用：

* [!UICONTROL 操作名称]（具有[进入](/help/components/dimensions/entry-dimensions.md)和[退出](/help/components/dimensions/exit-dimensions.md)维度）
* [!UICONTROL 应用程序ID]
* [!UICONTROL 客户获取内容]
* [!UICONTROL 客户获取Medium]
* [!UICONTROL 客户获取名称]
* [!UICONTROL 客户获取Source]
* [!UICONTROL 客户获取条件]
* [!UICONTROL 每周时间(SDK)]
* [!UICONTROL 首次使用后间隔天数]
* [!UICONTROL 上次使用后间隔天数]
* [!UICONTROL 设备名称(SDK)]
* [!UICONTROL 小时(SDK)]
* [!UICONTROL 首次启动日期]
* [!UICONTROL 启动次数]
* [!UICONTROL 生命周期值(evar)]
* [!UICONTROL 操作系统版本(SDK)]
* [!UICONTROL 分辨率(SDK)]

以下量度可用：

* [!UICONTROL 应用程序中的操作时间]
* [!UICONTROL 总操作时间]
* [!UICONTROL 崩溃]
* [!UICONTROL 首次启动次数]
* [!UICONTROL 启动项]
* [!UICONTROL 生命周期值（事件）]
* [!UICONTROL 会话总时长]
* [!UICONTROL 升级]

## [!UICONTROL 位置跟踪]

[!UICONTROL 位置跟踪]维度用于以下目的：

* 跟踪纬度和经度数据
* 识别、创建和可视化特定目标点。 目标点必须在移动设备SDK配置文件中定义。
* 跟踪蓝牙信标（UUID、major、minor 和 proximity）。

启用[!UICONTROL 位置跟踪]时，以下维度可用：

* [!UICONTROL 主要信标]（具有[进入](/help/components/dimensions/entry-dimensions.md)和[退出](/help/components/dimensions/exit-dimensions.md)维度）
* [!UICONTROL 次要信标]（具有[进入](/help/components/dimensions/entry-dimensions.md)和[退出](/help/components/dimensions/exit-dimensions.md)维度）
* [!UICONTROL 邻近地区信标]（具有[进入](/help/components/dimensions/entry-dimensions.md)和[退出](/help/components/dimensions/exit-dimensions.md)维度）
* [!UICONTROL 信标UUID] （具有[进入](/help/components/dimensions/entry-dimensions.md)和[退出](/help/components/dimensions/exit-dimensions.md)维度）
* [!UICONTROL 位置（精确到 10 千米）]
* [!UICONTROL 位置（精确到 100 米）]
* [!UICONTROL 位置（精确到 1 米）]
* [!UICONTROL 目标点名称]
* [!UICONTROL 与目标点中心的距离]
* [!UICONTROL 目标点ID]

## [!UICONTROL 语音和聊天机器人]

[!UICONTROL 语音和聊天机器人]维度和量度允许您测量语音助手，如Alexa或Google主页。 它还允许您测量本土开发的聊天机器人。 测量属性包括：

* **生命周期**：任何应用程序的基础级别报表，例如启动次数和平台类型。
* **对话**：测量与对话相关的意图、响应及其他量度和维度。

启用[!UICONTROL 语音和聊天机器人]时，以下维度可用：

* [!UICONTROL 语音设备功能]（具有[进入](/help/components/dimensions/entry-dimensions.md)和[退出](/help/components/dimensions/exit-dimensions.md)维度）
* [!UICONTROL 语音身份验证]
* [!UICONTROL 语音错误类型]
* [!UICONTROL 语音意图]
* [!UICONTROL 语音应用响应]
* [!UICONTROL 语音语言]

以下量度可用：

* [!UICONTROL 语音结束会话]
* [!UICONTROL 语音错误]
* [!UICONTROL 语音语音]

## 后台点击量的旧版报告和归因

旧版报表是指当应用程序处于后台时生成的点击被视为常规前台点击。 它们显示在报表中并影响归因。 通常，需要此旧版配置来保持与旧版实施的一致性。

Adobe建议禁用旧版报表，以便不显示后台点击。 如果要在分析中包括后台点击，可以启用[虚拟报表包](/help/components/vrs/vrs-about.md)设置&#x200B;**[!UICONTROL 包括后台点击]**。
