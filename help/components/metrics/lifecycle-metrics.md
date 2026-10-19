---
title: 移动存留期量度
description: 基于使用移动 SDK 收集的数据的量度。
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
TQID: 'https://experienceleague.adobe.com/Y1IigGbQygTsS9UD3WEp9z8rLTqkeDuhZZ83AJQMa3o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 10%
---
# 移动存留期量度

>[!BEGINSHADEBOX]

*此页面引用了通常通过Adobe Experience Platform Mobile SDK跟踪的数据。 有关使用Mobile SDK跟踪的维度，请参阅[移动生命周期维度](../dimensions/lifecycle-dimensions.md)。 有关使用用户代理的移动设备信息，请参阅[移动设备查找维度](../dimensions/mobile-dimensions.md)。*

>[!ENDSHADEBOX]

| 存留期量度名称 | 描述 | 上下文数据变量 |
| --- | --- | --- |
| **[!UICONTROL 首次启动次数]** | 安装或重新安装应用程序后首次运行的次数。 | `a.InstallEvent` |
| **[!UICONTROL 升级]** | 应用程序在升级后或版本号更改后首次运行的次数。 | `a.UpgradeEvent` |
| **[!UICONTROL 启动项]** | 应用程序运行的次数，包括在崩溃和安装后运行的次数。 在超出生命周期会话超时后，当应用程序从后台恢复时，也会计算启动次数。 | `a.LaunchEvent` |
| **[!UICONTROL 崩溃]** | 应用程序在关闭前崩溃的次数。 下次启动应用程序时，将报告崩溃。 | `a.CrashEvent` |
| **[!UICONTROL 会话总时长]** | 应用程序会话持续的总秒数，基于应用程序在前台打开时间的长短。 每个启动项都会报告上一个会话的时长；此量度是这些值的总和。 | `a.PrevSessionLength` |
| **[!UICONTROL 总操作时间]** | 定时操作的开始和结束之间跨会话的总秒数（时钟时间）。 由旧版Mobile Services SDK (4.x)中的`trackTimedAction`方法填充。 | `a.action.time.total` |
| **[!UICONTROL 应用程序中的操作时间]** | 从定时操作开始到结束期间跨会话在应用程序中花费的秒数。 由旧版Mobile Services SDK (4.x)中的`trackTimedAction`方法填充。 | `a.action.time.inapp` |
| **[!UICONTROL 生命周期值（事件）]** | 用户的生命周期值，如生命周期购买、广告查看、视频完成或社交分享。 由旧版Mobile Services SDK (4.x)中的`trackLifetimeValueIncrease`方法填充。 | `a.ltv.amount` |

>[!NOTE]
>
>[!UICONTROL 操作时间总计]、[!UICONTROL 应用程序中的操作时间]和[!UICONTROL 生命周期值（事件）]量度由旧版Mobile Services SDK (4.x)中的方法填充，该方法不再受支持。 Adobe Experience Platform Mobile SDK不会自动填充这些指标。 有关定时操作和生命周期值跟踪的替代方法，请参阅[Adobe Mobile Library (v4)到Experience Platform Analytics的迁移](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/)。
