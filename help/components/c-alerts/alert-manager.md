---
description: 了解如何管理警报。
title: 管理警报
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 24dd47e995523aedba1385ee8882af5e11c7b128
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 22%

---


# 管理警报


您可以从集中[!UICONTROL 警报]管理界面筛选、标记、删除、重命名、复制、启用、禁用、续订和导出警报。 要管理警报，请执行以下操作：

* 在主界面中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 警报]**。

警报管理器的结构类似于[区段管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md)和[计算量度管理器](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)。


## 警报管理器

警报管理器具有以下界面元素：

![过滤器界面](assets/alerts-manager.png)

### 警报列表

警报列表➊显示您拥有的所有警报、已覆盖到您所有项目的警报以及与您共享的警报。 该列表具有以下各列：

| 列 | 描述 |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 选择支持![Star](/help/assets/icons/Star.svg)或取消支持![StarOutline](/help/assets/icons/StarOutline.svg)警报。 |
| **[!UICONTROL 标题和描述]** | 要编辑警报，请选择标题链接，这将打开[警报生成器](alert-builder.md#alert-builder)。 |
| **[!UICONTROL Type]** | 警报的类型： Adobe Analytics数据警报或服务器调用使用情况警报。 |
| **[!UICONTROL 已启用]** | 警报已启用或已禁用。 |
| **[!UICONTROL 报告包]** | 此警报适用的报表包。 |
| **[!UICONTROL 所有者]** | 警报的所有者。 如果您不是管理员，则只能看到您拥有的警报或与您共享的警报。 |
| **[!UICONTROL 标记]** | 此警报的标记。 |
| **[!UICONTROL 到期日期]** | 警报设置为到期的日期和时间。 |
| **[!UICONTROL 修改日期]** | 上次修改警报的日期和时间。 |

<!-- 

When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul>

-->

使用 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) 指定您想要显示的列。

### 操作栏

您可以使用操作栏➋对警报执行操作。 操作栏包含以下操作：

| 图标 | 操作 | 描述 |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL 添加]** | 使用[警报生成器](alert-builder.md#alert-builder)添加另一个警报。 |
| ![Search](/help/assets/icons/Search.svg) | [!UICONTROL *按标题搜索*] | 在列表中未选择警报时，使用此搜索字段搜索警报。 |
| ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL 标记]** | 标记所选警报。 在&#x200B;**[!UICONTROL 标记警报]**&#x200B;对话框中，选择或取消选择所选警报的标记。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存选定警报的标记。 |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 删除]** | 删除所选警报。 系统将提示您确认。 |
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL 重命名]** | 重命名单个选定警报。 选中后，可以内联重命名警报。 |
| ![Copy](/help/assets/icons/Copy.svg) | **[!UICONTROL 复制]** | 复制所选警报。 创建的新警报具有相同的名称和后缀`(Copy)`。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 启用]**&#x200B;或&#x200B;**[!UICONTROL 禁用]** | 启用或禁用所选警报。 |
| ![刷新](/help/assets/icons/Refresh.svg) | **[!UICONTROL 续订]** | 续订警报过期日期。过期日期从选择此选项之日起延长1年，与原始过期日期无关。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 导出至 CSV]** | 将警报导出到`Alerts List.csv`文件。 |


### 活动过滤器栏

筛选器栏➌显示从筛选器面板应用到警报列表（如果有）的活动筛选器。 您可以使用 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 快速移除过滤器。如果指定了多个过滤器，则可以使用&#x200B;**[!UICONTROL 全部移除]**&#x200B;来移除所有过滤器。


### 过滤器面板

您可以使用![筛选器](/help/assets/icons/Filter.svg) **[!UICONTROL 筛选器]**&#x200B;左侧面板➍来筛选警报列表。 过滤器面板显示过滤器的类型和遵循特定过滤器的警报数。


1. 选择![Filter](/help/assets/icons/Filter.svg)以打开筛选面板。如果警报列表需要更多空间，您可以再次选择![筛选器](/help/assets/icons/Filter.svg)以关闭面板。
1. 从任何可用的过滤器部分中选择过滤器。


#### 标记过滤器部分

{{tagfiltersection}}


#### 报表包过滤器部分

{{reportsuitefiltersection}}


#### “所有者”过滤器部分

{{ownerfiltersection}}


#### 已启用状态过滤器部分

{{enabledstatusfiltersection}}


#### 类型过滤器部分

{{typefiltersection}}


#### 其他过滤器过滤器部分

{{otherfiltersfiltersection}}



## 编辑警报

您可以编辑警报

* 在[[!UICONTROL 警报]列表](#alerts-list)中，选择警报的标题。

您使用[警报生成器](alert-builder.md#alert-builder)编辑警报。

## 警报疑难解答

对警报问题进行故障诊断时，请向Adobe支持部门提供JID（作业实例ID）编号。 JID号位于您收到的警报电子邮件通知的底部。

![警报电子邮件](assets/alerts-email.PNG)


<!--

# Manage alerts

You can manage existing alerts in the Alerts manager. You can perform various management tasks on alerts, such as tagging, renaming, deleting, and more.

The Alerts manager is structured very much like the [Segment Manager](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html) and the [Calculated Metric Manager](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html).

 ![](assets/alert-manager.png)

## Create alerts

To create alerts from the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select [!UICONTROL **Add**] (or [!UICONTROL **Create new alert**] if you don't have any existing alerts).

1. Select the alert type that corresponds to the alert that you want to create:

   * [!UICONTROL **Analytics data alert**]: An alert to notify you when abnormal events occur in your data. 

     If you select this option, continue with [Create alerts](/help/components/c-alerts/alert-builder.md) for more details about creating alerts.

   * [!UICONTROL **Server call usage alert**]: An alert to notify you of the risk or occurrence of an overage in your server call consumption and commitment data. 

     If you select this option, continue with [Server call usage alerts](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >You must be an Analytics administrator or a user with the Server call usage permission in order to have access to server call usage. 

## Manage existing alerts

You can perform various actions on existing alerts, such as tagging, renaming, deleting, and so forth.

To manage existing alerts in the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select one or more alerts that you want to manage.

   ![](assets/alert-manager-tasks.png)

1. In the action bar, select any of the following options:

   | Action | Function | 
   |---------|----------|
   | [!UICONTROL **Tag**] | Apply a tag to an alert. This helps you to organize alerts for ease of use. | 
   | [!UICONTROL **Delete**] | Deletes the alert. | 
   | [!UICONTROL **Rename**] | Renames the alert. |
   | [!UICONTROL **Approve**] | Mark the alert as Approved. |
   | [!UICONTROL **Copy**] | Creates a copy (duplicate) of the alert. |
   | [!UICONTROL **Disable**] | Disables an alert that is currently enabled. |
   | [!UICONTROL **Enable**] | Enables an alert that is currently disabled. |
   | [!UICONTROL **Renew**] | Renews the alert expiration date. This extends the  expiration date to be 1 year from the day you selected this option, regardless of the original expiration date. |
   | [!UICONTROL **Export to CSV**] | Exports the alert to a .CSV file. |

## Edit an alert

To edit an existing alert:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select the alert name in the [!UICONTROL **Title and description**] column.

1. Edit the alert as desired. 

   Following are some of the things you can do when editing an alert:

   * Add alerts to other report suites
   * Add or modify the description
   * Modify the time granularity
   * Modify the recipients 
   * Modify the expiration date
   * Modify the metrics and filters

1. Select [!UICONTROL **Save**].

## Configure columns 

You can configure the information displayed for each alert in the Alerts manager by configuring the columns that are displayed.

To configure the visible columns in the Alerts manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Alerts]**. 

1. In the Alert manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Alerts manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Title and description | These values are provided in the Alert builder. To edit the title and description, select the title link to open the Alert builder.  |
   | Favorites  | Displays star icons next to each alert, allowing you to mark alerts as favorites. |
   | Type | Shows whether the alert is an Analytics data alert or a Server call usage alert. |
   | Enabled | Shows whether the alert is currently enabled or disabled. | 
   | Report suite | Indicates in which report suite the alert was last saved.  |
   | Owner | Indicates who owns the alert. As a non-admin, you can see only alerts you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the alert, either by you or by people who shared the alert with you.  |
   | Expiration date | Shows the date and time when the alert is set to expire. |
   | Date modified | Indicates the date when the alert was last modified.  |

   {style="table-layout:auto"}
   
   
    When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> 
   
-->

