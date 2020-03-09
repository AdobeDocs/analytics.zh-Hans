---
title: 从第三方分析平台过渡到 Adobe Analytics
description: 了解获取报表的关键概念，适用于熟悉其他平台（例如 Google Analytics）的用户。
translation-type: ht
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# 从第三方分析平台过渡到 Adobe Analytics

本指南介绍常见的报表类型，帮助您了解 Adobe Analytics 中的核心概念和工作流，重点介绍 Adobe 与其他常用工具之间的主要相似之处和差异。本指南面向熟悉基本数字分析概念但不熟悉 Adobe Analytics 的分析师。该指南假定贵组织有一个向 Adobe 数据收集服务器发送数据的有效实施。如果贵组织尚未设置 Adobe Analytics 实施，请首先阅读 [Adobe Analytics 首要管理指南](/help/admin/admin-console/first-admin-guide.md)。

Google Analytics 和 Adobe Analytics 都是功能强大的平台，都可为您的网站性能提供有价值的分析。每个平台都有各自的处理架构和用户界面，这为每个平台带来独特的优势。本指南旨在帮助具有使用 Google Analytics 经验的用户适应 Adobe Analytics。

在 Adobe Analytics 中，登录 Adobe Experience Cloud 后，可通过两种主要方式提取基本报表：

* **Reports &amp; Analytics** 是获取基本报表的历史方法。左侧菜单提供了一个预制报表列表，允许用户导航到所需报表并获取数据。区段和量度可提供额外的自定义。具有使用 Google Analytics 报表经验的用户可能发现这个布局非常熟悉。
* **Analysis Workspace** 是当前提取大多报表的推荐方法。左侧菜单允许用户拖放组件以构建自己的报表。左侧菜单拥有非常高的自由度，可满足确切的报表需求。具有创建 Google Analytics 功能板和自定义报表经验的用户可能发现这个布局非常熟悉。

大多数报表都可以在 Reports &amp; Analytics 和 Analysis Workspace 中创建。但是，某些报表只能使用其中一个平台进行提取。在大多数情况下，Adobe 建议使用 Analysis Workspace，除非特定功能仅在 Reports &amp; Analytics 中可用。

## 推荐学习路径

Adobe 建议从获取报表数据的绝对基础知识开始：

* [在 Analysis Workspace 中为 GA 用户创建基本报表](reports/create-report.md)

熟悉 Analysis Workspace 中的组件后，您可以了解如何使用正确的组件重新创建大多数报表。

* [在 Adobe Analytics 中创建实时报表](reports/realtime-reports.md)
* [在 Adobe Analytics 中创建受众报表](reports/audience-reports.md)
* [在 Adobe Analytics 中创建客户获取报表](reports/acquisition-reports.md)
* [在 Adobe Analytics 中创建行为报表](reports/behavior-reports.md)
* [在 Adobe Analytics 中创建转化报表](reports/conversions-reports.md)

了解了如何提取报表后，了解[处理和架构差异](processing-differences.md)有助于协调从平台之间获得的不同数字。还提供[常见问题解答](faq.md)。
