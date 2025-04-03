---
description: 使用Analytics库存
title: Analytics 库存
feature: Admin Tools
role: Admin
hide: true
hidefromtoc: true
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: fceb28b7af480e6d87abf09c26f45a7afb2d3270
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 37%

---

# 分析库存 {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="分析库存"
>abstract="此页面提供 Adobe Analytics 环境的全面概述，包括项目和组件的数量、报告包、用户等。在您开始准备升级到 Customer Journey Analytics 时，此信息尤为宝贵。"

<!-- markdownlint-enable MD034 -->

Analytics清单提供了Adobe Analytics环境的全面概述，包括项目和组件数量、报表包数量、用户数量等。 在您开始准备升级到 Customer Journey Analytics 时，此信息尤为宝贵。

此应用程序旨在帮助您回答以下问题：

* 对于您的组织，哪些资产（例如报表包、区段、用户、工作区项目、数据馈送等）需要升级，哪些资产可以留下？

* 确定需要迁移的资源后：

   * 是否应该在此升级之前进行一些资产清理？

   * 您是否应该在此过程中进行一些资产合并？

   * 您的资产应采用什么升级顺序？

   * 您应该首先升级哪组报表包？ 最后一个？

## 权限

在[Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/admin-roles-in-analytics)中具有Adobe Analytics产品管理员权限的用户可以使用Analytics清单。

## 访问Analytics库存

1. 在&#x200B;**[!UICONTROL 管理员]**&#x200B;菜单中单击&#x200B;**[!UICONTROL Analytics清单]**。 或转到&#x200B;**[!UICONTROL 所有管理员]** > **[!UICONTROL Analytics清单]**。

![Analytics-Inventory-menu](assets/an-inventory-menu.png)

1. 主屏幕显示您的Adobe Analytics环境的完整清单：

   ![主清单屏幕](assets/an_inventory.png)

>[!IMPORTANT]
>
>   在此初始版本中，您可以查看Workspace项目、区段、计算量度、高级(Media Analytics)数据和用户的概要数字。 目前，唯一可操作的项目是报表包。


## 组件 {#components}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-components"
>title="组件"
>abstract="此部分显示 Adobe Analytics 环境中存在的项目、区段和计算量度的数量。项目和组件可以迁移到 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

在此初始版本中，您可以查看Workspace项目、区段和计算量度的汇总库存数量。 后续版本将允许您分析这些组件。

## 数据配置和收集 {#data-config}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-data-config"
>title="数据配置和收集"
>abstract="此部分显示 Adobe Analytics 环境中报告包的数量，以及您对流媒体的访问权限。 "

<!-- markdownlint-enable MD034 -->

### 分析报表包

1. 要分析报表包并决定要迁移哪些报表包，请导航到&#x200B;**[!UICONTROL 数据配置和收集]** > **[!UICONTROL 报表包]**，然后单击&#x200B;**[!UICONTROL 分析]**。

   ![报表包列表](assets/an_inv_rs.png)

   | 元素 | 描述 |
   | --- | --- |
   | 名称 | 报表包的名称 |
   | ID | 报表包ID (rsid)。 指定一个唯一 ID，其中仅可包含字母数字字符。此 ID 一经创建，即无法更改。Adobe 会设置所需的 ID 前缀，该前缀也无法更改。 |
   | 发生次数（最近 90 天） |  |
   | 量度 | How |
   | 维度 |  |
   | Analytics for Target (A4T) 已启用 |  |
   | 已启用营销渠道 |  |
   | Source Connector已启用 | 要关注的内容 |
   | 日程表类型 | 有关详细信息，请参阅[自定义日历](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/custom-calendar#) |

1. 请注意……

### 导出到 CSV

1. 要将报表包列表导出到.csv文件，请单击&#x200B;**[!UICONTROL 导出到CSV]**。

1. .csv文件将显示在“下载”文件夹中。

1. 在设备上使用电子表格应用程序打开并保存它。


## 用户管理 {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="用户管理"
>abstract="此部分显示 Adobe Analytics 环境中用户的数量。"

<!-- markdownlint-enable MD034 -->

用户管理将在Analytics清单的更高版本中提供。