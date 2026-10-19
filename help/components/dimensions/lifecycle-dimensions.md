---
title: 移动存留期维度
description: 基于使用Mobile SDK收集的数据的维度。
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
TQID: 'https://experienceleague.adobe.com/VUN8x5eMzIfJ9VGw76v2pWfKWU7b-ct-kI6liwWTObw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 8%
---
# 移动存留期维度

>[!BEGINSHADEBOX]

*此页面引用了通常通过Adobe Experience Platform Mobile SDK跟踪的数据。 有关使用用户代理的移动设备信息，请参阅[移动设备查找维度](mobile-dimensions.md)。 有关使用Mobile SDK跟踪的指标，请参阅[移动生命周期指标](../metrics/lifecycle-metrics.md)。*

>[!ENDSHADEBOX]

| 生命周期维度名称 | 描述 | 上下文数据变量 |
| --- | --- | --- |
| **[!UICONTROL 首次启动日期]** | 应用程序安装或重新安装后首次运行的日期（格式为`M/d/yyyy`）。 | `a.InstallDate` |
| **[!UICONTROL 设备名称(SDK)]** | SDK收集的设备名称。 | `a.DeviceName` |
| **[!UICONTROL 操作系统版本(SDK)]** | SDK收集的操作系统名称和版本。 | `a.OSVersion` |
| **[!UICONTROL 分辨率(SDK)]** | 设备的屏幕分辨率（以像素为单位），如宽度x高度。 | `a.Resolution` |
| **[!UICONTROL 客户获取Source]** | 应用程序客户获取促销活动（如新闻稿或社交媒体网络）的原始反向链接。 | `a.referrer.campaign.source` |
| **[!UICONTROL 应用程序ID]** | 应用程序名称和版本，格式为`AppName BundleVersion (app version code)`。 例如：`MyAppName 1.1(1)`。 | `a.AppID` |
| **[!UICONTROL 客户获取Medium]** | 应用程序客户获取促销活动的营销媒介，如横幅或电子邮件。 | `a.referrer.campaign.medium` |
| **[!UICONTROL 客户获取条件]** | 与应用程序客户获取促销活动关联的付费关键字或其他搜索词。 | `a.referrer.campaign.term` |
| **[!UICONTROL 客户获取内容]** | 显示应用程序客户获取链接的内容名称或ID。 | `a.referrer.campaign.content` |
| **[!UICONTROL 客户获取名称]** | 应用程序客户获取促销活动的名称。 | `a.referrer.campaign.name` |
| **[!UICONTROL 位置（精确到 10 千米）]** | 访客的纬度和经度，精确到小数点后的第一位。 例如，`040.9` `-111.9`。 | `a.loc.lat.a` + `a.loc.lon.a` |
| **[!UICONTROL 位置（精确到 100 米）]** | 访客的纬度和经度，精确到小数点后第三位。 例如，`040.932` `-111.931`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| **[!UICONTROL 位置（精确到 1 米）]** | 访客的纬度和经度，精确到小数点后第五位。 例如，`040.93231` `-111.93152`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| **[!UICONTROL 目标点名称]** | 设备所在的目标点(POI)的名称。 当您使用[Places扩展](https://developer.adobe.com/client-sdks/solution/places/)时，此值是Places区域名称。 | `a.loc.poi` |
| **[!UICONTROL 与目标点中心的距离]** | 设备与设备所在的目标点中心之间的距离。 | `a.loc.dist` |
| **[!UICONTROL 启动次数]** | 应用程序启动或移出后台的次数。 | `a.Launches` |
| **[!UICONTROL 首次使用后间隔天数]** | 距应用程序首次运行的间隔天数。 | `a.DaysSinceFirstUse` |
| **[!UICONTROL 操作名称]** | 在`trackAction`调用中发送的操作的名称。 | `a.action` |
| **[!UICONTROL 生命周期值(evar)]** | 用户的生命周期值，如生命周期购买、广告查看、视频完成或社交分享。 | `a.ltv.amount` |
| **[!UICONTROL 信标Major]** | 设备附近信标的主要ID。 | `a.beacon.major` |
| **[!UICONTROL 次要信标]** | 设备邻近的信标的次要ID。 | `a.beacon.minor` |
| **[!UICONTROL 信标UUID]** | 设备附近信标的UUID。 | `a.beacon.uuid` |
| **[!UICONTROL 邻近地区信标]** | 设备与信标的接近度： `0` （未知）、`1` （立即）、`2` （近）或`3` （远）。 | `a.beacon.prox` |
| **[!UICONTROL 上次使用后间隔天数]** | 距应用程序上次使用的间隔天数。 | `a.DaysSinceLastUse` |
| **[!UICONTROL 小时(SDK)]** | 应用程序启动的小时（24小时制）。 时间划分可用于确定峰值使用时间。 | `a.HourOfDay` |
| **[!UICONTROL 每周时间(SDK)]** | 应用程序在一周中的哪一天启动。 | `a.DayOfWeek` |
| **[!UICONTROL 目标点ID]** | 设备所在的目标点ID。 当您使用[Places扩展](https://developer.adobe.com/client-sdks/solution/places/)时，此值是Places区域ID。 | `a.loc.poi.id` |

>[!NOTE]
>
>其中某些维度由旧版Mobile Services SDK (4.x)中的方法填充，该版本不再受支持。 Adobe Experience Platform Mobile SDK不会自动填充这些变量：
>
>* **客户获取维度** （[!UICONTROL 客户获取Source]、[!UICONTROL Medium]、[!UICONTROL Term]、[!UICONTROL Content]和[!UICONTROL Name]）：由移动设备应用程序客户获取填充，而移动设备SDK [不支持该功能](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/comparison/)。
>* **[!UICONTROL 位置]维度和[!UICONTROL 与目标点中心的距离]**：由4.x `trackLocation`方法填充。 Mobile SDK将此方法替换为[Places扩展](https://developer.adobe.com/client-sdks/solution/places/)，该扩展会填充[!UICONTROL 目标点名称]和[!UICONTROL 目标点ID]。
>* **[!UICONTROL 生命周期值(evar)]**：由4.x `trackLifetimeValueIncrease`方法填充。
>* **信标维度** （[!UICONTROL Beacon Major]、[!UICONTROL Minor]、[!UICONTROL UUID]和[!UICONTROL Proximity]）：由4.x `trackBeacon`方法填充。 要使用Mobile SDK发送信标数据，请参阅[跟踪信标](https://developer.adobe.com/client-sdks/solution/adobe-analytics/track-beacon/)。
>
>有关详细信息，请参阅[Adobe Mobile Library (v4)到Experience Platform Analytics的迁移](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/)。
