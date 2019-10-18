---
description: 有关在[!DNL Activity Map]中设置、配置和使用功能的常见问题解答。
seo-description: 有关在[!DNL Activity Map]中设置、配置和使用功能的常见问题解答。
seo-title: '[!DNL活动图]常见问题解答'
solution: Analytics
title: '[!DNL活动图]常见问题解答'
topic: Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# [!DNL Activity Map] 常见问题解答

Frequently asked questions for setting up, configuring, and employing features in [!DNL Activity Map].

## 实现和 AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**问：启用新功能的实施步骤有哪些[!DNL Activity Map]?**

答：请查看 [启用[!DNL活动图]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**问：是否所有的 Analytics 客户都可以访问管理工具 Activity Map 启用页面？**

A: Adobe SiteCatalyst customers do not have access to the Admin Console’s [!DNL Activity Map] Enablement page. 只有签署了 Adobe Analytics Standard 和 Adobe Analytics Premium 合同的公司，才具备访问此配置页面的权限。

**问：能否通过动态标签管理 (DTM) 配置新的 AppMeasurement 代码？**

答：可以，您可以[手动实现](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html)新的 AppMeasurement 代码。

**问：AppMeasurement v1.6 库有何重要变化？**

A: The only change in AppMeasurement v1.6 is in the [!DNL Activity Map] link tracking process methodology that requires the collection of Page name, Link ID and RegionID.

**问：能否在域级别上部署 AppMeasurement，而不是针对特定页面进行部署？**

答：AppMeasurement 是在报表包级别上部署的。报表包级别通常与域级别关联，但是会因为具体的实施而有所不同。

**[!DNL Activity Map]问：DTM 自动加载的 Visitor API 版本 (1.3.4) 早于 需要的版本 (1.5.1)。这样会有问题吗？**

答：没问题。[!DNL Activity Map] 功能不取决于VisitorAPI。

## [!DNL Activity Map] 应用程序 {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**[!DNL Activity Map]问：如果我之前没有在网站上用过访客 ClickMap，我能否使用 ？**

答：安装旧版本（现在简称为 ClickMap）并不是实现新版本的前提条件。Adobe 将在一段有限的时间内继续支持旧版本。

**问：支持哪些浏览器和版本[!DNL Activity Map]?**

答：我们只支持四种主要浏览器（Chrome、Firefox、Safari 和 IE）的最新版本。

**问：默认的叠加图设置是什么？**

A: By default, [!DNL Activity Map] shows ALL links that have collected data.

当客户网页顶部出现弹出式面板时，位于弹出式面板下方的链接所包含的叠加图可能会显示在弹出式面板的顶部。

**问：为什么有一些排名项目叠加图会丢失？**

答：一些排名链接可能不显示在页面中（例如，子菜单链接）。因此，看不到这些排名链接所对应的链接叠加图。这样一来，您可能会发现一些丢失了特定排名值的叠加图排名，这是因为排名是针对页面中的所有链接（包含显示的链接和未显示的链接）而计算的。

**问：“所有链接”报表中的链接排名是如何确定的？**

* 在&#x200B;**渐变**&#x200B;和&#x200B;**气泡**&#x200B;模式下：排名由量度列来确定。对于量度值相同的链接而言，其排名由链接 ID 的字母顺序进一步确定。
* 在&#x200B;**获胜方和失败方**&#x200B;模式下，排名主要由“获胜的百分比”列确定。对于获胜值相同的链接而言，其排名由链接 ID 的字母顺序进一步确定。

**[!DNL Activity Map]问：为什么在 运行时无法收集链接点击数据？**

A: While [!DNL Activity Map] is in use, link click data is not collected by the Analytics tag. 此行为与 ClickMap 插件的行为一致。

**问：为什么量度下拉菜单多次列出同样的量度？**

A: [!DNL Activity Map] lists metrics for all report suites. 因此，如果贵公司没有执行[量度合并流程](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html)，就会看到重复的量度。

您可以通过“量度”下拉菜单将计算的量度列表限制为分配给所访问页面的报表包的量度。

**问：所有链接报[!DNL Activity Map]告与报告和分析报告相比如[!DNL Activity Map]何？**

答：要在中拉取“所有链接”报 [!DNL Activity Map]表，我们将创建如下细分请求：页 [!DNL Activity Map] 面= "visitedpage"，按中的 [!DNL Activity Map] Link&amp;Region分类 `<list of link&regions present in the page at rendering time>`。

To get an equivalent report in Reports &amp; Analytics, you would need to first navigate to the [!DNL Activity Map] Page report. There, you would filter for the visited pagename in [!DNL Activity Map]. The visited Pagename is shown in the left column in the [!DNL Activity Map] Page Details Bottom Panel. Once the page has been found, you can break down from that page and choose [!DNL Activity Map] Links &amp; Regions as a secondary dimension.

但是，务必需要注意的是，在“报告与分析”中获得的报表将列出为该页面收集的所有链接和区域。But [!DNL Activity Map] only reports on Links&amp;Regions that are currently present in the webpage. 所以，如果您有一个新闻网站，Activity Map 只报告当前显示的新闻报道的数据，并不包括当天早些时候显示的新闻报道。

**[!DNL Activity Map]问： 如何使用包含了多个标签的页面（列有多个报表包）？**

A: By default, [!DNL Activity Map] uses the report suite that is associated with the first tag that is sent by the page.

您可以通过[!DNL Activity Map] 设置 &gt; 其他选项卡，选择带有标签的其他报表包。

**[!DNL Activity Map]问： 扫描 Analytics 标签要花多长时间？**

答：在页面完成事件发生后，我们至多需要 20 秒来扫描 Analytics 标签。

**问：如何处[!DNL Activity Map]理动态内容？**

A: [!DNL Activity Map] checks every 2 seconds to see if it has found changes in the state of the web page such as:

* HTML 内容变为可见
* 隐藏了 HTML 内容
* 插入了新的 HTML 内容

如果隐藏或显示了内容，该应用程序则会自动将受影响的链接状态（以及因此形成的叠加图）从“隐藏”改为“显示”或从“显示”改为“隐藏”。

如果插入了新内容，该应用程序将取回相关链接，并为它们提取分析数据，然后为这些链接添加叠加图。

**问：页面流量报表基于哪种量度？**

答：显示的所有数据都是基于页面查看次数。

**[!DNL Activity Map]问：能否解释一下与各类页面相对应的 行为？**

*网页不包含 Analytics 标签*

工具栏下方会出现警告消息，指示不存在任何标签。

*网页包含不兼容的 Analytics 标签（AppMeasurement v1.5 或早期版本）*

将显示一条警告消息，指示您需要(/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)将页面代码升级到v1.6。

*[!DNL Activity Map]网页包含兼容的 Analytics 标签（AppMeasurement v1.6 或更高版本），但是管理工具中未启用 报告*

将显示一条警告消息，指示您需要让您的管理员\[启用 [!DNL Activity Map] 报告\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md")。

**问：我是否可以通[!DNL Activity Map]过[Analytics Data Feed导出数据(contextData)](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)?**

答：不能。

## Segmentation in [!DNL Activity Map]{#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**问：区段是否与单个用户区段相关联？Or are shared Admin-level segments available in[!DNL Activity Map]?**

A: [!DNL Activity Map] inherits your Admin-level segments (reporting segments) from Analytics.

**问：实时模式下能否使用区段？**

答：不能，实时模式下不能使用区段。其功能等同于“Reports &amp; Analytics”中实时报告的功能。

## Virtual report suites {#section_BDB0CA9E732F478EAC349A79753A78DB}

**问：是否[!DNL Activity Map]与虚拟报告套件兼容？**

答：兼容。However, due to virtual report suite limitations, [!DNL Activity Map]'s Live Mode is not compatible with virtual report suites.
