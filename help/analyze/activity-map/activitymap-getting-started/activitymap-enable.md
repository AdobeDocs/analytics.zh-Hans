---
description: 解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。
title: 启用 Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: 4c6df8bc08f326bfb54b27eb61f97b4be2320805
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 27%

---


# 激活和启用Activity Map

解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。

## 步骤 1. 激活Activity Map {#update_code}

Activity Map模块是AppMeasurement.js、Adobe Experience Platform标签和Web SDK (alloy.js)的一部分。 除非您更新到，否则无法收集Activity Map数据 **Web SDK版本2.15.0** 或更高，或 **Adobe Analytics tags扩展版本1.90** 或更高，或 **AppMeasurement版本1.6** 或更高。

+++Web SDK(Adobe Experience Platform标记扩展)

1. 在Adobe Experience Platform标记中，导航到要实施Analytics的属性。 下 [!UICONTROL 扩展] -> [!UICONTROL Adobe Experience Platform Web SDK]，选择 **[!UICONTROL 启用点击数据收集]** 如下面突出显示的。
1. 使用更改构建库。
1. 将库发布到生产环境。

![](assets/web_sdk.png)

**验证**

使用“开发人员控制台网络”选项卡的Interact调用：

1. 在网站上加载开发Launch脚本。
1. 在单击元素时，在“网络”选项卡中搜索“/ee”

   ![](assets/validation1.png)

Adobe Experience Platform Debugger：

1. 下载并安装 [Adobe Experience Platform debugger](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpo).
1. 转到 [!UICONTROL 日志] > [!UICONTROL Edge] > [!UICONTROL 连接到边缘].

   ![](assets/validation2.jpg)

**常见问题解答**

* **在“网络”选项卡中不会触发interact调用。**
对于收集调用中的点击数据收集，我们需要使用“/ee”或“collect？”进行过滤。

* **收集调用没有有效负荷显示。**
收集调用的设计方式使得跟踪不会影响到其他站点的导航，因此文档卸载功能适用于收集调用。 这不会影响数据收集，但如果您需要在页面上验证，请将target = &quot;_blank&quot;添加到相应的元素。 然后，该链接将在新选项卡中打开。

* **如何忽略PII的收藏集？**
在&lt;&lt; on before link click send callback>>中添加相应的条件，并返回false以忽略这些值。 [了解详情](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans)

  示例代码:

  ![](assets/sample-code.png)

+++

+++手动Web SDK实施

请参阅 [跟踪链接](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) 有关如何实施链接跟踪以及如何通过捕获启用Activity Map的信息 `region` 点击的HTML元素的ID。

>[!NOTE]
>
>当客户从一个页面导航到下一个页面时，启用Web SDK的链接跟踪当前会发送链接事件。 这与 AppMeasurement 的工作方式不同，并且可能会导致将额外的可计费点击数发送到 Adobe。

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

