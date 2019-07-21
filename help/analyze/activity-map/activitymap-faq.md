---
description: 有关在 Activity Map 中设置、配置和部署功能的常见问题解答。
seo-description: 有关在 Activity Map 中设置、配置和部署功能的常见问题解答。
seo-title: Activity Map 常见问题解答
solution: Analytics
title: Activity Map 常见问题解答
topic: Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178 af370
translation-type: tm+mt
source-git-commit: 8f72f8cf086be0eade5616b074123a9f22e33347

---


# Activity Map 常见问题解答

有关在 Activity Map 中设置、配置和部署功能的常见问题解答。

## 实现和 AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**问：启用新 Activity Map 的实现步骤有哪些？**

答：请参阅[启用活动地图](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**问：是否所有的 Analytics 客户都可以访问管理工具 Activity Map 启用页面？**

答：Adobe SiteCatalyst 客户无法访问管理控制台的 Activity Map 启用页面。只有签署了 Adobe Analytics Standard 和 Adobe Analytics Premium 合同的公司，才具备访问此配置页面的权限。

**问：能否通过动态标签管理 (DTM) 配置新的 AppMeasurement 代码？**

答：可以，您可以[手动实现](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html)新的 AppMeasurement 代码。

**问：AppMeasurement v1.6 库有何重要变化？**

答：AppMeasurement v1.6 唯一的变化体现在 Activity Map 链接跟踪过程的方法上，该方法要求收集页面名称、链接 ID 和区域 ID。

**问：能否在域级别上部署 AppMeasurement，而不是针对特定页面进行部署？**

答：AppMeasurement 是在报表包级别上部署的。报表包级别通常与域级别关联，但是会因为具体的实施而有所不同。

**问：DTM 自动加载的 Visitor API 版本 (1.3.4) 早于 Activity Map 需要的版本 (1.5.1)。这样会有问题吗？**

答：没问题。Activity Map 的功能并不是取决于 Visitor API。

## Activity Map application {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**问：如果我之前没有在网站上用过访客 ClickMap，我能否使用 Activity Map？**

答：安装旧版本（现在简称为 ClickMap）并不是实现新版本的前提条件。Adobe 将在一段有限的时间内继续支持旧版本。

**问：Activity Map 支持哪些浏览器和版本？**

答：我们只支持四种主要浏览器（Chrome、Firefox、Safari 和 IE）的最新版本。

**问：默认的叠加图设置是什么？**

答：默认情况下，Activity Map 会显示收集了数据的所有链接。

当客户网页顶部出现弹出式面板时，位于弹出式面板下方的链接所包含的叠加图可能会显示在弹出式面板的顶部。

**问：为什么有一些排名项目叠加图会丢失？**

答：一些排名链接可能不显示在页面中（例如，子菜单链接）。因此，看不到这些排名链接所对应的链接叠加图。这样一来，您可能会发现一些丢失了特定排名值的叠加图排名，这是因为排名是针对页面中的所有链接（包含显示的链接和未显示的链接）而计算的。

**问：“所有链接”报表中的链接排名是如何确定的？**

* 在&#x200B;**渐变**&#x200B;和&#x200B;**气泡**&#x200B;模式下：排名由量度列来确定。对于量度值相同的链接而言，其排名由链接 ID 的字母顺序进一步确定。
* 在&#x200B;**获胜方和失败方**&#x200B;模式下，排名主要由“获胜的百分比”列确定。对于获胜值相同的链接而言，其排名由链接 ID 的字母顺序进一步确定。

**问：为什么在 Activity Map 运行时无法收集链接点击数据？**

答：使用 Activity Map 时，Analytics 标签无法收集链接点击数据。此行为与 ClickMap 插件的行为一致。

**问：为什么量度下拉菜单多次列出同样的量度？**

答：Activity Map 会列出所有报表包的量度。因此，如果贵公司没有执行[量度合并流程](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html)，就会看到重复的量度。

您可以通过“量度”下拉菜单将计算的量度列表限制为分配给所访问页面的报表包的量度。

**问：Activity Map“所有链接”报表与“Reports &amp; Analytics”Activity Map 报告有何区别？**

A: To pull the All Links Report in Activity Map, we create a breakdown request as follows: Activity Map Page = “visitedpage”, broken down by Activity Map Link&amp;Region in `<list of link&regions present in the page at rendering time>`.

要在“Reports &amp; Analytics”中获得同样的报表，您首选需要导航至 Activity Map 页面报表。通过该报表，您可以在 Activity Map 中过滤访问过的页面名称。访问过的页面名称将显示在 Activity Map 详细信息页面底部面板的左列中。找到页面后，您可以划分此页面，并选择 Activity Map 链接和区域作为次要维度。

但是，务必需要注意的是，在“报告与分析”中获得的报表将列出为该页面收集的所有链接和区域。而 Activity Map 仅报告当前显示在网页上的链接和区域。所以，如果您有一个新闻网站，Activity Map 只报告当前显示的新闻报道的数据，并不包括当天早些时候显示的新闻报道。

**问：Activity Map 如何使用包含了多个标签的页面（列有多个报表包）？**

答：默认情况下，Activity Map 会使用与页面发送的第一个标签相关联的报表包。

您可以通过Activity Map 设置 &gt; 其他选项卡，选择带有标签的其他报表包。

**问：Activity Map 扫描 Analytics 标签要花多长时间？**

答：在页面完成事件发生后，我们至多需要 20 秒来扫描 Analytics 标签。

**问：Activity Map 如何处理动态内容？**

答：Activity Map 每 2 秒检查一次，判断是否发现网页状态有以下变化：

* HTML 内容变为可见
* 隐藏了 HTML 内容
* 插入了新的 HTML 内容

如果隐藏或显示了内容，该应用程序则会自动将受影响的链接状态（以及因此形成的叠加图）从“隐藏”改为“显示”或从“显示”改为“隐藏”。

如果插入了新内容，该应用程序将取回相关链接，并为它们提取分析数据，然后为这些链接添加叠加图。

**问：页面流量报表基于哪种量度？**

答：显示的所有数据都是基于页面查看次数。

**问：能否解释一下与各类页面相对应的 Activity Map 行为？**

*网页不包含 Analytics 标签*

工具栏下方会出现警告消息，指示不存在任何标签。

*网页包含不兼容的 Analytics 标签（AppMeasurement v1.5 或早期版本）*

系统会显示一条警告消息，指示您需要(/home/analyze/activity-map/activitymap-getting-started-started-documents/activitymap-enablable. md)将页面代码升级到v1.6。

*网页包含兼容的 Analytics 标签（AppMeasurement v1.6 或更高版本），但是管理工具中未启用 Activity Map 报告*

系统会显示一条警告消息，指示您需要要求您的管理员\[启用活动地图报告\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-charts/activitymap-enable-md”)。

**问：能否通过[Analytics 数据馈送](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)导出 Activity Map 数据 (contextData)？**

答：不能。

## Activity Map 中的区段划分 {#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**问：区段是否与单个用户区段相关联？或者，Activity Map 中是否有可用的管理员级别的共享区段？**

A：Activity Map从Analytics继承您的管理员级区段(报告区段)。

**问：实时模式下能否使用区段？**

答：不能，实时模式下不能使用区段。其功能等同于“Reports &amp; Analytics”中实时报告的功能。

## Virtual report suites {#section_BDB0CA9E732F478EAC349A79753A78DB}

**问：Activity Map 是否兼容虚拟报表包？**

答：兼容。但是，由于虚拟报表包的限制，Activity Map 的实时模式与虚拟报表包不兼容。
