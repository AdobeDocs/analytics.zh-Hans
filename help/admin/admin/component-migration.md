---
description: 介绍如何将组件和项目从Adobe Analytics迁移到Customer Journey Analytics。
title: 将组件和项目从Adobe Analytics迁移到Customer Journey Analytics
feature: Admin Tools
source-git-commit: 8eb26f7aa3dcbb21f4d0c042b8d6958aa0a19cf6
workflow-type: tm+mt
source-wordcount: '1649'
ht-degree: 9%

---

# 将组件和项目从Adobe Analytics迁移到Customer Journey Analytics

Adobe Analytics管理员可以将Adobe Analytics组件和项目迁移到Customer Journey Analytics。

迁移过程包括：

* 在Customer Journey Analytics中重新创建Adobe Analytics项目。

* 将Adobe Analytics报表包中的维度和量度映射到Customer Journey Analytics数据视图中的维度和量度。

  某些维度和量度会自动映射；其他维度和量度必须在迁移过程中手动映射。

## 准备迁移

在开始迁移组织中的项目之前，请完成前提条件，了解哪些项目已迁移，哪些项目未迁移，并为组织创建迁移计划。

### 先决条件

在准备好迁移项目及其关联的维度和量度之前，您首先需要：

* 使用Analytics Source Connector在Customer Journey Analytics中查看Adobe Analytics报告包数据。 为此，您需要：

   * [设置报表包以引入Adobe Experience Platform和Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [摄取和使用数据](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=zh-Hans)

* 确保Customer Journey Analytics中的用户已设置到正在映射数据的数据视图。

  有关更多信息，请参阅 [Admin Console中的Customer Journey Analytics权限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) 在 [Customer Journey Analytics访问控制](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  权限选项卡是 Admin Console 中每个产品配置文件的一部分。您可以将用户添加到特定的产品配置文件。然后将权限分配给特定的数据视图，并指定用户在产品配置文件中拥有的权限。

* 创建迁移计划，如以下部分所述， [创建迁移计划作为组织](#create-a-migration-plan-as-an-organization).

### 了解迁移中包含的内容

下表概述了迁移中包含的项目和组件元素：


|  | 项目 | Dimension和指标 |
|---------|----------|---------|
| **日期范围** | 是 | 不适用 |
| **区段** | 是 | 不适用 |
| **快速区段** | 是 | 不适用 |
| **面板** | 是 | 不适用 |
| **可视化图表** | 是 | 不适用 |
| **所有者** | （由执行迁移的用户定义） | ? |
| **策划** | 否 | 不适用 |
| **共享（项目角色）** | 否 | 否 |
| **批注** | 否 | 不适用 |
| **文件夹结构** | 否 | 不适用 |
| **描述** | 是 | ? |
| **标记** | ? | ? |
| **时间表** | ? | 不适用 |
| **归因（在维度上）** | 不适用 | ? |
| **异常检测** | ? | 不适用 |
| **贡献分析** | ? | 不适用 |
| **警报** | ? | 不适用 |

{style="table-layout:auto"}

### 创建迁移计划作为组织

由于为给定项目迁移映射的任何组件都适用于整个组织未来的任何项目迁移，因此您的组织提前计划所有项目迁移非常重要。

作为组织，您应该决定如何映射维度和量度。 这样做可避免单个管理员在仅考虑单个项目时在思洛存储器中进行决策。

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

您可以通过以下任一方式重试失败的迁移：

>[!NOTE]
>
>如果重试后迁移继续失败，请联系客户关怀团队并提供项目ID。 您可以在迁移状态页面中找到项目ID。 <!-- when does this page display? How can they get there -->

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
