---
description: 解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。
title: 启用 Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: 46118b1bd7f3b8c4e0f653778c16a1c51011fb2d
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 40%

---


# 激活和启用Activity Map

解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。

## 步骤 1. 激活Activity Map {#update_code}

Activity Map模块是AppMeasurement.js、Adobe Experience Platform标签和Web SDK (alloy.js)的一部分。 除非您更新到，否则无法收集Activity Map数据 **Web SDK版本2.15.0** 或更高，或 **Adobe Analytics tags扩展版本1.90** 或更高，或 **AppMeasurement版本1.6** 或更高。

+++Web SDK(Adobe Experience Platform标记扩展)

在Adobe Experience Platform标记中，导航到要实施Analytics的属性。 下 [!UICONTROL 扩展] -> [!UICONTROL Adobe Experience Platform Web SDK]，选择 **[!UICONTROL 启用点击数据收集]** 如下面突出显示的。 然后，使用更改构建库，并将库发布到生产环境。

![](assets/web_sdk.png)

+++

+++手动Web SDK实施

请参阅 [跟踪链接](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) 有关如何实施链接跟踪以及如何通过捕获 `region` 点击的HTML元素的ID。

>[!NOTE]
>
>当客户从一个页面导航到下一个页面时，用 Web SDK 启用链接跟踪当前将发送链接事件。这与 AppMeasurement 的工作方式不同，并且可能会导致将额外的可计费点击数发送到 Adobe。

+++

+++Analytics扩展(Adobe Experience Platform标记)

在Adobe Experience Platform标记中，导航到要实施Analytics的属性。 在 [!UICONTROL 安装扩展] 对话框，选择 **[!UICONTROL 使用Activity Map]**.

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. 下载最新的Javascript库以进行AppMeasurement。
转到 **[!UICONTROL 分析]** > **[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 代码管理器]**.
1. 通过以下方式实施它 [这些说明](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=zh-Hans).

+++

## 步骤 2. 启用 Activity Map 报表 {#enable}

您需要在报表包级别启用Activity Map报表。

1. 登录 Adobe Analytics，然后导航至 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > 选择报表包 > **[!UICONTROL 编辑设置]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map 报告]**。

1. Activity Map 会收集 Activity Map 报表中的链接数据。为了激活，您必须首先通过单击&#x200B;**[!UICONTROL 启用 Activity Map 报表]**&#x200B;来激活变量。

   该步骤会添加您收集数据所需的所有维度。

   ![](assets/enable.png)

1. 大约一小时后，选中 [Activity Map 页面报表](/help/analyze/activity-map/activitymap-reporting-analytics.md)，这样一来，凡是用户单击了其中链接的所有页面，都将显示在报表中。

## 步骤 3. 将用户添加到 [!UICONTROL Activity Map访问] 产品配置文件 {#add_users}

1. 单击&#x200B;**[!UICONTROL 将用户添加至组]**。

   这会将您转到中的产品配置文件页面 [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. 如果您尚未创建 [!UICONTROL Activity Map访问] 产品配置文件，请立即执行此操作。 此配置文件所需的权限项为 [!UICONTROL Analytics工具] > [!UICONTROL Activity Map] 和 [!UICONTROL Analytics工具] > [!UICONTROL 区段发布].

1. 将用户添加到该产品配置文件。 这允许您的用户从下载Activity Map  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL ActivityMap]** .

