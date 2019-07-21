---
description: 显示有关网站的量化信息，如访客查看某个页面的次数、从特定页面进行的购买总数、访客进入网站的时间及其他类似的量化数据。其中每个报表都是一个量度，您可以将其放在其他基于项目的报表中。
seo-description: 显示有关网站的量化信息，如访客查看某个页面的次数、从特定页面进行的购买总数、访客进入网站的时间及其他类似的量化数据。其中每个报表都是一个量度，您可以将其放在其他基于项目的报表中。
seo-title: 站点量度报告
solution: Analytics
title: 站点量度报告
topic: Ad Hoc Analysis
uuid: 0730747a-216f-4a58-b62 b-a9812968 cde5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 站点量度报告

显示有关网站的量化信息，如访客查看某个页面的次数、从特定页面进行的购买总数、访客进入网站的时间及其他类似的量化数据。其中每个报表都是一个量度，您可以将其放在其他基于项目的报表中。

## Site Metrics reports {#concept_0639CA16551749A693F49ADED4842CCE}

显示有关网站的量化信息，如访客查看某个页面的次数、从特定页面进行的购买总数、访客进入网站的时间及其他类似的量化数据。其中每个报表都是一个量度，您可以将其放在其他基于项目的报表中。

量度报表随时间的推移形成趋势。您可以向这些报表应用时间和每周日期粒度。或者，可分析网站逗留时间、购买数目、收入及类似量度。

[!UICONTROL 网站量度]菜单中提供有以下网站量度报表。

## 页面查看次数报表 {#concept_5331AFB6948547F7B8DF367B49360E6B}

<!-- 

c_reports_pageviews.xml

 -->

页面查看报表是一个趋势报表，显示选定时段（小时、日、周、月份、季度或年）内网站页面的查看次数。[!UICONTROL 页面查看]是对完整页面文档的请求，而不是页面的某个元素，如图像或视频。例如，如果单一访客在一次访问中查看 15 个页面，则计算 15 次页面查看。如果一位访客在一次访问期间查看三次同一页面，将计算三次页面查看。您可利用此报表来跟踪网站中每个页面的查看次数，以及整个网站的页面查看次数总和。

## 访问报表 {#concept_50CA55CF2A41430CBC754AEEEE6023A9}

显示指定时间段内整个网站的访问量。*访问*&#x200B;是指查看一系列页面。访问从访客加载页面时开始，在处于非活动状态 30 分钟后结束。只要访客在超时前加载至少一个页面，则访问可持续数小时。访问不一定等同于浏览器会话。例如，如果访客关闭浏览器，再重新打开浏览器，并在 5 分钟后访问网站，则仍将其视为同一次访问。这也意味着如果访客持续 35 分钟查看一个网页，那么此访问将被关闭并进行处理，如果该访客点进了其他页面，则会开始一个新的访问。访问量是通过 Cookie 进行跟踪的。一次访问会在持续活动达到 12 个小时后结束。

<!-- 

c_reports_visits.xml

 -->

在 Marketing Reports &amp; Analytics 中，您可以在选择的页面运行[!UICONTROL 访问报表]。在 Ad Hoc Analysis 中，您可以对数据分段以查看特定页面。

## 独特访客报表 {#concept_39097C54E46C496CBAD537329DB3C84A}

趋势报表显示访问您的网站的独特访客数。每名访客计作一人，无论他对您的网站访问了多少次。Adobe 的 Cookie 握手技术（专利申请中）可以将独特访客同回访访客区别开来。这种新技术克服了 Internet 浏览器 Cookie 技术的限制和不足。

<!-- 

c_reports_unique_visitors.xml

 -->

此报表的用途包括：

* 了解指定时间段内查看过您的网站的不同身份访客的数量。
* 查看近期流量模式，并探究促销活动如何为您的网站带来独特访客。
* 比较独特访客数量和页面查看次数。

## 访客报表 {#concept_7371DAB5DA474D03A2D1448F151E011B}

显示选定时间段（小时、日、周、月、季或年）内网站独特访客人数。独特访客在所选时间范围内仅计数一次。在超过该时间范围前，不会将回访网站的访客再次算作独特用户。

<!-- 

c_reports_visitors.xml

 -->

表底部显示的总计值为指定时间段内总访问量，不一定表示独特访客人数。例如，如果运行时间范围为多日的[!UICONTROL 每日独特访客报表]，则总值可包括重复访客人数：由于同一访客可能在第二天回访，因而会再次计数。但若运行[!UICONTROL 每月独特访客报表]，则“总计”列会准确地显示当月独特访客人数。

## 每次访问逗留时间报表 {#concept_5CDB759F9C9B4002A786A71F2BDBB292}

显示访客在每次访问期间查看网站所花费的时间。它还包括“平均网站逗留时间”统计信息，显示访客查看网站所用的平均时间。

<!-- 

c_reports_time_spent_per_visit.xml

 -->

使用该报表可以：

* 确定访客在您的网站停留的时间。
* 确定网站中引起访客兴趣的内容和促销活动。
* 查明为什么网站流量很大，但访客却很快离开。

## 购买报表 {#concept_E3B9AF43CCD24F25A85D05DFB51C4740}

显示收入、订购和件数的汇总数据。You can also view the [!DNL Purchase Conversion Funnel] report.

<!-- 

c_reports_purchases.xml

 -->

* **收入**：用于查看所选时间段的总利润。例如，三月份的收入、上周购买数目或今日收入。
* **订购**：显示指定时间段内网站上的订购数。订购中可包含多种产品。
* **件数**：显示指定时间段内订购的总件数。
* **购买转换漏斗**：理想的选择是在您的网站上以特定订单发生转换事件(如零售设置)。漏斗报表可显示转化过程中每一步的转化量度，以及订购、收入和件数。

## 购物车报表 {#concept_6AEC5A6C707B46B790C1A79E72F9A339}

显示指定时间段内打开的购物车数目。您可以运行报表以分析购物车查看、加货、减货和结账。购物车通常在客户选择购买项目时打开，但在没有项目时也能打开它。

<!-- 

c_reports_shopping_cart.xml

 -->

[!UICONTROL 购物车报表]的用途包括：

* 确定网站上已打开购物车的模式或数量的高值或低值。
* 详细检查特定时间段，以查找有关专门贡献于购物车打开的量度的详细信息。

## 自定义事件报表 {#concept_9337B2FB8A3F417BA8689FE7FD64629F}

您希望访客在您的网站上完成的转化操作。这些操作可能是注册、订阅和填写商机表单、开始聊天、购买、预订或完成调查。

<!-- 

c_reports_custom_events.xml

 -->

由于每个分析报表包都不相同，因此对于不同的客户，此报表集的用途也不尽相同。[!UICONTROL 自定义事件]报表可用作显示事件发生次数的计数器。例如，如果将 **[!UICONTROL event1]设置为计算文档的下载次数，则事件 1 的自定义事件报表会显示该事件（或下载）发生的总次数。**你可使用多个自定义事件报表。

## 转化报表 {#concept_BDD3DD8A46F043BB916C7E346E7C314F}

显示您的网站各方面获得的收入。您可以看到显示广告促销活动收入的报表、比较忠诚客户与新客户所贡献收入的报表、按产品划分收入的报表以及其他各种收入报表。转化报表还可显示其他成功事件，如广告点击、下载或其他事件。

<!-- 

c_reports_conversion.xml

 -->

转化报告包含所有重要客户活动的实时统计信息，包括：

* 客户购买模式
* 购物车量度（包括流失量度）
* 客户转化率
* 广告和频道合作伙伴的成效
* 在线和离线营销活动绩效
* 客户忠诚度量度
* 销售周期分析

## 营销渠道报表 {#concept_81FFA8C15A9B4914BFED37488ADD17FD}

营销渠道报表显示第一个和最后一个成交流量渠道分配，并显示关键和标准量度，如收入、订单和成本，以使您对每个渠道产生的收入量一目了然。You configure channel definition rules in the [!DNL Admin Console], and APIs specific for the channel reports are available.

<!-- 

c_reports_marketing_channel.xml

 -->

** [!UICONTROL First or Last Touch Channel Report] **: Displays metrics showing data about a specific first-touch or last-touch channel. 在这些报表中，您可以划分渠道，显示每个渠道的详细信息。如果您启用了 AdLens，则可以在 Marketing Reports &amp; Analytics 渠道报表中看到分类信息。

** [!UICONTROL First or Last Touch Channel Detail Reports] **: Displays details such as page names and referrers, which is taken from the channel values you set up in the [!UICONTROL Set the channel's value to] option when configuring rules. 通过渠道详细报表可以仔细检查概述报表的渠道明细值。

有关在市场营销报告与分析中配置营销渠道的深度信息，请参阅[营销渠道帮助](https://marketing.adobe.com/resources/help/en_US/mchannel/index.html)系统。
