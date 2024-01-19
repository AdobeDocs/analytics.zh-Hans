---
title: 报表
description: Reports & Analytics 用于每个报表的维度和量度。
feature: Reports & Analytics Basics
role: User, Admin
exl-id: e3c23d17-fc4b-479e-9c48-6f27ef0de4e3
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 100%

---

# 报表

{{ra-eol}}

Reports &amp; Analytics 的每个报表会使用专用维度和量度。您可以根据需要更改每个报表中的量度并添加划分。以下列表提供了在每个报表中使用的维度。

>[!NOTE]
>
>您的报表菜单看上去可能会有所不同，具体取决于贵组织管理员所做的自定义设置。请参阅管理员用户指南中的[菜单自定义](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md)。

## 网站量度

包含通常情况下使用日期范围来显示某种趋势的报表。此外，还包含独特报表，例如推荐报表和实时报表。

* 我的推荐报表：创建包含多个缩图报表的功能板，以便即时获得洞察。
* 关键量度：允许一次显示最多五个量度的趋势的报表。默认情况下，显示[页面查看次数](/help/components/metrics/page-views.md)、[访问次数](/help/components/metrics/visits.md)和[独特访客数](/help/components/metrics/unique-visitors.md)的趋势。
* 页面查看次数：显示[页面查看次数](/help/components/metrics/page-views.md)量度随时间变化的趋势。
* 访问次数：显示[访问次数](/help/components/metrics/visits.md)量度随时间变化的趋势。
* 访客数：显示各种[独特访客](/help/components/metrics/unique-visitors.md)量度随时间变化的趋势。
   * 独特访客数：对整个选定日期范围的访客仅计数一次。
   * 每小时独特访客数：如果访客在选定日期范围的不同时段访问，则对其进行多次计数。
   * 每日独特访客数：如果访客在选定日期范围的不同日期访问，则对其进行多次计数。
   * 每周独特访客数：如果访客在选定日期范围的不同周内访问，则对其进行多次计数。
   * 每月独特访客数：如果访客在选定日期范围的不同月份访问，则对其进行多次计数。
   * 每季度独特访客数：如果访客在选定日期范围的不同季度访问，则对其进行多次计数。季度为 1-3 月、4-6 月、7-9 月以及 10-12 月。
   * 每年独特访客数：如果访客在选定日期范围的不同日历年访问，则对其进行多次计数。
* 每次访问逗留时间：使用[每次访问逗留时间 - 分段统计](/help/components/dimensions/time-spent-per-visit.md)维度。
* 事件前耗费时间：使用[事件前耗费时间](/help/components/dimensions/time-prior-to-event.md)维度。
* 购买：包含有关购买量度的报表。
   * 购买转化漏斗：在漏斗报表中报告[访问次数](/help/components/metrics/visits.md)、[购物车](/help/components/metrics/carts.md)、[订单](/help/components/metrics/orders.md)、[收入](/help/components/metrics/revenue.md)以及[单位](/help/components/metrics/units.md)。在 Analysis Workspace 中使用[流失可视化图表](../analysis-workspace/visualizations/fallout/fallout-flow.md)可获得类似的可视化图表。
   * 收入：显示[收入](/help/components/metrics/revenue.md)量度随时间变化的趋势。
   * 订单：显示[订单](/help/components/metrics/orders.md)量度随时间变化的趋势。
   * 单位：显示[单位](/help/components/metrics/units.md)量度随时间变化的趋势。
* 购物车：包含有关购物车量度的报表。
   * 购物车转换漏斗：在漏斗报表中报告[实例](/help/components/metrics/instances.md)、[购物车](/help/components/metrics/carts.md)、[结账](/help/components/metrics/checkouts.md)、[订单](/help/components/metrics/orders.md)以及[收入](/help/components/metrics/revenue.md)。
   * 购物车：显示[购物车](/help/components/metrics/carts.md)量度随时间变化的趋势。
   * 购物车查看次数：显示[购物车查看次数](/help/components/metrics/cart-views.md)量度随时间变化的趋势。
   * 购物车添加：显示[购物车添加](/help/components/metrics/cart-additions.md)量度随时间变化的趋势。
   * 购物车移除：显示[购物车移除](/help/components/metrics/cart-removals.md)量度随时间变化的趋势。
   * 结帐：显示[结账](/help/components/metrics/checkouts.md)量度随时间变化的趋势。
* 自定义事件：包含有关您的具体实施的[自定义事件](/help/components/metrics/custom-events.md)的所有报表。
* 机器人程序：显示与机器人程序相关的报表。
   * 机器人程序：显示最频繁地访问您网站的机器人程序。请参阅管理员用户指南中的[机器人程序规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)。
   * 机器人程序页面：显示机器人程序点击最多的页面。
* 实时：在数据收集后的数秒内显示某些维度和量度。有关更多信息，请参阅[实时报表](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)。

## 网站内容

包含有关通常情况下显示网站内容的维度的报表。您可以将分类应用于其中一些报表。应用分类意味着报表将成为包含源报表和分类报表的菜单。

* 页面：使用[页面](/help/components/dimensions/page.md)维度。
* 网站区域：使用[网站区域](/help/components/dimensions/site-section.md)维度。
* 服务器：使用[服务器](/help/components/dimensions/server.md)维度。
* 链接：包含使用链接跟踪的报表。
   * 退出链接：使用[退出链接](/help/components/dimensions/exit-link.md)维度。
   * 文件下载：使用[下载链接](/help/components/dimensions/download-link.md)维度。
   * 自定义链接：使用[自定义链接](/help/components/dimensions/custom-link.md)维度。
   * 未找到页面：使用[未找到页面](/help/components/dimensions/pages-not-found.md)维度。

## 移动设备

包含有关旧版移动设备报表的报表。这些报表的数据以用户代理字符串为基础。他们对各自的报表使用各种[移动设备维度](/help/components/dimensions/mobile-dimensions.md)。

* 设备：使用[移动设备](/help/components/dimensions/mobile-dimensions.md)维度。
* 设备类型：使用[移动设备类型](/help/components/dimensions/mobile-dimensions.md)维度。
* 制造商：使用[移动设备制造商](/help/components/dimensions/mobile-dimensions.md)维度。
* 屏幕大小：使用[移动设备屏幕大小](/help/components/dimensions/mobile-dimensions.md)维度。
* 屏幕高度：使用[移动设备屏幕高度](/help/components/dimensions/mobile-dimensions.md)维度。
* 屏幕宽度：使用[移动设备屏幕宽度](/help/components/dimensions/mobile-dimensions.md)维度。
* Cookie 支持：使用[移动设备 Cookie 支持](/help/components/dimensions/mobile-dimensions.md)维度。
* 图像支持：使用[移动设备图像支持](/help/components/dimensions/mobile-dimensions.md)维度。
* 颜色深度：使用[移动设备颜色深度](/help/components/dimensions/mobile-dimensions.md)维度。
* 音频支持：使用[移动设备音频支持](/help/components/dimensions/mobile-dimensions.md)维度。
* 视频支持：使用[移动设备视频支持](/help/components/dimensions/mobile-dimensions.md)维度。
* 操作系统（已弃用）：使用[移动设备操作系统（已弃用）](/help/components/dimensions/mobile-dimensions.md)维度。

## 路径

包含允许您查看访客路径数据的报表。

* 下一页面流量：对热门页面维度项目使用流量报表。路径视图与[实例](/help/components/metrics/instances.md)类似。您可以更改报告的维度项目。在 Analysis Workspace 中使用[流量可视化图表](../analysis-workspace/visualizations/c-flow/flow.md)可获得类似的报表。
* 下一页：采用热门页面维度项目，并显示访客转到的后续页面。
* 上一页面流量：对热门页面维度项目使用流量报表。在 Analysis Workspace 中使用[流量可视化图表](../analysis-workspace/visualizations/c-flow/flow.md)可获得类似的报表。
* 上一页：采用热门页面维度项目，并显示访客来自的先前页面。
* 流失：允许您在步骤中选择页面维度项目，并显示遵循和未遵循该路径的人员比例。在 Analysis Workspace 中使用[流失可视化图表](../analysis-workspace/visualizations/fallout/fallout-flow.md)可获得类似的报表。
* 完整路径：将单个路径显示为维度项目。在 Analysis Workspace 中已停用，请改用[流量可视化图表](../analysis-workspace/visualizations/c-flow/flow.md)。
* PathFinder：提供多种类型的报表，用于分析路径（在 Analysis Workspace 中已停用）。
* 路径长度：使用[访问深度](/help/components/dimensions/visit-depth.md)维度。
* 页面分析
   * 页面概要：采用热门页面维度项目并显示趋势视图。此外，还显示该热门页面维度项目的登入点、上一页、退出点和下一页。
   * 重新加载：将[页面](/help/components/dimensions/page.md)维度与[重新加载](/help/components/metrics/reloads.md)量度一起使用。
   * 页面逗留时间：使用[页面逗留时间 - 分段统计](/help/components/dimensions/time-spent-on-page.md)维度。
   * 页面点击次数：采用热门页面维度项目并显示在给定访问中经过多少次点击后才转到该页面。
* 登录和退出
   * 进入页面：使用[登入页面](/help/components/dimensions/entry-dimensions.md)维度。
   * 原始登入页面：使用[原始登入页面](/help/components/dimensions/entry-dimensions.md)维度。
   * 单页访问数：在应用 Adobe 提供的“单页访问数”区段的情况下，使用[页面](/help/components/dimensions/page.md)维度。
   * 退出页面：使用[退出页面](/help/components/dimensions/exit-dimensions.md)维度。

>[!NOTE]
>
>其他报表可能会显示在此文件夹中。还有其他维度，例如 prop，您可以在报表包设置下[启用路径](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)。

## 流量源

包含提供关于访客在访问您的网站前来自哪里的洞察信息的报表。除非在报表包设置下正确设置[内部 URL 过滤器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)，否则这些报表无法正常工作。

* 搜索关键词 - 全部：使用[搜索关键词](/help/components/dimensions/search-keyword.md)维度。
* 搜索关键词 - 付费：使用[搜索关键词 - 付费](/help/components/dimensions/search-keyword.md)维度。
* 搜索关键词 - 免费：使用[搜索关键词 - 免费](/help/components/dimensions/search-keyword.md)维度。
* 搜索引擎 - 全部：使用[搜索引擎](/help/components/dimensions/search-engine.md)维度。
* 搜索引擎 - 付费：使用[搜索引擎 - 付费](/help/components/dimensions/search-engine.md)维度。
* 搜索引擎 - 免费：使用[搜索引擎 - 免费费](/help/components/dimensions/search-engine.md)维度。
* 所有搜索页面排名：使用[所有搜索页面排名](/help/components/dimensions/all-search-page-rank.md)维度。
* 反向链接域：使用[反向链接域](/help/components/dimensions/referring-domain.md)维度。
* 原始反向链接域：使用[原始反向链接域](/help/components/dimensions/original-referring-domain.md)维度。
* 反向链接：使用[反向链接](/help/components/dimensions/referrer.md)维度。
* 反向链接类型：使用[反向链接类型](/help/components/dimensions/referrer-type.md)维度。

## 促销活动

包含主要有关[跟踪代码](/help/components/dimensions/tracking-code.md)维度的报表。

* 促销活动转换漏斗：在漏斗报表中报告点进次数、[结账](/help/components/metrics/checkouts.md)、[订单](/help/components/metrics/orders.md)以及[收入](/help/components/metrics/revenue.md)。在[跟踪代码](/help/components/dimensions/tracking-code.md)维度的上下文中，点进次数量度类似于[实例](/help/components/metrics/instances.md)度量。在 Analysis Workspace 中使用[流失可视化图表](../analysis-workspace/visualizations/fallout/fallout-flow.md)可获得类似的可视化图表。
* 跟踪代码：使用[跟踪代码](/help/components/dimensions/tracking-code.md)维度。

## 产品

包含主要有关[产品](/help/components/dimensions/product.md)维度的报表。

* 产品转换漏斗：在漏斗报表中报告[产品查看次数](/help/components/metrics/product-views.md)、[购物车添加](/help/components/metrics/cart-additions.md)、[结账](/help/components/metrics/checkouts.md)、[订单](/help/components/metrics/orders.md)、[单位](/help/components/metrics/units.md)以及[收入](/help/components/metrics/revenue.md)。在 Analysis Workspace 中使用[流失可视化图表](../analysis-workspace/visualizations/fallout/fallout-flow.md)可获得类似的可视化图表。
* 产品：使用[产品](/help/components/dimensions/product.md)维度。
* 交叉销售：显示通常一起销售的产品（在 Analysis Workspace 中已停用）。
* 类别：使用[类别](/help/components/dimensions/category.md)维度。

## 访客维系

包含有关回访您网站的访客的报表。

* 回访频度：使用[回访频度](/help/components/dimensions/return-frequency.md)维度。
* 回访数：在应用 Adobe 提供的“回访访问数”区段的情况下，显示[回访数](/help/components/metrics/visits.md)量度随时间变化的趋势。
* 访问编号：使用[访问编号](/help/components/dimensions/visit-number.md)维度。
* 销售周期：用于与购买相关报表的文件夹。
   * 客户忠诚度：使用[客户忠诚度](/help/components/dimensions/customer-loyalty.md)维度。
   * 首次购买前的天数：使用[首次购买前的天数](/help/components/dimensions/days-before-first-purchase.md)维度。
   * 上次购买后的天数：使用[上次购买后的天数](/help/components/dimensions/days-since-last-purchase.md)维度。
   * 每日独特访客：在应用 Adobe 提供的“购物者”区段的情况下，显示[每日独特访客](/help/components/metrics/unique-visitors.md)量度随时间变化的趋势。
   * 每周独特访客：在应用 Adobe 提供的“购物者”区段的情况下，显示[每周独特访客](/help/components/metrics/unique-visitors.md)量度随时间变化的趋势。
   * 每月独特访客：在应用 Adobe 提供的“购物者”区段的情况下，显示[每月独特访客](/help/components/metrics/unique-visitors.md)量度随时间变化的趋势。
   * 每季度独特访客：在应用 Adobe 提供的“购物者”区段的情况下，显示[每季度独特访客](/help/components/metrics/unique-visitors.md)量度随时间变化的趋势。季度为 1-3 月、4-6 月、7-9 月以及 10-12 月。
   * 每年独特访客：在应用 Adobe 提供的“购物者”区段的情况下，显示[每年独特访客](/help/components/metrics/unique-visitors.md)量度随时间变化的趋势。

## 访客资料

包含有关访问您网站的人员的报表。

* 地理划分：有关点击您网站的访客所处的全球位置的报表。
   * 国家/地区：使用[国家/地区](/help/components/dimensions/countries.md)维度。
   * 区域：使用[区域](/help/components/dimensions/regions.md)维度。
   * 城市：使用[城市](/help/components/dimensions/cities.md)维度。
   * 美国州：使用[美国州](/help/components/dimensions/us-states.md)维度。
   * 美国 DMA：使用[美国 DMA](/help/components/dimensions/us-dma.md) 维度。
* 语言：使用[语言](/help/components/dimensions/language.md)维度。
* 时区：使用时区维度（在 Analysis Workspace 中已停用）。维度项目是点击的 GMT 偏移。
* 域：使用[域](/help/components/dimensions/domain.md)维度。
* 顶级域：使用顶级域维度（在 Analysis Workspace 中已停用）。它将[域](/help/components/dimensions/domain.md)维度分组为更高级别的类别，通常按域的国家/地区来分组。
* 技术：包含访客用于访问网站的技术报表的文件夹。
   * 浏览器：使用[浏览器](/help/components/dimensions/browser.md)维度。
   * 浏览器类型：使用[浏览器类型](/help/components/dimensions/browser-type.md)维度。
   * 浏览器宽度：使用[浏览器宽度 - 分段统计](/help/components/dimensions/browser-width.md)维度。
   * 浏览器高度：使用[浏览器高度 - 分段统计](/help/components/dimensions/browser-height.md)维度。
   * 操作系统：使用[操作系统](/help/components/dimensions/operating-systems.md)维度。
   * 操作系统类型：使用[操作系统类型](/help/components/dimensions/operating-system-types.md)维度。
   * 显示器颜色深度：使用[颜色深度深度](/help/components/dimensions/color-depth.md)维度。
   * 显示器分辨率：使用[显示器分辨率](/help/components/dimensions/monitor-resolution.md)维度。
   * Java：使用[启用 Java](/help/components/dimensions/java-enabled.md) 维度。
   * JavaScript：使用“启用 JavaScript”维度（在 Analysis Workspace 中已停用）。维度项目为“已启用”、“已禁用”或“未知”，具体取决于浏览器是否启用了 JavaScript。
   * JavaScript 版本：使用 JavaScript 版本维度（在 Analysis Workspace 中已停用）。维度项目显示浏览器使用的 JavaScript 版本。
   * Cookie：使用 [Cookie 支持](/help/components/dimensions/cookie-support.md)维度。
   * 连接类型：使用[连接类型](/help/components/dimensions/connection-type.md)维度。
   * 移动运营商：使用[移动运营商](/help/components/dimensions/mobile-dimensions.md)维度。
* 访客状态：使用状态维度（在 Analysis Workspace 中已停用）。维度项目源自 [`state`](../../implement/vars/page-vars/state.md) 变量。
* 访客邮政编码：使用[邮政编码](/help/components/dimensions/zip-code.md)维度。

## 自定义转换

包含特定于您的实施的报表。自定义转换报表使用 [eVar](/help/components/dimensions/evar.md) 作为维度。

## 自定义流量

包含特定于您的实施的报表。自定义转换报表使用 [prop](/help/components/dimensions/prop.md) 作为维度。

## 营销渠道

包含涉及[营销渠道](/help/components/c-marketing-channels/c-getting-started-mchannel.md)的报表。

* 渠道概述报表：特定于 Reports &amp; Analytics 的自定义报表。将营销渠道用作维度项目，量度使用首次联系或最近联系归因。
* 首次接触渠道：使用[首次接触渠道](/help/components/dimensions/first-touch-channel.md)维度。
* 首次接触渠道详细信息：使用[首次接触](/help/components/dimensions/first-touch-detail.md)维度。
* 最后接触渠道：使用[最后接触渠道](/help/components/dimensions/last-touch-channel.md)维度。
* 最后接触渠道详细信息：使用[最后接触](/help/components/dimensions/last-touch-detail.md)维度。

## 书签

包含已添加书签的报表。有关更多信息，请参阅[书签](bookmarks.md)。

## 功能板

包含您已创建的功能板。有关更多信息，请参阅[功能板](dashboard.md)。

## 目标

包含您已创建的目标。有关更多信息，请参阅[目标](targets.md)。

>[!NOTE]
>
>如果在此帮助页面上找不到您的报表，则可能是因为管理员重命名或调整了文件夹。请参阅管理员用户指南中的[菜单自定义](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md)。
