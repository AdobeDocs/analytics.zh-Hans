---
description: 配置云导入帐户和可以上传分类数据的位置
keywords: Analysis Workspace
title: 位置管理器
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: 273fea86cde8880d9c9e03ac9c6a99b75f70f6cd
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 1%

---

# 位置管理器

“位置”管理器允许您查看、创建、编辑或删除帐户和位置。 它们可用于以下任意目的：

* 导出文件，使用 [数据馈送](/help/export/analytics-data-feed/create-feed.md)
* 导出报告，使用 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* 使用以下方式导入架构 [分类集](/help/components/classifications/sets/overview.md)

## 查看、筛选和搜索位置

位置管理器允许您查看您创建的任何位置。 系统管理员可以查看由所有用户创建的位置。

1. 要访问Adobe Analytics中的位置管理器，请选择 **[!UICONTROL 组件]** > **[!UICONTROL 位置]**.

1. （视情况而定）如果您是系统管理员，则可以启用 [!UICONTROL **查看所有用户的位置**] 选项，用于查看由您组织中的所有用户创建的位置。 <!-- Maybe add a screenshot? This is new functionality -->

1. 筛选或搜索位置列表：

   * **筛选器：** 选择过滤器图标以过滤位置列表。

     您可以通过以下方式筛选位置 **[!UICONTROL 位置类型]**， **[!UICONTROL 帐户]**，或 **[!UICONTROL 创建者]**.

     ![位置过滤器](assets/locations-filters.png)

   * **搜索：** 在搜索字段中，开始键入要查看位置的名称。 结果会按键入内容进行筛选。 将搜索以下列： **位置名称**， **位置类型**， **帐户**、和 **创建者**.

1. （可选）如果您有超过1,000个位置，则仅显示前1,000个位置。 选择 [!UICONTROL **加载更多**] 以加载1000多个位置。

## 在位置管理器中配置列

“位置”管理器中有以下列。 要定制表中显示的列，请选择 **自定义表** 图标 ![“自定义表”图标](assets/customize-table-icon.png).

* **[!UICONTROL 位置名称]**：位置名称。 选择位置名称旁边的3点菜单，可以 [编辑位置](/help/components/locations/configure-import-locations.md) 或者删除它。
* **[!UICONTROL 位置类型]**：与位置关联的帐户类型。
* **[!UICONTROL 帐户]**：与位置关联的特定帐户。
* **应用程序**：位置可以结合使用的应用程序类型(例如数据馈送、Data Warehouse或分类集)。
* **[!UICONTROL 上次使用时间]**：上次使用位置的日期。
* **[!UICONTROL 创建者]**：创建位置的用户。
* **[!UICONTROL 创建日期]**：创建位置的日期。

## 创建和管理位置

您可以创建、编辑和删除位置。

### 创建位置

有关如何创建位置的信息，请参阅 [配置云导入和导出位置](/help/components/locations/configure-import-locations.md).

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### 编辑位置

有关如何编辑位置的信息，请参阅 [配置云导入和导出位置](/help/components/locations/configure-import-locations.md).

### 删除位置

>[!IMPORTANT]
>
>如果删除了某个位置，则与该位置关联的任何数据馈送文件、Data Warehouse报表或分类集架构在下次使用它们时将失败。
>
>如果删除位置，则应 [编辑您的数据馈送](/help/export/analytics-data-feed/create-feed.md)， [Data Warehouse报表](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)、和 [分类集架构](/help/components/classifications/sets/manage/schema.md) 使用正常工作位置。

要在Adobe Analytics的位置管理器中删除位置，请执行以下操作：

1. 选择 **[!UICONTROL 组件]** > **[!UICONTROL 位置]**，然后选择 [!UICONTROL **位置**] 选项卡。

1. 选择以下内容中的3点菜单 [!UICONTROL **位置名称**] 要删除的位置对应的列。

1. 选择&#x200B;[!UICONTROL **删除**]。

## 编辑帐户

1. 要在Adobe Analytics的位置管理器中编辑帐户，请选择 **[!UICONTROL 组件]** > **[!UICONTROL 位置]**，然后选择 [!UICONTROL **位置帐户**] 选项卡。

1. （视情况而定）如果您是系统管理员，则可以启用 [!UICONTROL **查看所有用户的帐户**] 选项，用于查看由您组织中的所有用户创建的位置。 <!-- Maybe add a screenshot? This is new functionality -->


1. 选择 [!UICONTROL **查看详细信息**] 在要编辑的帐户上。

1. 进行任何所需的更改，然后选择 [!UICONTROL **保存**].

## 查看帐户密钥

创建帐户后，您可以查看该帐户的任何关联帐户密钥。 如果在配置帐户时没有完成与云提供商的配置，您可能需要查看此信息 [最初配置帐户](/help/components/locations/configure-import-accounts.md).

要查看与导出帐户关联的密钥，请执行以下操作：

1. 在Adobe Analytics中，选择 **[!UICONTROL 组件]** > **[!UICONTROL 位置]**，然后选择 [!UICONTROL **位置帐户**] 选项卡。

1. 在要编辑的帐户上选择3点图标，然后选择 [!UICONTROL **帐户密钥**].

## 删除帐户

1. 在Adobe Analytics中，选择 **[!UICONTROL 组件]** > **[!UICONTROL 位置]**，然后选择 [!UICONTROL **位置帐户**] 选项卡。

1. 在要编辑的帐户上选择3点图标，然后选择 [!UICONTROL **删除帐户**]
