---
title: 移动生命周期维度
description: 基于使用Mobile SDK收集的数据的Dimension。
feature: Dimensions
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 55%

---

# 移动生命周期维度

*本页引用了通常通过Adobe Experience Platform Mobile SDK跟踪的数据。 有关使用用户代理的移动设备信息，请参阅 [移动设备查找维度](mobile-dimensions.md). 有关使用Mobile SDK跟踪的量度，请参阅 [移动生命周期量度](../metrics/lifecycle-metrics.md).*

| 生命周期维度名称 | 描述 | 上下文数据变量 |
| --- | --- | --- |
| [!UICONTROL 首次启动日期] | | TBD（此安装日期是否？） |
| [!UICONTROL 设备名称 (SDK)] | | `a.DeviceName` |
| [!UICONTROL 操作系统版本 (SDK)] | | `a.OSVersion` |
| [!UICONTROL 分辨率(SDK)] | | `a.Resolution` |
| [!UICONTROL 客户获取来源] | | `a.referrer.campaign.source` |
| [!UICONTROL 应用程序 ID] | | `a.AppID` |
| [!UICONTROL 客户获取媒介] | | `a.referrer.campaign.medium` |
| [!UICONTROL 客户获取搜索词] | | `a.referrer.campaign.term` |
| [!UICONTROL 客户获取内容] | | `a.refferer.campaign.content` |
| [!UICONTROL 客户获取名称] | | `a.referrer.campaign.name` |
| [!UICONTROL 位置（精确到 10 千米）] | | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL 位置（精确到 100 米）] | | `a.loc.lat.b` + `a.loc.lon.b` |
| [!UICONTROL 位置（精确到 1 米）] | | `a.loc.lat.c` + `a.loc.lon.c` |
| [!UICONTROL 目标点名称] | | `a.loc.poi` |
| [!UICONTROL 与目标点中心的距离] | | `a.loc.dist` |
| [!UICONTROL 启动次数] | | `a.Launches` |
| [!UICONTROL 首次使用后间隔天数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL 操作名称] | | 待定 |
| [!UICONTROL 存留期价值 (evar)] | | `a.ltv.amount` |
| [!UICONTROL 信标 Major] | | 待定 |
| [!UICONTROL 信标 Minor] | | 待定 |
| [!UICONTROL 信标 UUID] | | 待定 |
| [!UICONTROL 信标 Proximity] | | 待定 |
| [!UICONTROL 上次使用后间隔天数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL 小时 (SDK)] | | `a.HourOfDay` |
| [!UICONTROL 每周时间 (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL 目标点ID] | | 待定 |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
