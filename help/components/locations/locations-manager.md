---
description: 配置云导入帐户和可以上传分类数据的位置
keywords: Analysis Workspace
title: 位置管理器
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: 5c02b46a7757e07a23505dc8e3dc21b6353aa9e2
workflow-type: tm+mt
source-wordcount: '1490'
ht-degree: 1%

---

# 位置管理器

“位置”管理器允许您查看、创建、编辑或删除帐户和位置。 它们可用于以下任意目的：

* 使用[数据馈送](/help/export/analytics-data-feed/create-feed.md)导出文件
* 使用[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)导出报告
* 使用[Report Builder](/help/analyze/report-builder/report-builder-export.md)时导出文件
* 使用[分类集](/help/components/classifications/sets/overview.md)导入架构

## 查看、筛选和搜索位置

位置管理器允许您查看已创建的任何位置或与组织共享的任何位置。 系统管理员可以查看所有用户创建的位置，而不管这些用户是否共享。

1. 要访问Adobe Analytics中的位置管理器，请选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 位置]**。

1. （视情况而定）如果您是系统管理员，则可以启用&#x200B;[!UICONTROL **查看所有用户的位置**]&#x200B;选项以查看由您组织中的所有用户创建的位置。<!-- Maybe add a screenshot? This is new functionality -->

1. 筛选或搜索位置列表：

   * **筛选器：**&#x200B;选择“筛选器”图标以筛选位置列表。

     您可以按&#x200B;**[!UICONTROL 位置类型]**、**[!UICONTROL 帐户]**&#x200B;或&#x200B;**创建的**&#x200B;筛选位置。

     ![位置筛选器](assets/locations-filters.png)

   * **搜索：**&#x200B;在搜索字段中，开始键入要查看位置的名称。 结果会按键入内容进行筛选。 搜索了以下列：**位置名称**、**位置类型**、**帐户**&#x200B;和&#x200B;**创建者**。

1. （可选）如果您有超过1,000个位置，则仅显示前1,000个位置。 选择&#x200B;[!UICONTROL **加载更多**]&#x200B;以加载1,000多个位置。

## 在位置管理器中配置列

“位置”管理器中有以下列。 要自定义表中显示的列，请选择&#x200B;**自定义表**&#x200B;图标![自定义表图标](assets/customize-table-icon.png)。

* **[!UICONTROL 位置名称]**：位置名称。 选择位置名称旁边的3点菜单以[编辑位置](/help/components/locations/configure-import-locations.md)或删除它。
* **[!UICONTROL 位置类型]**：与位置关联的帐户类型。
* **[!UICONTROL 帐户]**：与位置关联的特定帐户。
* **应用程序**：位置可以与其一起使用的应用程序类型(如数据馈送、Data Warehouse或分类集)。
* **[!UICONTROL 上次使用]**：上次使用该位置的日期。
* **[!UICONTROL 创建者]**：创建位置的用户。
* **[!UICONTROL 创建日期]**：创建位置的日期。

## 创建和管理位置

您可以创建、编辑和删除位置。

### 创建位置

有关如何创建位置的信息，请参阅[配置云导入和导出位置](/help/components/locations/configure-import-locations.md)。

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### 编辑位置

位置只能由创建该位置的用户或系统管理员编辑。

有关如何编辑位置的信息，请参阅[配置云导入和导出位置](/help/components/locations/configure-import-locations.md)。

### 删除位置

>[!IMPORTANT]
>
>如果删除位置，则与已删除位置关联的任何数据馈送文件、Data Warehouse报表或分类集架构在下次使用时都将失败。
>
>如果删除位置，您应[编辑数据馈送](/help/export/analytics-data-feed/create-feed.md)、[Data Warehouse报告](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)和[分类集架构](/help/components/classifications/sets/manage/schema.md)以使用正常的位置。

位置只能由创建该位置的用户或系统管理员删除。

要在Adobe Analytics的位置管理器中删除位置，请执行以下操作：

1. 选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 位置]**，然后选择&#x200B;[!UICONTROL **位置**]&#x200B;选项卡。

1. 为要删除的位置选择&#x200B;[!UICONTROL **位置名称**]&#x200B;列中的3点菜单。

1. 选择&#x200B;[!UICONTROL **删除**]。

## 创建和管理帐户

您可以创建、编辑和删除帐户。

### 创建帐户

有关如何创建帐户的信息，请参阅[配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md)。

### 编辑帐户

帐户只能由创建该帐户的用户或系统管理员编辑。

有关如何编辑帐户的信息，请参阅[配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md)。

### 查看帐户密钥

创建帐户后，您可以查看该帐户的任何关联帐户密钥。 如果您[最初配置帐户](/help/components/locations/configure-import-accounts.md)时没有完成与云提供商的帐户配置，您可能需要查看此信息。

要查看与导出帐户关联的密钥，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 位置]**，然后选择&#x200B;[!UICONTROL **位置帐户**]&#x200B;选项卡。

1. （视情况而定）如果您是系统管理员，则可以启用&#x200B;[!UICONTROL **查看所有用户的位置**]&#x200B;选项以查看由您组织中的所有用户创建的位置。<!-- Maybe add a screenshot? This is new functionality -->

1. 选择要编辑的帐户上的3点图标，然后选择&#x200B;[!UICONTROL **帐户密钥**]。

### 删除帐户

>[!IMPORTANT]
>
>仅当没有位置使用帐户时，才能删除帐户。 在删除帐户之前，必须先删除帐户上的任何位置，如[删除位置](#delete-a-location)中所述。

只能由创建帐户的用户或系统管理员删除帐户。

要删除帐户，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 位置]**，然后选择&#x200B;[!UICONTROL **位置帐户**]&#x200B;选项卡。

1. （视情况而定）如果您是系统管理员，则可以启用&#x200B;[!UICONTROL **查看所有用户的帐户**]&#x200B;选项以查看由您组织中的所有用户创建的位置。

1. 选择要编辑的帐户上的3点图标，然后选择&#x200B;[!UICONTROL **删除帐户**]

## 配置公司范围的设置（仅限管理员）

系统管理员可以限制用户创建帐户和位置，也可以限制用户可以创建和使用的帐户类型。

![管理员设置选项卡](assets/locations-admin-settings.png)

### 配置用户是否可以创建和编辑帐户

默认情况下，组织中的所有用户都可以创建帐户并编辑他们在Adobe Analytics环境中创建的帐户，如[配置Cloud Import和Export帐户](/help/components/locations/configure-import-accounts.md)中所述。

您可以限制用户创建帐户。 执行此操作时，用户仍可以使用他们已创建的任何帐户，但无法再编辑这些帐户。 您可以删除用户已创建的帐户，如[删除帐户](#delete-an-account)中所述。

要限制所有用户创建和编辑帐户，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 位置]**，然后选择&#x200B;[!UICONTROL **管理员设置**]&#x200B;选项卡。

1. 在&#x200B;[!UICONTROL **位置帐户**]&#x200B;部分中，取消选择选项&#x200B;[!UICONTROL **允许用户创建和管理位置帐户**]。

1. 选择&#x200B;[!UICONTROL **保存**]。

1. （可选）按照[删除帐户](#delete-an-account)中的说明，删除用户已创建但不再希望他们使用的任何帐户。

### 配置用户是否可以创建和编辑位置

默认情况下，组织中的所有用户都可以在Adobe Analytics环境中创建位置并编辑他们创建的位置，如[配置云导入和导出位置](/help/components/locations/configure-import-locations.md)中所述。

您可以限制用户创建位置。 执行此操作时，用户仍可以使用他们已创建的任何位置，但无法再编辑这些位置。 您可以删除用户已创建的位置，如[删除位置](#delete-a-location)中所述。

要限制所有用户创建和编辑位置，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 位置]**，然后选择&#x200B;[!UICONTROL **管理员设置**]&#x200B;选项卡。

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;部分中，取消选择选项&#x200B;[!UICONTROL **允许用户创建和管理位置**]。

1. 选择&#x200B;[!UICONTROL **保存**]。

1. （可选）按照[删除位置](#delete-a-location)中的说明，删除用户已创建但不再希望他们使用的任何位置。

### 限制用户可以创建和使用的帐户类型

在以下情况下，您可以限制用户看到的帐户类型：

* 在[创建新帐户](/help/components/locations/configure-import-accounts.md)时。

* 在使用[数据馈送](/help/export/analytics-data-feed/create-feed.md)导出文件时、使用[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)导出报告或使用[分类集](/help/components/classifications/sets/overview.md)导入架构时，选择要使用哪些帐户。

当按本节所述限制帐户类型时，用户将无法再看到您限制的任何类型的帐户。 这意味着无法创建该类型的新帐户，并且在创建数据馈送、Data Warehouse或分类集时，也无法使用该类型的现有帐户。

但是，如果要限制使用为计划导出配置的现有帐户，则必须删除这些帐户。

#### 确保未将帐户用于计划导出

限制帐户类型时，会隐藏现有帐户，而不会删除现有帐户。

如果计划已配置为将数据发送到您限制类型的帐户，则即使在您限制帐户类型后，计划仍将继续运行，并且数据将继续发送到该帐户。  例如，如果计划将数据馈送发送到您限制的帐户类型，则计划将继续运行。

如果您需要确保特定类型的帐户未在计划导出中使用，则可以在[限制帐户类型](#limit-the-account-types-that-are-available-to-users)之前删除这些帐户。

要删除帐户，请执行以下操作：

1. 找到计划限制的帐户类型的帐户，这些帐户正用于计划导出。

1. 按照[删除帐户](#delete-an-account)中的说明删除帐户。

1. 继续下面的部分，[限制用户可用的帐户类型](#limit-the-account-types-that-are-available-to-users)。

#### 限制用户可用的帐户类型

要限制用户在创建和使用帐户时可用的帐户类型，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 位置]**，然后选择&#x200B;[!UICONTROL **管理员设置**]&#x200B;选项卡。

1. 找到&#x200B;[!UICONTROL **允许的帐户类型**]&#x200B;部分。

   默认情况下，用户可以使用以下帐户类型。 取消选择要限制用户使用的任意帐户类型。

   必须至少选择一个帐户类型。

   * [!UICONTROL **Amazon S3 Role ARN**]

   * [!UICONTROL **Google Cloud Platform**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **电子邮件**]

   * 旧帐户类型，包括&#x200B;[!UICONTROL **Amazon S3**]、[!UICONTROL **Azure**]、[!UICONTROL **FTP**]&#x200B;和&#x200B;[!UICONTROL **SFTP**]

1. 选择&#x200B;[!UICONTROL **保存**]。


