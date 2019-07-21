---
title: 从第三方分析平台过渡到Adobe Analytics
description: 了解获取报告的关键概念，这些报告面向熟悉其他平台的用户，如Google Analytics。
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# 从第三方分析平台过渡到Adobe Analytics

本指南提供常见报告类型，可帮助您了解Adobe Analytics中的核心概念和工作流程，着重于Adobe与其他常用工具之间的关键相似性和差异。本指南专为熟悉基本数字分析概念的分析师设计，但对于Adobe Analytics则是如此。它假定该组织具有一个可将数据发送到Adobe数据收集服务器的工作实施。If your organization has not yet set up an Adobe Analytics implementation, start with the [Adobe Analytics First Admin Guide](../../admin/admin-console/first-admin-guide.md).

Google Analytics和Adobe Analytics都是强大的平台，可获得有价值的网站性能洞察。每个组件都有自己的处理架构和用户界面，提供了各种平台的独特优势。本指南旨在帮助用户将Google Analytics中的Google Analytics模拟为Adobe Analytics。

在Adobe Analytics中，登录Adobe Experience Cloud后，有两种主要方法可提取基础报表：

* **Reports&amp; Analytics** 是提取基本报表的历史方法。左侧菜单提供预制报表列表，允许用户导航到所需的报告并获取数据。区段和指标可提供其他自定义。熟悉Google Analytics报告的用户可能发现此布局熟悉。
* **Analysis Workspace** 是提取大多数报告的当前建议方法。左侧菜单允许用户拖放组件以构建自己的报告。它可以更自由地满足准确的报告需求。在创建Google Analytics仪表板和自定义报告方面经验丰富的用户可能会发现此布局熟悉。

大多数报告都可以在Reports&amp; Analytics和Analysis Workspace中创建。但是，某些报告只能使用一个平台或另一个平台进行拉动。在大多数情况下，除非仅在Reports&amp; Analytics中提供特定功能，否则Adobe建议使用Analysis Workspace。

## 推荐的学习路径

Adobe建议从获取报告数据的绝对基础知识开始：

* [在Analysis Workspace中为GA用户创建基本报表](reports/create-report.md)

熟悉Analysis Workspace中的组件后，您可以学习如何使用正确的组件重新创建大多数报告。

* [在Adobe Analytics中创建实时报告](reports/realtime-reports.md)
* [在Adobe Analytics中创建受众报告](reports/audience-reports.md)
* [在Adobe Analytics中创建客户获取报告](reports/acquisition-reports.md)
* [在Adobe Analytics中创建行为报告](reports/behavior-reports.md)
* [在Adobe Analytics中创建转换报告](reports/conversions-reports.md)

After learning to pull reports, understanding [processing and architecture differences](processing-differences.md) can help reconcile the different numbers obtained between platforms. An [FAQ](faq.md) is also available.
