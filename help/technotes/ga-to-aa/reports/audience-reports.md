---
title: Adobe Analytics中的受众报告
description: 了解如何使用Analysis Workspace创建基于受众的报告。
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# 受众报告

受众报告显示有关访问您网站的人员类型的信息。

本页假定用户对使用Analysis Workspace有基本知识。 如 [果您还不熟悉Adobe Analytics中的工具](create-report.md) ，请参阅在Analysis Workspace中为Google Analytics用户创建基本报告。

## 活动用户

活动用户显示您的站点在过去1、7、14或28天内的累计用户数。 虽然Adobe没有在Google Analytics中使用的确切计算，但您可以使用度量“唯一访客”来根据选定的日期范围查看您网站的重复用户计数。

要获取唯一访客的线图，请执行以下操作：

1. 单击左侧的可视化图标，然后将线可视化拖动到空的自由格式表上方的工作区上。
2. 单击左侧的组件图标，然后将“唯一访客 **”量度拖动到标有“将一个量度放在此处** ”的较小空间中。
3. 如果需要不同的粒度，请拖动所需的日期范围( **例如** Day、 **Week**、 **Month**&#x200B;等)在现有日期维标题的顶部。

有关Adobe [如何计算独特访客的详细信息](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) ，请参阅组件用户指南中的独特访客。

## 生命周期值

终身价值是一项功能，它需要在两个平台上进行额外的专门实施。 Adobe建议与实施顾问合作获取此数据。

## 同类群组分析

同期群分析显示同一用户返回网站的频率。

要创建同期群表，请执行以下操作：

1. 单击左侧的“可视化”图标，然后将“同期群表”可视化拖到工作区上。
2. 单击左侧的组件图标，然后将访问量度拖 **动到** “包含条件”和“返回条件”上。
3. 单击生成。

有关对 [](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) 队列可视化进行其他自定义的详细信息，请参阅Analysis Workspace用户指南中的队列分析。

## 受众

Google Analytics中的“受众”报表需要设置受众。 受众还需要通过Adobe Audience manager在Adobe中进行配置。 有关详细信息，请参阅Adobe Audience manager用户指南。

## 用户浏览器

用户浏览器报告允许分析人员通过匿名标识符查看个人访问。 Adobe不会在数据馈送之外显示后端标识符，这些数据馈送是数据的命中级原始导出。

* 如果Analysis Workspace中需要此数据，则可以与实施顾问合作，将匿名唯一标识符cookie值传递到eVar。 请注意，这仅适用于每月唯一访问者少于100万的较小实施。
* 如果数据馈送中需要此数据，则连接列 `visid_high` 和 `visid_low` 是识别唯一访客的最常用方法。 了解有关数据 [源的更多信息](/help/export/analytics-data-feed/c-getstarted/data-feed-overview.md) ，请参阅导出用户指南。

## 人口统计和兴趣报告

人口统计和兴趣数据提供有关网站用户年龄、性别和兴趣的信息。 谷歌通过其跨站点跟踪功能收集这些数据。

Adobe不会自动收集人口统计和兴趣数据。 但是，如果您的组织获得此数据，您可以使用Adobe Experience Cloud Platform中的“客户属性”（一项功能）。 它允许完全控制按属性组织数据，并且不仅限于人口统计或兴趣。

有关详细信息，请参阅客户属性帮助。

## 地理——语言

地理语言报告按访客浏览器中的语言设置显示网站流量。

要创建语言报告，请执行以下操作：

1. 在“组件”菜单中，找到“语 **言** ”维并将其拖动到标有“将维放在此处”的大型自由格式表区域。
2. 将所需的度量与自动创建的“发生次数”度量一起拖 **动到工** 作区。 有关如何获 [取各个度量的详细信息](common-metrics.md) ，请参阅度量转换指南。

有关详细信息， [请参阅](/help/components/c-variables/dimensionslist/reports-languages.md) “组件”用户指南中的“语言”维。

## 地理位置

地理位置报告提供全球地图视图，按国家／地区划分数据。

要创建地理位置报表，请执行以下操作：

1. 单击左侧的可视化图标，然后将映射可视化拖到空的自由格式表上方的工作区上。
2. 单击左侧的组件图标，然后将唯一访客 **量度拖入标有“添加量度** ”的空间。
3. 单击生成。

如果除了地图之外还希望使用表格：

1. 在“组件”菜单中，找到“国 **家** ”维并将其拖动到标有“将维放在此处”的大型自由格式表区域。
2. 将所需的度量与自动创建的“发生次数”度量一起拖 **动到工** 作区。 有关如何获 [取各个度量的详细信息](common-metrics.md) ，请参阅度量转换指南。

有关详 [细信息](/help/components/c-variables/dimensionslist/reports-geosegmentation.md) ，请参阅组件用户指南中的地域划分维度。

## 行为——新增与退回

新会话与回访报告可简化第一个会话（新访问）与后续会话（回访）的视图。

要创建新的与回访报告，请执行以下操作：

1. 在组件菜单中，找到“ **首次访问”区段** ，并将其拖动到标有“将维放在此处”的大型自由格式表区域。 请注意， **首次访问是一个细分** ，而Workspace通常使用维来表示行。
2. 找到回 **访区段** ，并将其拖动到区段行标题的顶部。 这会将区段添加为“首次访问”下的维度，从而便于比较。
3. 将所需的度量与自动创建的“发生次数”度量一起拖 **动到工** 作区。 有关如何获 [取各个度量的详细信息](common-metrics.md) ，请参阅度量转换指南。

如果还需要线图：

1. 单击左侧的可视化图标，然后将线条可视化拖动到自由格式表上方的工作区上
2. 在自由格式表中的每行上使用Ctrl+单击(Windows)或Cmd+单击(Mac)可高亮显示它们。 这允许在线可视化中显示这两种趋势。
3. 单击线可视化左上角的小圆点，然后单击复选框“锁定选择”。

## 行为——频率和新近度

频率和最近度报告大约等于Analysis Workspace中 **的“访问次数** ”维度。

1. 在组件菜单中，找到“访 **问次数** ”维并将其拖动到标有“将维放在此处”的大型自由格式表区域。
2. 将所需的度量与自动创建的“发生次数”度量一起拖 **动到工** 作区。 有关如何获 [取各个度量的详细信息](common-metrics.md) ，请参阅度量转换指南。

有关详细 [信息，请参阅组件](/help/components/c-variables/dimensionslist/reports-visitor-number.md) 用户指南中的访问次数维。

## 行为——参与

参与报告大约等于“每次访 **问所花费的时间——分时段** ”维。

1. 在组件菜单中，找到每次访 **问的停留时间——存储段维** ，并将其拖动到标有“将维放在此处”的大型自由格式表区域。
2. 将所需的度量与自动创建的“发生次数”度量一起拖 **动到工** 作区。 有关如何获 [取各个度量的详细信息](common-metrics.md) ，请参阅度量转换指南。

有关详细 [信息，请参阅组件用户指南中的](/help/components/c-variables/dimensionslist/reports-time-spent-per-visit.md) “每次访问所花费的时间”维。

## 技术——浏览器和操作系统

浏览器和操作系统报告中有多个主要维。

* 浏览器 **主维度** （在Analysis Workspace中也可以作为维度使用）。
* Analysis Workspace **中也提供Operating System** Primary维度作为维。
* “屏 **幕分辨率** ”主要维度在Analysis Workspace中可用作“监视器 **分辨率** ”维度。
* Analysis Workspace **中提供了“屏幕颜色** ”(Screen Colors **)主维，作为“颜** 色深度”(Color Depth)维。
* Adobe **Analytics中不提供Flash Version** primary维度，但eVar可以根据需要收集此数据。

1. 在组件菜单中，找到上面注明的所需维，并将其拖动到标有“将维放在此处”的大型自由格式表区域。
2. 将所需的度量与自动创建的“发生次数”度量一起拖 **动到工** 作区。 有关如何获 [取各个度量的详细信息](common-metrics.md) ，请参阅度量转换指南。

有关各个维的详细信息，请参阅组件用户指南中的以下页面：

* [浏览器](/help/components/c-variables/dimensionslist/reports-browsers.md)
* [操作系统](/help/components/c-variables/dimensionslist/reports-operating-system.md)
* [监视器分辨率](/help/components/c-variables/dimensionslist/reports-technology.md)
* [颜色深度](/help/components/c-variables/dimensionslist/reports-color-depth.md)

## 技术——网络

网络报告大致等于“域 **”维** 。

1. 在组件菜单中，找到 **域维** ，并将其拖动到标有“将维放在此处”的大型自由格式表区域。
2. 将所需的度量与自动创建的“发生次数”度量一起拖 **动到工** 作区。 有关如何获 [取各个度量的详细信息](common-metrics.md) ，请参阅度量转换指南。

有关详细 [信息](/help/components/c-variables/dimensionslist/reports-domains.md) ，请参阅组件用户指南中的域维。

## 移动——概述

移动设备概述报告大致等于“移 **动设备类型** ”维。 请注意，“其他”值等同于桌面流量。

1. 在组件菜单中，找到“移 **动设备类型** ”维并将其拖动到标有“将维放在此处”的大型自由格式表区域。
2. 将所需的度量与自动创建的“发生次数”度量一起拖 **动到工** 作区。 有关如何获 [取各个度量的详细信息](common-metrics.md) ，请参阅度量转换指南。

有关详细 [信息，请参阅组件用户指南中的](/help/components/c-variables/dimensionslist/reports-device-types.md) “移动设备类型”维。

## 移动——设备

移动设备报告与移动设备维度 **大致相同** 。

1. 在组件菜单中，找到移 **动设备维度** ，并将其拖动到标有“将维度放在此处”的大型自由格式表区域。
2. 将所需的度量与自动创建的“发生次数”度量一起拖 **动到工** 作区。 有关如何获 [取各个度量的详细信息](common-metrics.md) ，请参阅度量转换指南。

有关详细 [信息，请参阅组件用户指南中的](/help/components/c-variables/dimensionslist/reports-devices.md) “移动设备”维度。

## 自定义

自定义报告是按实施情况定义的。 与贵组织的Analytics管理员和／或实施顾问合作解释这些报告。 通常，组织会维护一 [个解决方案设计文档](/help/implement/prepare/solution-design.md) ，以跟踪自定义变量值及其填充方式。

## 基准测试

基准测试报告允许您查看数据方面与行业平均值的比较情况。 Adobe目前不在客户之间共享基准数据。

## 用户流

流报告在两种平台上均可用。 要创建流报表，请执行以下操作：

1. 单击左侧的可视化图标，然后将流可视化拖到自由格式表上方的工作区上
2. 找到页 **面维** ，然后单击箭头图标以显示页面值。 尺寸值为黄色。
3. 找到要开始的所需页面值，并将其拖动到中心标有“维度或项目”的空间中
4. 此流报告是交互式的。 单击任意值可将流展开到后续或上一页。 使用右键单击菜单可展开或折叠列。 同一流量报告中也可以使用不同的维度。
