---
description: 有关在Activity Map中设置、配置和使用功能的常见问题解答。
title: Activity Map 常见问题解答
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: 5a8ff1c81644c12f7d00ef147db197f54c48f60c

---


# Activity Map 常见问题解答

有关在Activity Map中设置、配置和使用功能的常见问题解答。

## 实现和 AppMeasurement

**问：启用新的Activity Map的实施步骤有哪些？**

答：请查看启 [用活动图](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**问：是否所有的 Analytics 客户都可以访问管理工具 Activity Map 启用页面？**

答：Adobe SiteCatalyst 客户无法访问管理控制台的 Activity Map 启用页面。只有Adobe Analytics Standard和Adobe Analytics Premium合同下的公司才有权访问此配置页面。

**问：能否通过 Dynamic Tag Management (DTM) 配置新的 AppMeasurement 代码？**

答：是的，您可以手 [动实施](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) 新的AppMeasurement代码。

**问：AppMeasurement v1.6库中有哪些重大更改？**

答：AppMeasurement v1.6中唯一的更改是Activity Map链接跟踪流程方法，该方法需要页面名称、链接ID和区域ID的集合。

**问：AppMeasurement是否将在域级别而非特定页面上推出？**

答：AppMeasurement在报表包级别推出。 报表包级别通常与域级别关联，但这与每个实现不同。

**问：DTM会自动加载比Activity Map想要的(1.5.1)更早版本的访客API(1.3.4)。 这是问题吗？**

答：没问题。Activity Map功能不取决于VisitorAPI。

## Activity Map 应用程序

<!--**Q: How does Activity Map support Single-Page Applications (SPA)?**

A: 

* Every few seconds, Activity Map scans the web page, looking for changes to the page. ActivityMap finds new content on the page without needing a new page load, but this new content is always attributed to the first pageName found when the page loaded.

* Activity Map checks to see if the visibility of links that it knows about has changed. If a change in visibility is found, then the [Links On Page](/help/analyze/activity-map/activitymap-links-report.md) table's Present column for that link updates with **[!UICONTROL Displayed]** or **[!UICONTROL Hidden]**.

* When user interaction creates new content, any new elements that are found by AppMeasurement to be a link will be added to the **[!UICONTROL Links On Page]** table. Activity Map sends a new data request that includes these new links. The new links should appear in the **[!UICONTROL Links On Page]** table when the data request is handled by the UI.-->

**问：Activity Map是否提供“查看”数据？**

答：否，Adobe不跟踪已查看的链接。

**问：如果我之前在我的网站上没有使用访客ClickMap，我是否可以使用Activity Map?**

答：安装旧版本（现在简称为ClickMap）并不是实施新版本的先决条件。 Adobe将在有限的时间内继续支持旧版本。

**问：Activity Map支持哪些浏览器和版本？**

答：我们支持四个主要浏览器（Chrome、Firefox、Safari和IE）的最新版本。

**问：什么是默认的叠加设置？**

答：默认情况下，活动图显示已收集数据的所有链接。

当弹出式面板显示在客户网页顶部时，属于位于弹出式面板下方的链接的叠加可能显示在弹出式面板的顶部。

**问：为什么缺少某些排名项叠加？**

答：某些排名的链接可能会在页面中隐藏（例如，子菜单链接）。 因此，不会显示其相应的链接叠加。 因此，您会看到缺少某些特定排名值的叠加排名，因为该排名是为页面中的所有链接（当前链接+隐藏链接）计算的。

**问：如何在“所有链接”报告中确定链接等级？**

* 在“ **渐变** ”和“ **气泡** ”模式中：排名由度量列决定。 对于具有相同度量值的链接，其排名会根据链接ID的字母顺序进一步确定。
* 在“ **增益和失败者** ”模式中，排名主要由“%增益”列确定。 对于具有相同增益的链接，其排名会根据链接ID的字母顺序进一步确定。

**问：为什么在Activity Map运行时未收集链接点击数据？**

答：在Activity Map使用中，链接点击数据不会由Analytics标记收集。 此行为遵循ClickMap插件的行为。

**问：Activity Map所有链接报表与Reports &amp; Analytics Activity Map报表相比如何？**

答：要在 Activity Map 中提取“所有链接”报表，我们将创建一个划分请求，如下所示：Activity Map 页面 =“visitedpage”，按 `<list of link&regions present in the page at rendering time>` 中的 Activity Map 链接和区域划分。

要在Reports &amp; Analytics中获取等效的报表，您首先需要导航到Activity Map页面报表。 在Activity Map中，您可以过滤访问过的页面名称。 访问过的Pagename显示在Activity Map页面详细信息底部面板的左列中。 找到该页面后，您可以从该页面中进行细分，然后选择Activity Map链接和区域作为辅助维度。

但是，请务必注意，在R&amp;A中获得的报告将列出为该页面收集的所有链接和区域。 但Activity Map仅报告网页中当前存在的Links&amp;Regions。 所以如果有一个新闻网站，它只显示这个时候的新闻报道的数据，而不显示当天早些时候的新闻报道。

**问：Activity Map如何处理包含多个标记的页面，这些标记列出多个报表包？**

答：默认情况下，Activity Map使用与页面发送的第一个标记关联的报表包。 您可以通过“Activity Map 设置”> 其他选项卡，选择带有标签的其他报表包。

**问：Activity Map扫描分析标记的时间长短？**

答：在页面完成事件后，我们最多可在20秒内扫描Analytics标记。

**问：Activity Map如何处理动态内容？**

答：Activity Map每2秒检查一次，以查看它是否在网页状态中发现了以下更改：

* 已可见的HTML内容
* 隐藏的HTML内容
* 插入的新HTML内容

如果内容被隐藏或显示，应用程序会自动将受影响的链接状态（以及叠加）从隐藏更改为显示或从显示更改为隐藏。

如果插入了新内容，应用程序将检索关联的链接，为它们提取分析数据，并为这些链接添加叠加。

**问：页面流报表基于什么指标？**

答：显示的所有数据均基于页面视图。

**问：能否解释Activity Map对各种类型页面的行为？**

*不带Analytics标签的网页*

工具栏下方显示一条警告消息，指示不存在标记。

*包含不兼容Analytics标记（AppMeasurement v1.5或更早版本）的网页*

将显示一条警告消息，指示您需要将页面代码升级到v1.6或更高版本。

*网页包含兼容的 Analytics 标签（AppMeasurement v1.6 或更高版本），但是管理工具中未启用 Activity Map 报告*

出现警告消息，指示您需要请求管理员 \[启用 Activity Map 报表\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) 。

**问：能否通过 [Analytics 数据馈送](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html)导出 Activity Map 数据 (contextData)？**

答：没问题。

## Activity Map 中的区段划分

**问：区段是否与单个用户区段关联？ Activity Map中是否提供共享区段？**

答：Activity Map会从Analytics继承您的报告区段。

**问：区段是否在实时模式下工作？**

答：否，区段在“实时”模式下不工作。 该功能与Reports &amp; Analytics中的实时报告功能相当。

## 虚拟报表包

**问：Activity Map是否与虚拟报告套件兼容？**

答：兼容。但是，由于虚拟报告包的限制，Activity Map的“实时模式”与虚拟报告包不兼容。
