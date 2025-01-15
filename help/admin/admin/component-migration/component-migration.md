---
description: 介绍如何将组件和项目从Adobe Analytics迁移到Customer Journey Analytics。
title: 将组件和项目从Adobe Analytics迁移到Customer Journey Analytics
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: 96c202870a4e584cf3625d6e4d40024b787c2f0e
workflow-type: tm+mt
source-wordcount: '1501'
ht-degree: 5%

---

# 将组件和项目从Adobe Analytics迁移到Customer Journey Analytics

Adobe Analytics 管理员可将 Adobe Analytics 项目及其关联的组件迁移到 Customer Journey Analytics。

迁移过程包括：

* 在 Customer Journey Analytics 中重新创建 Adobe Analytics 项目。

* 将来自 Adobe Analytics 报告包的维度和指标映射到 Customer Journey Analytics 数据视图中的维度和指标。

  某些维度和量度会自动映射；其他维度和量度必须在迁移过程中手动映射。 区段也会迁移，但无需在迁移过程中映射这些区段。

  迁移完成后，所有已迁移的组件都会显示在迁移摘要中。

>[!NOTE]
>
>本页上的信息介绍了如何使用用户界面迁移项目及其关联的组件。
>
>或者，您可以使用API执行迁移。 有关详细信息，请参阅[Adobe Analytics API](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Analytics%202.0%20APIs)。 在&#x200B;**[!UICONTROL 选择定义]**&#x200B;下拉菜单中可以使用所有API定义。


## 准备迁移

在将任何项目迁移到Customer Journey Analytics之前，请在[准备将组件和项目从Adobe Analytics迁移到Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md)中了解有关迁移项目的更多信息。

## 将Adobe Analytics项目迁移到Customer Journey Analytics

>[!IMPORTANT]
>
>在按本节所述将任何项目迁移到Customer Journey Analytics之前，请在[准备将组件和项目从Adobe Analytics迁移到Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md)中了解有关迁移项目的更多信息。
>
>**您映射的任何维度或量度对于此项目以及在整个IMS组织中迁移的所有未来项目都是永久性的，无论哪个用户正在执行迁移。 无法修改或撤消这些映射，除非联系客户关怀团队。**

1. 在 Adobe Analytics 中，选择&#x200B;[!UICONTROL **管理员**]&#x200B;选项卡，然后选择&#x200B;[!UICONTROL **所有管理员**]。

1. 在&#x200B;[!UICONTROL **数据配置和集合**]&#x200B;下，选择&#x200B;[!UICONTROL **组件迁移**]。

1. 找到要迁移的项目。 您可以过滤、排序或搜索项目列表。

   默认情况下，仅显示与您共享的项目。 要查看您组织中的所有项目，请选择&#x200B;**筛选器**&#x200B;图标，然后展开&#x200B;[!UICONTROL **其他筛选器**]&#x200B;并选择&#x200B;[!UICONTROL **显示所有**]。 （有关筛选、排序和搜索项目列表的详细信息，请参阅[筛选、排序和搜索项目列表](#filter-sort-and-search-the-list-of-projects)。）

1. 将鼠标悬停在要迁移的项目上，然后选择&#x200B;**迁移**&#x200B;图标![迁移项目](assets/migrate.svg)。

   或

   选择要迁移的项目，然后选择&#x200B;[!UICONTROL **迁移到Customer Journey Analytics**]。

   一次只能选择一个要迁移的项目。

   将显示&#x200B;[!UICONTROL **将project_name迁移到Customer Journey Analytics**]&#x200B;对话框。

   <!-- add screenshot -->

1. 在&#x200B;[!UICONTROL **项目所有者**]&#x200B;字段中，开始在Customer Journey Analytics中输入要设置为项目所有者的用户的名称，然后在下拉菜单中选择其名称。

   您指定的所有者具有项目的完全管理权限。 所有者必须是Customer Journey Analytics管理员。 您可以在后续步骤中更改项目的所有权。

1. 在&#x200B;[!UICONTROL **映射报表包**]&#x200B;部分中，选择一个报表包。

1. 在&#x200B;[!UICONTROL **数据视图**]&#x200B;下拉菜单中，选择要将项目和组件迁移到的Customer Journey Analytics数据视图。

1. 选择&#x200B;[!UICONTROL **映射架构**]。

1. 在&#x200B;[!UICONTROL **映射架构**]&#x200B;部分中，展开&#x200B;[!UICONTROL **Dimension**]&#x200B;和&#x200B;[!UICONTROL **指标**]&#x200B;部分。

   Adobe Analytics中的某些维度和量度会自动映射到Customer Journey Analytics中的维度或量度。 其他则需要手动映射。

   **自动映射维度和量度**

   >[!NOTE]
   >
   >   如果您使用WebSDK将数据摄取到Adobe Experience Platform，则维度和量度无法自动映射。 有关详细信息，请参阅[准备将组件和项目从Adobe Analytics迁移到Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md)中的[先决条件](/help/admin/admin/component-migration/prepare-component-migration.md#prerequisites)。

   Adobe Analytics中的某些维度和量度会自动映射到Customer Journey Analytics中的维度或量度。 您无法为这些维度和量度做出任何映射决策。

   例如，Adobe Analytics中的&#x200B;**访问次数**&#x200B;指标自动映射为Customer Journey Analytics中的&#x200B;**会话**&#x200B;指标。

   您可以选择任意维度或量度以查看其关联的ID。

   <!-- update screenshot after I can see the Status column -->

   ![项目迁移架构](assets/project-migration-schema.png)

   **手动映射维度和量度**

   Adobe Analytics中的某些维度和量度无法自动映射到Customer Journey Analytics中的维度或量度。

   当维度或量度无法自动映射时，[!UICONTROL **Dimension**]&#x200B;或&#x200B;[!UICONTROL **量度**]&#x200B;分区标题旁边会显示一个橙色计数器，指示需要手动映射的维度或量度数量。 在表中，每个需要手动映射的维度或量度旁边会显示一个警告图标![警告图标](assets/schema-warning.png)。

   此外，[!UICONTROL **状态**]&#x200B;列显示&#x200B;[!UICONTROL **未映射**]。

   <!-- update screenshot after I can see the Status column -->

   ![迁移架构手动映射](assets/schema-manual-map.png)

1. 要手动映射维度和量度，请选择包含警告图标![警告图标](assets/schema-warning.png)的维度或量度，然后在&#x200B;[!UICONTROL **映射的Customer Journey Analytics量度**]&#x200B;字段(如果要映射维度，则在&#x200B;[!UICONTROL **映射的Customer Journey Analytics维度**]&#x200B;字段中)中选择要映射到所选维度或量度的Customer Journey Analytics维度或量度。

   ![映射维度和量度](assets/schema-manual-map-drop-down.png)

   映射维度或量度后，警告图标消失，[!UICONTROL **状态**]&#x200B;列更改为&#x200B;[!UICONTROL **已映射**]（带有绿色圆点）。 （带有灰色圆点的&#x200B;[!UICONTROL **Mapped**]&#x200B;状态表示在上次迁移期间映射了维度或量度；无法更新任何以前的映射。）

   对包含警告图标的每个维度或量度重复此过程。

   将Adobe Analytics报表包中的所有维度和量度映射到Customer Journey Analytics报表包中的维度或量度后，[!UICONTROL **映射报表包架构**]&#x200B;部分中的报表包名称旁边会显示一个绿色复选标记![复选标记](assets/report-suite-check.png)。

1. （视情况而定）如果要迁移的项目包含多个报表包，请在&#x200B;[!UICONTROL **映射报表包架构**]&#x200B;部分中选择其他报表包，然后重复步骤6到步骤10。<!-- double-check that the step numbers are still correct -->

1. 选择&#x200B;[!UICONTROL **迁移**]。

   >[!WARNING]
   >
   >   选择&#x200B;[!UICONTROL **迁移**]&#x200B;后，将显示屏幕上的警告消息。 在选择继续之前，请了解您映射的任何维度或量度对于此项目以及迁移整个组织的所有未来项目都是永久性的。 如果继续，将无法修改您所做的映射。

   迁移完成后，[!UICONTROL **迁移状态**]&#x200B;页面将提供迁移内容的摘要。

   如果迁移失败，请参阅下面的[重试失败的迁移](#retry-a-failed-migration)部分以了解更多信息。

1. （可选）迁移项目后，您可以将该项目的所有权转移给Customer Journey Analytics中的任何用户。 有关详细信息，请参阅《Customer Journey Analytics指南》中的[转移资源](https://experienceleague.adobe.com/en/docs/analytics-platform/using/tools/asset-transfer/transfer-assets)。

## 重试失败的迁移

如果迁移失败，您可以重试迁移。

在重试失败的迁移之前，请确保从项目中删除所有[不受支持的元素](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html#understand-unsupported-elements-that-cause-errors)。

>[!NOTE]
>
>如果重试后迁移继续失败，请联系客户关怀团队并提供项目ID。 您可以在迁移状态页面中找到项目ID。<!-- when does this page display? How can they get there -->

要重试失败的迁移，请执行以下操作：

1. 在 Adobe Analytics 中，选择&#x200B;[!UICONTROL **管理员**]&#x200B;选项卡，然后选择&#x200B;[!UICONTROL **所有管理员**]。

1. 在&#x200B;[!UICONTROL **数据配置和集合**]&#x200B;下，选择&#x200B;[!UICONTROL **组件迁移**]。

1. 在要重试的项目旁的&#x200B;[!UICONTROL **迁移状态**]&#x200B;列中选择&#x200B;[!UICONTROL **失败**]。

   ![迁移状态列失败](assets/migration-failed.png)

   此时将显示&#x200B;[!UICONTROL **迁移状态**]&#x200B;页面。

   完成以上[将Adobe Analytics项目迁移到Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics)部分中描述的迁移步骤后，此页面也会立即显示。

1. 选择&#x200B;[!UICONTROL **重试迁移**]。

## 筛选、排序和搜索项目列表

您可以在组件迁移页面上过滤、排序和搜索项目列表。

### 筛选项目列表

您可以按以下条件进行筛选：

| 过滤器 | 描述 |
|---------|----------|
| [!UICONTROL **状态**] | 迁移的状态： <ul><li>[!UICONTROL **未启动**]</li><li>[!UICONTROL **已启动**]</li><li>[!UICONTROL **已完成**]</li><li>[!UICONTROL **失败**]</li></ul>。 |
| [!UICONTROL **标记**] | 选择标记列表中的任意标记。 仅显示应用了选定标记的项目。 |
| [!UICONTROL **报告包**] | 在报表包列表中选择任意报表包。 仅显示使用选定报表包的项目。 |
| [!UICONTROL **所有者**] | 选择所有者列表中的任意所有者。 仅显示您选择的用户拥有的项目。 |
| [!UICONTROL **其他筛选条件**] | 还提供以下附加过滤器： <ul><li>[!UICONTROL **我的**]：仅显示您设置为所有者的项目。</li><li>[!UICONTROL **与我共享**]：仅显示与您共享的项目。</li><li>[!UICONTROL **收藏夹**]：仅显示标记为收藏的项目。 （您可以从[项目登陆页面](/help/analyze/landing.md)中将项目标记为收藏。）</li><li>[!UICONTROL **每月**]</li><li>[!UICONTROL **每年**]</li></ul> |

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
