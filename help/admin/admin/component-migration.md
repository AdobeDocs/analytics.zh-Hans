---
description: 介绍如何将组件和项目从Adobe Analytics迁移到Customer Journey Analytics。
title: 将组件和项目从Adobe Analytics迁移到Customer Journey Analytics
feature: Admin Tools
source-git-commit: 8a9c3b4d6c7a59582a6fd8bdc5464c2dbed3ad1b
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 6%

---

# 将组件和项目从Adobe Analytics迁移到Customer Journey Analytics

Adobe Analytics管理员可以将Adobe Analytics组件和项目迁移到Customer Journey Analytics。

迁移过程包括：

* 在Customer Journey Analytics中重新创建Adobe Analytics项目。

* 将Adobe Analytics报表包中的维度和指标与Customer Journey Analytics数据视图中的维度和指标进行匹配。

  某些维度和量度会自动匹配；其他维度和量度必须在迁移过程中手动匹配。

## 先决条件

在准备好迁移项目及其关联的维度和量度之前，您首先需要：

* 使用Analytics Source Connector在Customer Journey Analytics中查看Adobe Analytics报告包数据。 为此，您需要：

   * [设置报表包以引入Adobe Experience Platform和Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [摄取和使用数据](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=zh-Hans)

* 确保Customer Journey Analytics中的用户已预配到数据匹配的数据视图。

  有关更多信息，请参阅 [Admin Console中的Customer Journey Analytics权限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) 在 [Customer Journey Analytics访问控制](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  权限选项卡是 Admin Console 中每个产品配置文件的一部分。您可以将用户添加到特定的产品配置文件。然后将权限分配给特定的数据视图，并指定用户在产品配置文件中拥有的权限。

## 创建迁移计划作为组织

由于与给定项目迁移匹配的任何组件都适用于整个组织未来的任何项目迁移，因此您的组织提前计划所有项目迁移非常重要。

作为组织，您应该决定哪些维度和量度将与哪些维度和量度匹配，以避免单个管理员在项目迁移时在思洛存储器中做出决策。

## 将Adobe Analytics项目迁移到Customer Journey Analytics

>[!IMPORTANT]
>
>在将任何项目迁移到Customer Journey Analytics（如本节所述）之前，请通过了解 [规划迁移](#plan-the-migration) 部分。
>
>您匹配的任何维度或量度对于此项目以及在整个组织中迁移的所有未来项目都是永久性的。 如果继续，则无法修改您所做的匹配。



1. 在Adobe Analytics中，选择 [!UICONTROL **管理员**] 选项卡，然后选择 [!UICONTROL **所有管理员**].

1. 下 [!UICONTROL **数据配置和收集**]，选择 [!UICONTROL **组件迁移**].

1. （视情况而定）要快速找到要迁移的项目，您可以：

   * 通过选择过滤器图标来过滤项目列表。

     您可以按以下条件进行筛选：

      * 状态

      * 标记

      * 报表包

      * 所有者

      * 其他筛选条件

   * 使用搜索字段搜索要迁移的项目。

1. 将鼠标悬停在要迁移的项目上，然后选择 **迁移** 图标 ![迁移项目](assets/migrate.svg).

   或

   选择要迁移的项目，然后选择 [!UICONTROL **迁移到Customer Journey Analytics**].

   一次只能选择一个要迁移的项目。

   此 [!UICONTROL **将project_name迁移到Customer Journey Analytics**] 对话框随即显示。

   <!-- add screenshot -->

1. 在 [!UICONTROL **项目所有者**] 字段中，开始键入要在Customer Journey Analytics中设置为项目所有者的用户的名称，然后在下拉菜单中选择其名称。

   您指定的所有者拥有对该项目的所有管理权限.

1. 在 [!UICONTROL **匹配报表包的架构**] 部分，选择一个报表包。

1. 在 [!UICONTROL **数据视图**] 下拉菜单中，选择要将项目和组件迁移到的Customer Journey Analytics数据视图。

1. 选择 [!UICONTROL **匹配架构**].

1. 在 [!UICONTROL **匹配架构**] 部分，展开 [!UICONTROL **Dimension**] 和 [!UICONTROL **量度**] 部分。

   Adobe Analytics中的某些维度和量度会自动与Customer Journey Analytics中的某个维度或量度匹配。 其他需要手动匹配。

   **自动匹配的维度和量度**

   Adobe Analytics中的某些维度和量度会自动与Customer Journey Analytics中的某个维度或量度匹配。 您无法为这些维度和量度做出任何匹配决策。

   例如， **访问** Adobe Analytics中的量度会自动与 **会话** Customer Journey Analytics中的指标。

   您可以选择任意维度或量度以查看其关联的ID。

   <!-- update screenshot after I can see the Status column -->

   ![项目迁移模式](assets/project-migration-schema.png)

   **手动匹配维度和量度**

   Adobe Analytics中的其他维度和量度无法自动与Customer Journey Analytics中的维度或量度匹配。

   当维度或量度无法自动匹配时，橙色计数器显示在 [!UICONTROL **Dimension**] 或 [!UICONTROL **量度**] 区域标题，指示需要手动匹配的维度或量度数量。 在表中，有一个警告图标 ![警告图标](assets/schema-warning.png) 显示在需要手动匹配的每个维度或量度旁边。

   <!-- update screenshot after I can see the Status column -->

   ![迁移架构手动匹配](assets/schema-manual-map.png)

1. 要手动匹配维度和指标，请选择包含警告图标的维度或指标 ![警告图标](assets/schema-warning.png)，然后在 [!UICONTROL **匹配Customer Journey Analytics指标**] 字段(或 [!UICONTROL **匹配Customer Journey Analytics维度**] 字段（如果要匹配维度），请在Customer Journey Analytics中选择要与所选维度或量度匹配的维度或量度。

   ![匹配维度和量度](assets/schema-manual-map-drop-down.png)

   对包含警告图标的每个维度或量度重复此过程。

   在Adobe Analytics报表包中的所有维度和指标与Customer Journey Analytics数据视图中的某个维度或指标匹配后，将显示一个绿色复选标记 ![复选标记](assets/report-suite-check.png) 显示在中的报表包名称旁边 [!UICONTROL **匹配报表包的架构**] 部分。

1. （视情况而定）如果要迁移的项目包含多个报表包，请在 [!UICONTROL **匹配报表包的架构**] 部分，然后重复步骤6到步骤10。 <!-- double-check that the step numbers are still correct -->

1. 选择 [!UICONTROL **迁移**].

   >[!WARNING]
   >
   >   选择后，屏幕上会显示警告消息 [!UICONTROL **迁移**]. 在选择继续之前，请了解您匹配的任何维度或量度对于此项目以及在整个组织中迁移的所有未来项目都是永久性的。 如果继续，则无法修改您所做的匹配。
