---
description: 介绍为将组件和项目从Adobe Analytics迁移到Customer Journey Analytics所做的必要准备。
title: 准备将组件和项目从Adobe Analytics迁移到Customer Journey Analytics
feature: Admin Tools
exl-id: a9ff98dc-6568-428d-a8a8-faca5bc76a29
source-git-commit: df9c6d59ef5f5c43d0e1ef822bd23bc0e09ff20e
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 9%

---

# 准备将组件和项目从Adobe Analytics迁移到Customer Journey Analytics

在您组织中的任何人开始迁移项目之前（如所述） [将组件和项目从Adobe Analytics迁移到Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md)，请完成以下部分。

## 先决条件

在项目及其相关组件准备好迁移之前，您首先需要执行中的步骤 [Adobe Analytics的演变](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=zh-Hans) 在《Adobe Customer Journey Analytics指南》中。 这些步骤包括：

1. 使用以下任一方法将数据摄取到Adobe Experience Platform中，以便在Customer Journey Analytics中查看Adobe Analytics报表包数据：

   >[!NOTE]
   >
   >  在使用WebSDK摄取数据时，必须手动映射所有架构字段。 (有关映射过程的详细信息，请参见 [将组件和项目从Adobe Analytics迁移到Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md))


   * 要使用Adobe Analytics源连接器，您需要：

      1. [设置报表包以引入Adobe Experience Platform和Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [摄取和使用数据](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=zh-Hans)

   * 要使用WebSDK，您需要：

      1. [设置报表包以引入Adobe Experience Platform和Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [通过Adobe Experience Platform Web SDK引入数据](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html)

1. 创建 [连接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html) 和 [数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html) 并摄取数据。

1. 确保Customer Journey Analytics中的用户已设置到正在映射数据的数据视图。

   有关更多信息，请参阅 [Admin Console中的Customer Journey Analytics权限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) 在 [Customer Journey Analytics访问控制](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

   “权限”选项卡是Admin Console中每个产品配置文件的一部分。 您可以将用户添加到特定的产品配置文件。然后，将权限分配给特定的数据视图，并指定用户在产品配置文件中拥有的权限。

1. 作为一个组织，决定如何映射组件。

   有关更多信息，请参阅以下部分， [作为组织决定如何映射组件](#decide-as-an-organization-how-you-will-map-components).

## 了解迁移中包含的内容

下表概述了迁移中包含的项目和组件元素：

### 已迁移的组件元素

Dimension和量度将作为映射过程的一部分进行迁移，如中所述 [将Adobe Analytics项目迁移到Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics).

Customer Journey Analytics中尚未存在的区段、日期范围和计算指标会根据映射的维度和指标在此处重新创建。

|  | 已迁移 |
|---------|---------|
| **[所有者](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | Dimension和指标：否<p>区段和日期范围： ![复选标记](assets/Smock_Checkmark_18_N.svg)</p> |
| **[共享](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimension和指标：否<p>区段和日期范围：否</p> |
| **[描述](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimension和指标：否<p>区段和日期范围： ![复选标记](assets/Smock_Checkmark_18_N.svg)</p> |
| **[标记](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimension和指标：否<p>区段和日期范围：否</p> |
| **[归因（在维度上）](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimension和指标：否<p>区段和日期范围：否</p> |

{style="table-layout:auto"}

### 迁移的项目元素

|  | 已迁移 |
|---------|----------|
| **[日期范围](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![复选标记](assets/Smock_Checkmark_18_N.svg) |
| **[区段](/help/components/segmentation/seg-overview.md)** | ![复选标记](assets/Smock_Checkmark_18_N.svg) |
| **[快速区段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![复选标记](assets/Smock_Checkmark_18_N.svg) |
| **[维度](/help/components/dimensions/overview.md)** | ![复选标记](assets/Smock_Checkmark_18_N.svg) 自动或手动映射 |
| **[指标](/help/components/metrics/overview.md)** | ![复选标记](assets/Smock_Checkmark_18_N.svg) 自动或手动映射 |
| **[面板](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![复选标记](assets/Smock_Checkmark_18_N.svg) |
| **[可视化图表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![复选标记](assets/Smock_Checkmark_18_N.svg) |
| **[所有者](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![复选标记](assets/Smock_Checkmark_18_N.svg) 由执行迁移的用户定义 |
| **[策划](/help/analyze/analysis-workspace/curate-share/curate.md)** | 否 |
| **[共享](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | 否 |
| **[注释](/help/analyze/analysis-workspace/components/annotations/overview.md)** | 否 |
| **[文件夹结构](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | 否 |
| **[描述](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![复选标记](assets/Smock_Checkmark_18_N.svg) |
| **[标记](/help/analyze/landing.md)** | 否 |
| **[收藏夹](/help/analyze/landing.md)** | 否 |
| **[时间表](/help/components/scheduled-projects-manager.md)** | 否 |
| **[异常检测](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)** | ![复选标记](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## 了解导致错误的不支持的元素

Customer Journey Analytics不支持以下可视化和面板。 如果在迁移之前将这些元素包含在项目中，则它们可能会导致迁移失败，或者会在迁移项目后导致错误。

在将项目迁移到Customer Journey Analytics之前，请从Adobe Analytics项目中删除这些元素。 如果迁移失败，请在重试迁移之前删除这些元素。

### 不支持的可视化图表

* [地图](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

### 不支持的面板

* [Analytics for Target (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [区段比较](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [媒体平均受众访问分钟数](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [下一个或上一个项目](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [页面摘要](/help/analyze/analysis-workspace/c-panels/page-summary.md)

* [贡献分析](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)

## 作为组织决定如何映射组件

>[!IMPORTANT]
>
>迁移过程会识别Adobe Analytics项目中无法自动映射到Customer Journey Analytics中组件的组件，并且允许您手动映射这些组件。
>
>**对一个项目所做的任何映射都适用于整个IMS组织中的所有未来项目，无论哪个用户正在执行迁移。 除非联系客户关怀团队，否则无法修改或撤消这些映射。**
>
>因此，在迁移任何项目之前，贵组织必须决定如何映射维度和量度，这一点非常重要。 这样做可避免单个管理员在仅考虑单个项目时在思洛存储器中进行决策。
>
>以下是您必须手动映射的维度和量度列表（如果项目中存在这些维度和量度）。 我们建议您在迁移之前查看此列表。 如果项目中存在这些组件中的任何组件，请立即决定要将它们映射到哪些Customer Journey Analytics组件。


### 必须手动映射的Dimension

* averagepagetime
* pagetimeseconds
* singlepagevisits
* visitnumber
* timeprior
* timespent
* category
* connectiontype
* customerloyalty
* customlink
* downloadlink
* exitlink
* hitdepth
* hittype
* pathlength
* daysbeforefirstpurchase
* dayssincelastpurchase
* dayssincelastvisit
* identificationstate
* optoutreason
* persistentcookie
* returnfrequency
* searchenginenatural
* searchenginenaturalkeyword
* mobilecarrier
* monitorresolution
* surveybase
* mcaudiences
* tntbase
* targetraw


### 必须手动映射的量度

* timespentvisit
* timespentvisitor
* 重新载入
* bounces
* 退回
* pageevents
* pageviewspervisit
* orderspervisit
* averagepagedepth
* averagetimespentonsite
* 退出实例
* 自定义实例
* 下载链接实例
* 黑暗访客
* singlepagevisits
* singlevaluevisits
* visitorhomepage
* visitorsmcvisid
* pagesnotfound
* 新参与
* time_granular
* concurrent_viewers_visitors
* concurrent_viewers_occurrences
* 设备
* estimatedpeople
* playback_time_spent_seconds
* playback_time_spent_minutes
* average_minute_audience_time_based
* average_minute_audience_media_time
* average_minute_audience_content_time
* video_length
* 目标转换
* targetetimpression
