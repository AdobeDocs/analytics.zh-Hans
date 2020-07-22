---
title: 报表
description: 报表和Analytics为每个报表使用的维度和指标。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 1%

---


# 报表

报告和Analytics中的每个报告都使用专用维度和默认度量。 您可以更改每个报表中的度量，并根据需要添加细分。 以下列表提供了在每个报告中使用的维度。

>[!NOTE]
>
>根据您组织中的管理员进行的自定义，您的报告菜单可能会有所不同。 See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.

## 网站量度

包含通常使用日期范围呈趋势的报表。 还包含独特的报告，如推荐报告和实时报告。

* 我推荐的报告： 创建包含多个报表的仪表板，以便立即获得洞察。
* 关键指标： 一个报告，允许您一次最多趋势化五个指标。 默认 [情况下](/help/components/metrics/page-views.md)，趋 [势页](/help/components/metrics/visits.md)、 [访问](/help/components/metrics/unique-visitors.md) 和唯一视图。
* 页面视图: 随时间推 [动页面视图](/help/components/metrics/page-views.md) 量度的趋势。
* 访问： 随时间推 [移](/help/components/metrics/visits.md) ,“访问”量度的趋势。
* 访客: 随时间推 [移各种独特访客](/help/components/metrics/unique-visitors.md) 指标的趋势。
   * 独特访客: 仅对整个选定日期范围的访客计数一次。
   * 每小时唯一访客: 如果访客在所选日期范围的不同小时访问，则对其进行多次计数。
   * 每日独特访客: 如果访客在所选日期范围的不同日期访问，则对其进行多次计数。
   * 每周唯一访客: 如果访客在所选日期范围的不同周内访问，则对其进行多次计数。
   * 每月独特访客: 如果访客在所选日期范围的不同月份访问，则对其进行多次计数。
   * 季度独特访客: 如果访客在所选日期范围的不同季度访问，则对其进行多次计数。 季度为1-3月、4-6月、7-9月和10-12月。
   * 每年的唯一访客: 如果访客在所选日期范围的不同日历年访问，则对其进行多次计数。
* 每次访问所花费的时间： 使用每 [次访问所用的时间——分时段的](/help/components/dimensions/time-spent-per-visit.md) 维。
* 事件前的时间： 使用事件 [维之前的时间](/help/components/dimensions/time-prior-to-event.md) 。
* 购买： 包含有关基于购买的指标的报告。
   * 购买转化漏斗： 访问报 [表](/help/components/metrics/visits.md)、购 [物车](/help/components/metrics/carts.md)、订 [单、收](/help/components/metrics/orders.md)入 [、](/help/components/metrics/revenue.md)和漏斗中 [](/help/components/metrics/units.md) 的单位报表。 在Analysis Workspace中，使用流失可视化可实现类 [似的可视化](../analysis-workspace/visualizations/fallout/fallout-flow.md)。
   * 收入： 随时间推移 [衡量](/help/components/metrics/revenue.md) “收入”的趋势。
   * 订单： 随时间推移 [量度](/help/components/metrics/orders.md) “订单”趋势。
   * 单位： 随时间推 [移](/help/components/metrics/units.md) ，度量单位。
* 购物车： 包含有关购物车指标的报告。
   * 购物车转换漏斗： 报 [表实例](/help/components/metrics/instances.md)、车 [辆、](/help/components/metrics/carts.md)订单 [、](/help/components/metrics/checkouts.md)、 [、](/help/components/metrics/orders.md)[](/help/components/metrics/revenue.md) 和漏斗中的收入报表。
   * 购物车： 随时间推移 [量度](/help/components/metrics/carts.md) “购物车”。
   * 购物车视图: 随时间推移趋势 [度量购物车视图](/help/components/metrics/cart-views.md) 。
   * 购物车加货： 随时间推移趋 [势显示](/help/components/metrics/cart-additions.md) “购物车增加”。
   * 购物车删除： 随时间推移 [量度](/help/components/metrics/cart-removals.md) Cart删除。
   * 结帐： 随时间推移 [度量结](/help/components/metrics/checkouts.md) 算的趋势。
* 自定义事件: 包含与您的实施特定的 [自定义事件](/help/components/metrics/custom-events.md) 相关的所有报告。
* 机器人程序： 显示与机器人相关的报告。
   * 机器人程序： 显示最频繁访问您网站的机器人程序。 See [Bot rules](../../admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
   * 运行页面： 显示机器人程序点击最多的页面。
* 实时： 在数据收集后的数秒内显示某些维度和指标。 See [Real-time reports](/help/components/c-real-time-reporting/realtime.md) for more information.

## 站点内容

包含有关通常显示网站内容的维度的报表。 您可以将分类应用于其中一些报表。 应用分类意味着报表将成为包含源报表和分类报表的菜单。

* 页面： 使用页 [面维](/help/components/dimensions/page.md) 。
* 站点部分： 使用“ [站点](/help/components/dimensions/site-section.md) ”节维。
* 服务器： 使用服 [务器](/help/components/dimensions/server.md) 维。
* 链接： 包含使用链接跟踪的报表。
   * 退出链接： 使用退 [出链接](/help/components/dimensions/exit-link.md) 维。
   * 文件下载： 使用“下 [载链接](/help/components/dimensions/download-link.md) ”维。
   * 自定义链接： 使用自 [定义链接](/help/components/dimensions/custom-link.md) 维。
   * 找不到页面： 使用“ [找不到页面](/help/components/dimensions/pages-not-found.md) ”维。

## 移动设备

包含有关传统移动报表的报表。 这些报告将其数据基于用户代理字符串。 他们对各自的 [报告使](/help/components/dimensions/mobile-dimensions.md) 用各种移动维度。

* 设备： 使用移 [动设备](/help/components/dimensions/mobile-dimensions.md) 维度。
* 设备类型： 使用移 [动设备类型](/help/components/dimensions/mobile-dimensions.md) 维。
* 制造商： 使用移动 [制造商](/help/components/dimensions/mobile-dimensions.md) 维度。
* 屏幕大小： 使用“移 [动”屏幕大小](/help/components/dimensions/mobile-dimensions.md) 。
* 屏幕高度： 使用“移 [动”屏幕高度](/help/components/dimensions/mobile-dimensions.md) 。
* 屏幕宽度： 使用移 [动屏幕宽度](/help/components/dimensions/mobile-dimensions.md) 。
* Cookie支持： 使用移 [动Cookie支持](/help/components/dimensions/mobile-dimensions.md) 维。
* 图像支持： 使用移 [动图像支持](/help/components/dimensions/mobile-dimensions.md) 维度。
* 颜色深度： 使用移 [动颜色深度](/help/components/dimensions/mobile-dimensions.md) 。
* 音频支持： 使用移 [动音频支持](/help/components/dimensions/mobile-dimensions.md) 。
* 视频支持： 使用移 [动视频支持](/help/components/dimensions/mobile-dimensions.md) 维度。
* 操作系统（已弃用）: 使用移 [动操作系统（已弃用）](/help/components/dimensions/mobile-dimensions.md) 维。

## 路径

包含允许您查看访客路径数据的报表。

* 下一页流： 在顶部页面维度项目上使用流报表。 路径视图与实例 [类似](/help/components/metrics/instances.md)。 可以更改报告的维项。 Analysis Workspace中的类似报表可使用流 [可视化](../analysis-workspace/visualizations/c-flow/flow.md)。
* 下一页： 获取顶部页面维度项目，并向您显示访客转到的下一页。
* 上一页流： 在顶部页面维度项上使用流报表使用流可视化，可以获得Analysis Workspace中的类 [似报表](../analysis-workspace/visualizations/c-flow/flow.md)。
* 上一页： 获取顶部页面维度项目，并向您显示访客来自的上一页。
* 流失： 允许您按步骤选择页面维度项目，并显示遵循和未遵循该路径的人员比例。 Analysis Workspace中的类似报表可使用流失 [可视化](../analysis-workspace/visualizations/fallout/fallout-flow.md)。
* 完整路径： 将单个路径显示为维项。 退休Analysis Workspace; 请改 [用流](../analysis-workspace/visualizations/c-flow/flow.md) 。
* PathFinder: 提供多种类型的报告，用于分析路径(在Analysis Workspace中停用)。
* 路径长度： 使用访 [问深度](/help/components/dimensions/visit-depth.md) 维。
* 页面分析
   * 页面摘要： 获取顶部页面维度项目并显示趋势视图。 还显示该顶页维度项目的入口点、上一页、退出点和下一页。
   * 重新加载： 将页面 [维与](/help/components/dimensions/page.md) “重新加 [载](/help/components/metrics/reloads.md) ”度量一起使用。
   * 页面停留时间： 使用页 [面停留的时间——分时段的维](/help/components/dimensions/time-spent-on-page.md) 。
   * 点击页面： 获取顶部页面维度项目并显示在给定访问中访问该页面时点击次数。
* 进入和退出
   * 条目页面： 使用“ [条目页](/help/components/dimensions/entry-dimensions.md) ”维。
   * 原始条目页面： 使用“ [条目”页原始](/help/components/dimensions/entry-dimensions.md) 维。
   * 单页访问： 在应 [用Adobe](/help/components/dimensions/page.md) 提供的“单页访问”区段时，使用页面维度。
   * 退出页面： 使用退 [出页面](/help/components/dimensions/exit-dimensions.md) 维。

>[!NOTE]
>
>其他报告可显示在此文件夹中。 它们是其他维度，如prop，您在报告包设置 [下启用](../../admin/admin/c-traffic-variables/traffic-var.md) 了路径功能。

## 流量源

包含报告，可让您在访客到达您的网站前了解其来源。 除非在报表包设置下正确设置“ [内部URL过滤器](../../admin/admin/internal-url-filter-admin.md) ”，否则这些报表无法正常工作。

* 搜索关键字——全部： 使用“搜 [索关键字](/help/components/dimensions/search-keyword.md) ”维。
* 搜索关键字——付费： 使用搜 [索关键字——付费](/help/components/dimensions/search-keyword.md) 维度。
* 搜索关键字——自然： 使用搜 [索关键字——自然维](/help/components/dimensions/search-keyword.md) 度
* 搜索引擎——全部： 使用搜 [索引擎](/help/components/dimensions/search-engine.md) 维。
* 搜索引擎——付费： 使用搜 [索引擎——付费](/help/components/dimensions/search-engine.md) 维度。
* 搜索引擎——自然： 使用搜 [索引擎——自然维](/help/components/dimensions/search-engine.md) 度。
* 所有搜索页面排名： 使用“ [全部搜索”页排名](/help/components/dimensions/all-search-page-rank.md) 维。
* 引用域： 使用引 [用域维](/help/components/dimensions/referring-domain.md) 。
* 原始引用域： 使用原 [始引用域](/help/components/dimensions/original-referring-domain.md) 维
* 推荐人: 使用 [推荐人](/help/components/dimensions/referrer.md) 维。
* 推荐人类型： 使用 [推荐人类](/help/components/dimensions/referrer-type.md) 型维。

## 促销活动

包含主要围绕跟踪代 [码维度的](/help/components/dimensions/tracking-code.md) 报表。

* 活动转换漏斗： 漏斗报表中 [的点进](/help/components/metrics/checkouts.md)、结 [帐](/help/components/metrics/orders.md)、 [订单](/help/components/metrics/revenue.md) 和收入。 点进率度量与跟踪代码维 [度的](/help/components/metrics/instances.md) 上下文中的实例 [度量类似](/help/components/dimensions/tracking-code.md) 。 在Analysis Workspace中，使用流失可视化可实现类 [似的可视化](../analysis-workspace/visualizations/fallout/fallout-flow.md)。
* 跟踪代码： 使用跟 [踪代码](/help/components/dimensions/tracking-code.md) 维。

## 产品

包含主要围绕产品维 [度的](/help/components/dimensions/product.md) 报表。

* 产品转换漏斗： 报 [告视图](/help/components/metrics/product-views.md)、购 [物车加货](/help/components/metrics/cart-additions.md)、 [核对、](/help/components/metrics/checkouts.md)、 [](/help/components/metrics/orders.md)[](/help/components/metrics/units.md)[](/help/components/metrics/revenue.md) 、、、单、和中的和漏斗中的收入报告。 在Analysis Workspace中，使用流失可视化可实现类 [似的可视化](../analysis-workspace/visualizations/fallout/fallout-flow.md)。
* 产品： 使用 [产品](/help/components/dimensions/product.md) 维。
* 交叉销售： 显示通常一起销售(在Analysis Workspace中报废)的产品。
* 类别: 使用 [类别](/help/components/dimensions/category.md) 维。

## 访客维系

包含有关返回您网站的访客的报告。

* 返回频率： 使用“ [返回频率](/help/components/dimensions/return-frequency.md) ”维。
* 回访： 使用Adobe [提供](/help/components/metrics/visits.md) 的“回访”区段，使访问量度随时间变化的趋势。
* 访问号： 使用访 [问号](/help/components/dimensions/visit-number.md) 维。
* 销售周期： 用于与购买相关报告的文件夹。
   * 客户忠诚度： 使用客 [户忠诚度](/help/components/dimensions/customer-loyalty.md) 维度。
   * 首次购买前的天数： 使用第 [一次购买维度前](/help/components/dimensions/days-before-first-purchase.md) 的天数。
   * 上次购买后的天数： 使用自上 [次购买以来的天](/help/components/dimensions/days-since-last-purchase.md) 数维。
   * 每日独特客户： 趋势 [随着时间推移](/help/components/metrics/unique-visitors.md) ,Adobe提供的“购买者”细分会不断推出每日独特访客。
   * 每周唯一客户： 趋 [势通过应用](/help/components/metrics/unique-visitors.md) Adobe提供的“购买者”细分，逐周发布独特访客。
   * 每月唯一客户： 趋势 [随着时间推移](/help/components/metrics/unique-visitors.md) ,Adobe提供的“购买者”细分会不断应用每月独特访客。
   * 每季度唯一客户： 趋 [势通过应用](/help/components/metrics/unique-visitors.md) Adobe提供的“购买者”细分，逐季度独特访客。 季度为1-3月、4-6月、7-9月和10-12月。
   * 每年唯一客户： 趋 [势通过应用](/help/components/metrics/unique-visitors.md) Adobe提供的“购买者”细分，逐年提供独特访客。

## 访客资料

包含有关访问您网站的人员的报告。

* 地理分割： 有关全球点击网站的位置的报告。
   * 国家／地区： 使用国 [家](/help/components/dimensions/countries.md) 维。
   * 地区： 使用“ [区域](/help/components/dimensions/regions.md) ”尺寸。
   * 城市： 使用“城 [市](/help/components/dimensions/cities.md) ”维度。
   * 美国州： 使用 [美国](/help/components/dimensions/us-states.md) 。
   * 美国DMA: 使用 [美国DMA](/help/components/dimensions/us-dma.md) 维。
* 语言： 使用“ [语言](/help/components/dimensions/language.md) ”维。
* 时区： 使用时区维(在Analysis Workspace中停用)。 维项是点击的GMT偏移。
* 域： 使用 [域](/help/components/dimensions/domain.md) 维。
* 顶级域： 使用顶级域维(在Analysis Workspace中停用)。 它将域 [维分组](/help/components/dimensions/domain.md) 为更高级别的类别，通常按域的国家／地区。
* 技术： 包含访客用于访问站点的报告的文件夹。
   * 浏览器： 使用浏 [览器](/help/components/dimensions/browser.md) 维。
   * 浏览器类型： 使用浏 [览器类型](/help/components/dimensions/browser-type.md) 维。
   * 浏览器宽度： 使用浏 [览器宽度——分时段](/help/components/dimensions/browser-width.md) 尺寸。
   * 浏览器高度： 使用浏 [览器高度——分时段的](/help/components/dimensions/browser-height.md) 维度。
   * 操作系统： 使用操 [作系统](/help/components/dimensions/operating-systems.md) 维。
   * 操作系统类型： 使用操 [作系统类型](/help/components/dimensions/operating-system-types.md) 维。
   * 显示器颜色深度： 使用“颜 [色深度](/help/components/dimensions/color-depth.md) ”尺寸。
   * 显示器分辨率： 使用“监 [视器](/help/components/dimensions/monitor-resolution.md) ”分辨率。
   * Java: 使用启 [用Java](/help/components/dimensions/java-enabled.md) 的维。
   * JavaScript: 使用启用JavaScript的维(在Analysis Workspace中停用)。 维项目为“已启用”、“已禁用”或“未知”，具体取决于浏览器是否启用了JavaScript。
   * JavaScript版本： 使用JavaScript版本维(在Analysis Workspace中停用)。 维度项显示浏览器使用的JavaScript版本。
   * Cookie: 使用Cookie [支持维](/help/components/dimensions/cookie-support.md) 。
   * 连接类型： 使用“ [连接类型](/help/components/dimensions/connection-type.md) ”维。
   * 移动运营商： 使用移 [动运营商](/help/components/dimensions/mobile-dimensions.md) 维度。
* 访客状态： 使用状态维(在Analysis Workspace中停用)。 维项来自变 [`state`](../../implement/vars/page-vars/state.md) 量。
* 访客邮政编码： 使用 [邮政编码](/help/components/dimensions/zip-code.md) 。

## 自定义转换

包含特定于您的实施的报告。 自定义转换报 [告使用](/help/components/dimensions/evar.md) eVar作为维度。

## 自定义流量

包含特定于您的实施的报告。 自定义流量报 [表使用](/help/components/dimensions/prop.md) prop作为维。

## 营销渠道

包含涉及营销 [渠道的报表](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。

* 渠道概述报告： 特定于报告和Analytics的自定义报告。 将营销渠道用作维度项目，并使用第一次或最后一次触碰归因来衡量。
* 首次触摸渠道: 使用“ [首次触摸渠道](/help/components/dimensions/first-touch-channel.md) ”尺寸。
* 首次触摸渠道详细信息： 使用“首 [次触摸渠道”详细信息](/help/components/dimensions/first-touch-detail.md) 。
* 上次触摸渠道: 使用“ [上次触摸渠道](/help/components/dimensions/last-touch-channel.md) ”维。
* 上次触摸渠道详细信息： 使用上次 [触摸渠道详细信息](/help/components/dimensions/last-touch-detail.md) 维。

## 书签

包含已添加书签的报表。 See [Bookmarks](bookmarks.md) for more information.

## 功能板

包含您创建的仪表板。 See [Dashboards](dashboard.md) for more information.

## 目标

包含您创建的目标。 See [Targets](targets.md) for more information.

>[!NOTE]
>
>如果在此帮助页面上找不到您的报告，则管理员可能会重命名或调整文件夹。 See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.
