---
description: 介绍如何将组件和项目从Adobe Analytics迁移到Customer Journey Analytics。
title: 将组件和项目从Adobe Analytics迁移到Customer Journey Analytics
feature: Admin Tools
source-git-commit: e32b239fd64eea4516bc73b934b10346832f2bab
workflow-type: tm+mt
source-wordcount: '2051'
ht-degree: 8%

---

# 将组件和项目从Adobe Analytics迁移到Customer Journey Analytics

Adobe Analytics管理员可以将Adobe Analytics项目及其相关组件迁移到Customer Journey Analytics。

迁移过程包括：

* 在Customer Journey Analytics中重新创建Adobe Analytics项目。

* 将Adobe Analytics报表包中的维度和量度映射到Customer Journey Analytics数据视图中的维度和量度。

  某些维度和量度会自动映射；其他维度和量度必须在迁移过程中手动映射。 区段也会迁移，但无需在迁移过程中映射这些区段。

  迁移完成后，所有已迁移的组件都会显示在迁移摘要中。

## 准备迁移

在您组织中的任何人开始迁移项目之前，请完成以下部分。

### 先决条件

在准备好迁移项目及其相关组件之前，您首先需要：

* 使用Analytics Source Connector在Customer Journey Analytics中查看Adobe Analytics报告包数据。 为此，您需要：

   * [设置报表包以引入Adobe Experience Platform和Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [摄取和使用数据](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=zh-Hans)

* 确保Customer Journey Analytics中的用户已设置到正在映射数据的数据视图。

  有关更多信息，请参阅 [Admin Console中的Customer Journey Analytics权限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) 在 [Customer Journey Analytics访问控制](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  权限选项卡是 Admin Console 中每个产品配置文件的一部分。您可以将用户添加到特定的产品配置文件。然后将权限分配给特定的数据视图，并指定用户在产品配置文件中拥有的权限。

* 创建迁移计划，如以下部分所述， [创建迁移计划作为组织](#create-a-migration-plan-as-an-organization).

### 了解迁移中包含的内容

下表概述了迁移中包含的项目和组件元素：

#### 已迁移的组件元素

Dimension和量度将作为映射过程的一部分进行迁移，如中所述 [将Adobe Analytics项目迁移到Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics)Customer Journey Analytics ，而区段和日期范围则是根据

|  | 已迁移 |
|---------|---------|
| **[所有者](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | Dimension和指标：否<p>区段和日期范围： ![复选标记](assets/Smock_Checkmark_18_N.svg)</p> |
| **[共享](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimension和指标：否<p>区段和日期范围：否</p> |
| **[描述](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimension和指标：否<p>区段和日期范围： ![复选标记](assets/Smock_Checkmark_18_N.svg)</p> |
| **[标记](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimension和指标：否<p>区段和日期范围：否</p> |
| **[归因（在维度上）](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimension和指标：否<p>区段和日期范围：否</p> |

{style="table-layout:auto"}

#### 迁移的项目元素

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
| **[共享（项目角色）](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | 否 <!-- Add info on Share with Anyone? Is it the same?--> |
| **[批注](/help/analyze/analysis-workspace/components/annotations/overview.md)** | 否 |
| **[文件夹结构](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | 否 |
| **[描述](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![复选标记](assets/Smock_Checkmark_18_N.svg) |
| **[标记](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | 否 |
| **[时间表](/help/components/scheduled-projects-manager.md)** | 否 |

{style="table-layout:auto"}

<!-- What about Anomaly Detection and Favorites? -->

### 了解导致错误的不支持的元素

Customer Journey Analytics不支持以下可视化图表、面板和功能。 如果在迁移之前将这些元素包含在项目中，则它们可能会导致迁移失败，或者会在迁移项目后导致错误。

在将项目迁移到Customer Journey Analytics之前，请从Adobe Analytics项目中删除这些元素。 如果迁移失败，请在重试迁移之前删除这些元素。

#### 不支持的可视化图表

* [地图](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

#### 不支持的面板

* [Analytics for Target (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [区段比较](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [媒体平均受众访问分钟数](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [下一个或上一个项目](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [页面摘要](/help/analyze/analysis-workspace/c-panels/page-summary.md)

#### 不支持的功能

* [贡献分析](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md)

* [警报](/help/components/c-alerts/intellligent-alerts.md)

### 作为组织决定如何映射组件

>[!IMPORTANT]
>
>迁移过程会识别Adobe Analytics项目中无法自动映射到Customer Journey Analytics中组件的组件，并且允许您手动映射这些组件。
>
>**对一个项目所做的任何映射都将应用于整个组织中的所有未来项目，而不管哪个用户正在执行迁移。 除非联系客户关怀团队，否则无法修改或撤消这些映射。**
>
>因此，在迁移任何项目之前，贵组织必须决定如何映射维度和量度，这一点非常重要。 这样做可避免单个管理员在仅考虑单个项目时在思洛存储器中进行决策。
>
>以下是您必须手动映射的维度和量度列表（如果项目中存在这些维度和量度）。 我们建议您在迁移之前查看此列表。 如果项目中存在这些组件中的任何组件，请立即决定要将它们映射到哪些Customer Journey Analytics组件。


#### 必须手动映射的Dimension

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


#### 必须手动映射的量度

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


## 将Adobe Analytics项目迁移到Customer Journey Analytics

>[!IMPORTANT]
>
>在将任何项目迁移到Customer Journey Analytics（如本节所述）之前，请通过了解 [规划迁移](#plan-the-migration) 部分。
>
>您映射的任何维度或量度对于此项目以及在整个组织中迁移的所有未来项目都是永久性的。 迁移完成后，无法修改您创建的任何映射。

1. 在 Adobe Analytics 中，选择&#x200B;[!UICONTROL **管理员**]&#x200B;选项卡，然后选择&#x200B;[!UICONTROL **所有管理员**]。

1. 下 [!UICONTROL **数据配置和收集**]，选择 [!UICONTROL **组件迁移**].

1. 找到要迁移的项目。 您可以过滤、排序或搜索项目列表。

   默认情况下，仅显示与您共享的项目。 要查看您组织中的所有项目，请选择 **筛选** 图标，然后展开 [!UICONTROL **其他筛选器**] 并选择 [!UICONTROL **显示全部**]. (有关筛选、排序和搜索项目列表的详细信息，请参阅 [筛选、排序和搜索项目列表](#filter-sort-and-search-the-list-of-projects).)

1. 将鼠标悬停在要迁移的项目上，然后选择 **迁移** 图标 ![迁移项目](assets/migrate.svg).

   或

   选择要迁移的项目，然后选择 [!UICONTROL **迁移到Customer Journey Analytics**].

   一次只能选择一个要迁移的项目。

   此 [!UICONTROL **将project_name迁移到Customer Journey Analytics**] 对话框随即显示。

   <!-- add screenshot -->

1. 在 [!UICONTROL **项目所有者**] 字段中，开始键入要在Customer Journey Analytics中设置为项目所有者的用户的名称，然后在下拉菜单中选择其名称。

   您指定的所有者拥有对该项目的所有管理权限.

1. 在 [!UICONTROL **映射报表包的架构**] 部分，选择一个报表包。

1. 在 [!UICONTROL **数据视图**] 下拉菜单中，选择要将项目和组件迁移到的Customer Journey Analytics数据视图。

1. 选择 [!UICONTROL **映射架构**].

1. 在 [!UICONTROL **映射架构**] 部分，展开 [!UICONTROL **Dimension**] 和 [!UICONTROL **量度**] 部分。

   Adobe Analytics中的某些维度和量度会自动映射到Customer Journey Analytics中的维度或量度。 其他则需要手动映射。

   **自动映射维度和量度**

   Adobe Analytics中的某些维度和量度会自动映射到Customer Journey Analytics中的维度或量度。 您无法为这些维度和量度做出任何映射决策。

   例如， **访问** Adobe Analytics中的量度自动映射到 **会话** Customer Journey Analytics中的指标。

   您可以选择任意维度或量度以查看其关联的ID。

   <!-- update screenshot after I can see the Status column -->

   ![项目迁移模式](assets/project-migration-schema.png)

   **手动映射维度和量度**

   Adobe Analytics中的某些维度和量度无法自动映射到Customer Journey Analytics中的维度或量度。

   当维度或量度无法自动映射时，橙色计数器显示在 [!UICONTROL **Dimension**] 或 [!UICONTROL **量度**] 章节标题，指示需要手动映射的维度或量度数量。 在表中，有一个警告图标 ![警告图标](assets/schema-warning.png) 显示在需要手动映射的每个维度或量度旁边。

   此外， [!UICONTROL **状态**] 列显示 [!UICONTROL **未映射**].

   <!-- update screenshot after I can see the Status column -->

   ![迁移模式手动映射](assets/schema-manual-map.png)

1. 要手动映射维度和指标，请选择包含警告图标的维度或指标 ![警告图标](assets/schema-warning.png)，然后在 [!UICONTROL **映射的Customer Journey Analytics指标**] 字段(或 [!UICONTROL **映射的Customer Journey Analytics维度**] 字段（如果要映射维），在Customer Journey Analytics中选择要映射到所选维或度量的维或度量。

   ![映射维度和量度](assets/schema-manual-map-drop-down.png)

   映射维度或量度后，警告图标消失，并且 [!UICONTROL **状态**] 列更改为 [!UICONTROL **已映射**] 绿色圆点。 (状态 [!UICONTROL **已映射**] 灰点表示在上次迁移期间映射了维度或量度；无法更新任何以前的映射。)

   对包含警告图标的每个维度或量度重复此过程。

   将Adobe Analytics报表包中的所有维度和量度映射到Customer Journey Analytics数据视图中的维度或量度后，会出现一个绿色复选标记 ![复选标记](assets/report-suite-check.png) 显示在中的报表包名称旁边 [!UICONTROL **映射报表包的架构**] 部分。

1. （视情况而定）如果要迁移的项目包含多个报表包，请在 [!UICONTROL **映射报表包的架构**] 部分，然后重复步骤6到步骤10。 <!-- double-check that the step numbers are still correct -->

1. 选择 [!UICONTROL **迁移**].

   >[!WARNING]
   >
   >   选择后，屏幕上会显示警告消息 [!UICONTROL **迁移**]. 在选择继续之前，请了解您映射的任何维度或量度对于此项目以及迁移整个组织的所有未来项目都是永久性的。 如果继续，将无法修改您所做的映射。

   迁移完成后， [!UICONTROL **迁移状态**] 页面提供了已迁移内容的摘要。

   如果迁移失败，请参阅 [重试失败的迁移](#retry-a-failed-migration) 部分以了解更多信息。

## 重试失败的迁移

如果迁移失败，您可以重试迁移。

在重试失败的迁移之前，请确保删除所有 [不支持的元素](#understand-unsupported-elements-that-cause-errors) 项目中的。

>[!NOTE]
>
>如果重试后迁移继续失败，请联系客户关怀团队并提供项目ID。 您可以在迁移状态页面中找到项目ID。 <!-- when does this page display? How can they get there -->

要重试失败的迁移，请执行以下操作：

1. 在 Adobe Analytics 中，选择&#x200B;[!UICONTROL **管理员**]&#x200B;选项卡，然后选择&#x200B;[!UICONTROL **所有管理员**]。

1. 下 [!UICONTROL **数据配置和收集**]，选择 [!UICONTROL **组件迁移**].

1. 选择 [!UICONTROL **失败**] 在 [!UICONTROL **迁移状态**] 要重试的项目旁边的列。

   ![迁移状态列失败](assets/migration-failed.png)

   此 [!UICONTROL **迁移状态**] 页面显示。

   完成一节中所述的迁移步骤后，此页面也会立即显示 [将Adobe Analytics项目迁移到Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) 以上。

1. 选择 [!UICONTROL **重试迁移**].

## 筛选、排序和搜索项目列表

您可以在组件迁移页面上过滤、排序和搜索项目列表。

### 筛选项目列表

您可以按以下条件进行筛选：

| 过滤器 | 描述 |
|---------|----------|
| [!UICONTROL **状态**] | 迁移的状态： <ul><li>[!UICONTROL **未开始**]</li><li>[!UICONTROL **开始时间**]</li><li>[!UICONTROL **已完成**]</li><li>[!UICONTROL **失败**]</li></ul>。 |
| [!UICONTROL **标记**] | 选择标记列表中的任意标记。 仅显示应用了选定标记的项目。 |
| [!UICONTROL **报表包**] | 在报表包列表中选择任意报表包。 仅显示使用选定报表包的项目。 |
| [!UICONTROL **所有者**] | 选择所有者列表中的任意所有者。 仅显示您选择的用户拥有的项目。 |
| [!UICONTROL **其他筛选条件**] | 还提供以下附加过滤器： <ul><li>[!UICONTROL **我的**]：仅显示您设置为所有者的项目。</li><li>[!UICONTROL **与我共享**]：仅显示与您共享的项目。</li><li>[!UICONTROL **收藏夹**]：仅显示标记为收藏的项目。 (您可以从以下位置将项目标记为收藏： [项目登陆页面](/help/analyze/landing.md).)</li><li>[!UICONTROL **每月**]</li><li>[!UICONTROL **每年**]</li></ul> |

{style="table-layout:auto"}

### 对项目列表进行排序

您可以按任何列对项目列表进行排序。

要对项目列表进行排序，请执行以下操作：

1. 选择要作为排序依据的列的列标题。

1. （可选）再次选择相同的列标题以反转排序顺序。

### 搜索项目

您可以在“组件迁移”页面上搜索项目列表，以查找要迁移的项目。

1. 在组件迁移页面顶部的搜索字段中，开始键入要迁移的项目名称。

1. 当项目出现在下拉菜单中时，选择该项目。

<!-- is there going to be a way to customize the columns that are displayed? -->
