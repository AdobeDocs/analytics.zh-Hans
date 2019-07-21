---
description: 启用移动设备管理可激活移动设备解决方案变量，以便从移动设备应用程序中捕获生命周期和其他量度。
seo-description: 启用移动设备管理可激活移动设备解决方案变量，以便从移动设备应用程序中捕获生命周期和其他量度。
seo-title: 移动设备管理
solution: Analytics
title: 移动设备管理
topic: 管理工具
uuid: d09edf72-bb91-422d-b22 c-7b6971 f228 de
translation-type: tm+mt
source-git-commit: 6184104b5a46242c5973552298964e96ff671d7c

---


# 移动设备管理

启用移动设备管理可激活移动设备解决方案变量，以便从移动设备应用程序中捕获生命周期和其他量度。

Adobe Analytics 与 Mobile Services 之间的此集成

* 允许您将 KPI（关键绩效指标）数据从 Mobile Services 共享到 Adobe Analytics。
* 允许您启用位置跟踪。
* 在“Analytics”&gt;“报表”&gt;“移动设备应用程序”下添加了新报表。
* 添加了 25 个新的 Adobe Mobile 分类。
* 添加了 5 个新的 Adobe Mobile 量度。
* 添加 个新的 Adobe Mobile 维度。
* 每隔 15 分钟将数据同步到 Analytics。

**[!UICONTROL “分析]** ”&gt;“ **[!UICONTROL 管理员]** ”&gt; **[!UICONTROL “报告包]** ”&gt; **[!UICONTROL “编辑设置]** ”&gt; **[!UICONTROL “Mobile Management”]** &gt; **[!UICONTROL “Mobile Application Reporting]**”。

## 步骤 1. 启用应用程序报表 {#section_FBADF80AED2B4978A904ABB770B3B931}

启用应用程序报表 v3.0 以测量以下量度：

* **客户获取** - 跟踪应用程序下载促销活动的反向链接 URL。
* **生命周期** - 报告的基础级别，由每次应用程序启动时发送的测量提供。
* **应用程序操作** - 基于应用程序内操作的报表和路径。
* **存留期价值** - 了解用户如何使用应用程序 KPI（例如购买、广告查看、视频完成、社交分享、照片上载），让价值随着时间增长。
* **定时事件** - 测量各个关键应用程序操作之间经过的时间量（包括应用程序内的时间和总时间），例如第一次购买之前的时间。

## 步骤 2. 启用位置跟踪 {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

启用位置跟踪使您能够：

* 跟踪纬度和经度数据并在 Analysis Workspace 和 Mobile Services 中报告该数据。
* 在 Mobile Services 内识别、创建和可视化特定目标点 (POI)。POI 必须在移动 SDK 配置文件中定义。
* 跟踪蓝牙信标（UUID、major、minor 和 proximity）。

## 步骤 3. （可选）启用/禁用“计算后台点击量的旧版报告和属性”{#section_1708BCAA87AA4884986F7532759C5DD4}

启用后台点击量（在应用程序处于后台时产生的点击量）意味着它们将被视为常规的前台点击量。这些点击量当前显示在常规报表中，并且这还会影响属性。此配置通常只是用来保持与旧版实施的一致性。

我们则建议您在[虚拟报表包](../../components/vrs/vrs-about.md)中“包含后台点击量”。这允许您查看这些点击量，但它们不会对访问和访客计数产生不良影响。Mobile classifications are enabled after you enable **[!UICONTROL Mobile Management]** &gt; **[!UICONTROL Mobile Application Reporting]**.

分类可用于将值分组并在组级别进行报告。例如，您可将所有“付费搜索”促销活动划分到诸如“流行音乐搜索词”类别，并报告与“实例”（也称“点进次数”）量度相关的类别成功以及到成功事件的转化。

| 分类 | 定义 |
|--- |--- |
| 首次启动日期 | 安装或重新安装后首次启动的日期。YYYY/MM/DD |
| 应用程序 ID | 采用以下格式存储应用程序名称和版本：`[AppName] [BundleVersion]` 例如， `myapp 1.1.` |
| 启动次数 | 应用程序启动或移出后台的次数。 |
| 首次使用后间隔天数 | 自首次运行以来经过的天数。 |
| 上次使用后间隔天数 | 上次使用后间隔的天数。 |
| 小时 | 测量应用程序启动的小时，采用 24 小时制数字格式。用于时间分片以确定峰值使用时间。 |
| 星期 | 应用程序星期几启动。 |
| 设备名称 | 存储设备名称。以逗号分隔的两位数字字符串，用于标识 设备。第一个数字通常代表第几代设备，第二个数字通常注释设备系列的不同成员。 |
| 操作系统版本 | 操作系统版本。 |
| 分辨率 | 宽 x 高（以实际像素为单位）。 |
| 存留期价值 (eVar) | 由 trackLifetimeValue 方法填充。 |
| 客户获取来源 |  |
| 客户获取媒介 |  |
| 客户获取搜索词 |  |
| 客户获取内容 |  |
| 客户获取名称 |  |
| 位置（精确到 10 千米） | 由 trackLocation 方法填充。 |
| 位置（精确到 100 米） | 由 trackLocation 方法填充。 |
| 位置（精确到 1 米） | 由 trackLocation 方法填充。 |
| 目标点名称 | 当设备位于定义的 POI 中时，由 trackLocation 方法填充。 |
| 与目标点中心的距离 | 当设备位于定义的 POI 中时，由 trackLocation 方法填充。 |
| 应用程序内消息 ID |  |
| 应用程序内消息在线 |  |
| 允许推送 |  |
| 负载 ID |  |

