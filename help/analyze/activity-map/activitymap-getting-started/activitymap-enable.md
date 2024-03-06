---
description: 解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。
title: 启用 Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: e35210582e94037cf286b98e7e0a6b06040a8c6f
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 99%

---


# 激活并启用 Activity Map

解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。

## 步骤 1. 激活 Activity Map {#update_code}

Activity Map 模块是 AppMeasurement.js、Adobe Experience Platform 标记和 Web SDK (alloy.js) 的一部分。除非您更新到 **Web SDK 版本 2.15.0** 或更高版本、**Adobe Analytics 标记扩展 v1.90** 或更高版本，或者 **AppMeasurement 版本 1.6** 或更高版本，否则无法收集 Activity Map 数据。

+++Web SDK（Adobe Experience Platform 标记扩展）

1. 在 Adobe Experience Platform 标记中，导航到要为其实施 Analytics 的属性。在[!UICONTROL 扩展] -> [!UICONTROL Adobe Experience Platform Web SDK] 下，选择&#x200B;**[!UICONTROL 启用点击数据收集]**，如下突出显示。
1. 使用更改构建库。
1. 将库发布到生产环境。

![](assets/web_sdk.png)

**验证**

使用 Developer Console“网络”选项卡来交互调用：

1. 在站点上加载 Development Launch 脚本。
1. 在“点击元素”上，在“网络”选项卡中搜索“/ee”

   ![](assets/validation1.png)

Adobe Experience Platform Debugger：

1. 下载并安装 [Adobe Experience Platform Debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob)。
1. 转到[!UICONTROL 日志] > [!UICONTROL Edge] > [!UICONTROL 连接到 Edge]。

   ![](assets/validation2.jpg)

**常见问题解答**

* **交互调用未在“网络”选项卡中触发。**
收集调用中的点击数据收集，我们需要使用“/ee”或“collect?”进行过滤

* **收集调用没有负载显示。**
收集调用经过设计，使跟踪不影响到其他站点的导航，因此文档卸载功能适用于收集调用。这不会影响您的数据收集，但如果您需要在页面上验证，请将 target = &quot;_blank&quot; 添加到相应的元素。之后，链接将在新选项卡中打开。

* **如何忽略 PII 的收集？**
在 &lt;&lt;在链接点击发送回调之前>> 中添加相应的条件，并返回 false 以忽略这些值。[了解详情](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans)

  示例代码：

  ![](assets/sample-code.png)

+++

+++手动 Web SDK 实施

有关如何实施链接跟踪以及如何通过捕获点击的 HTML 元素的 `region` 来启用 Activity Map 的信息，请参阅[跟踪链接](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html)。

>[!NOTE]
>
>当客户从一个页面导航到下一个页面时，用 Web SDK 启用链接跟踪当前将发送链接事件。这与 AppMeasurement 的工作方式不同，并且可能会导致将额外的可计费点击数发送到 Adobe。

+++

+++Analytics 扩展（Adobe Experience Platform 标记）

在 Adobe Experience Platform 标记中，导航到要为其实施 Analytics 的属性。在[!UICONTROL 安装扩展]对话框中，选择&#x200B;**[!UICONTROL 使用 Activity Map]**。

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. 下载最新的 JavaScript AppMeasurement 库。
转到 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 代码管理器]**。
1. 请按照[这些说明](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=zh-Hans)来实施它。

+++

## 步骤 2. 启用 Activity Map 报表 {#enable}

您需要在报表包级别上启用 Activity Map 报表。

1. 登录 Adobe Analytics，然后导航至 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > 选择报表包 > **[!UICONTROL 编辑设置]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map 报告]**。

1. Activity Map 会收集 Activity Map 报表中的链接数据。为了激活，您必须首先通过单击&#x200B;**[!UICONTROL 启用 Activity Map 报表]**&#x200B;来激活变量。

   该步骤会添加您收集数据所需的所有维度。

   ![](assets/enable.png)

1. 大约一小时后，选中 [Activity Map 页面报表](/help/analyze/activity-map/activitymap-reporting-analytics.md)，这样一来，凡是用户单击了其中链接的所有页面，都将显示在报表中。

## 步骤 3. 将用户添加到 [!UICONTROL Activity Map 访问]产品配置文件 {#add_users}

1. 单击&#x200B;**[!UICONTROL 将用户添加至组]**。

   这会将您带入 [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview) 中的产品配置文件页面。

1. 如果您尚未创建 [!UICONTROL Activity Map 访问]产品配置文件，请立即创建。此配置文件所需的权限项为 [!UICONTROL Analytics 工具] > [!UICONTROL Activity Map] 和 [!UICONTROL Analytics 工具] > [!UICONTROL 区段发布]。

1. 将用户添加到该产品配置文件。这将允许您的用户从 **[!UICONTROL Adobe Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL ActivityMap]** 下载 Activity Map。

