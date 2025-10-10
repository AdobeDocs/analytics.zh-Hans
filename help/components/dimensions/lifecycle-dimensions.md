---
title: 移动存留期维度
description: 基于使用Mobile SDK收集的数据的维度。
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: 4c472d9a99f15ed253b68124aa31bdc88554d9a5
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 26%

---

# 移动存留期维度

*此页面引用了通常通过Adobe Experience Platform Mobile SDK跟踪的数据。 有关使用用户代理的移动设备信息，请参阅[移动设备查找维度](mobile-dimensions.md)。 有关使用Mobile SDK跟踪的指标，请参阅[移动生命周期指标](../metrics/lifecycle-metrics.md)。*

| 生命周期维度名称 | 描述 | 上下文数据变量 |
| --- | --- | --- |
| [!UICONTROL 首次启动日期] | | 待定 |
| [!UICONTROL 设备名称(SDK)] | | `a.DeviceName` |
| [!UICONTROL 操作系统版本(SDK)] | | `a.OSVersion` |
| [!UICONTROL 分辨率(SDK)] | | `a.Resolution` |
| [!UICONTROL 客户获取Source] | | `a.referrer.campaign.source` |
| [!UICONTROL 应用程序ID] | | `a.AppID` |
| [!UICONTROL 客户获取Medium] | | `a.referrer.campaign.medium` |
| [!UICONTROL 客户获取条件] | | `a.referrer.campaign.term` |
| [!UICONTROL 客户获取内容] | | `a.refferer.campaign.content` |
| [!UICONTROL 客户获取名称] | | `a.referrer.campaign.name` |
| [!UICONTROL 位置（精确到 10 千米）] | 访客的纬度和经度，精确到小数点后的第一位。 例如，`040.9` `-111.9`。 | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL 位置（精确到 100 米）] | 访客的纬度和经度，精确到小数点后第三位。 例如，`040.932` `-111.931`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| [!UICONTROL 位置（精确到 1 米）] | 访客的纬度和经度，精确到小数点后第五位。 例如，`040.93231` `-111.93152`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| [!UICONTROL 目标点名称] | | `a.loc.poi` |
| [!UICONTROL 与目标点中心的距离] | | `a.loc.dist` |
| [!UICONTROL 启动次数] | | `a.Launches` |
| [!UICONTROL 首次使用后间隔天数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL 操作名称] | | 待定 |
| [!UICONTROL 生命周期值(evar)] | | `a.ltv.amount` |
| [!UICONTROL 信标Major] | | 待定 |
| [!UICONTROL 次要信标] | | 待定 |
| [!UICONTROL 信标UUID] | | 待定 |
| [!UICONTROL 邻近地区信标] | | 待定 |
| [!UICONTROL 上次使用后间隔天数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL 小时(SDK)] | | `a.HourOfDay` |
| [!UICONTROL 每周时间(SDK)] | | `a.DayOfWeek` |
| [!UICONTROL 目标点ID] | | 待定 |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
