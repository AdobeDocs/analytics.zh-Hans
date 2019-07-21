---
description: 为一些最常见的 Analytics 问题提供答案和故障诊断建议。
keywords: 诊断 Analytics 故障
seo-description: 为一些最常见的 Analytics 问题提供答案和故障诊断建议。
seo-title: 常见问题解答
title: 常见问题解答
uuid: 285b0ea4-aa07-4d39 f-37b1 d02 d19 f1 d
translation-type: tm+mt
source-git-commit: fd1e2f1789ed9c8c31c89f0e7b6b7b2dd3ee114d

---


# 常见问题解答

为Reports&amp; Analytics中最频繁提出的Analytics问题提供答案和疑难解答建议。For frequently asked implementation questions, see the [FAQ](../../implement/faq.md) in the Implement user guide.

**我的帐户已被锁定；如何解锁它？**

要重新激活帐户，请与组织中的管理员联系。See also [Troubleshoot login issues with Adobe Analytics](../../technotes/troubleshoot-login.md) in the Technotes user guide.

**即使我知道数据被收集，为何仍会看到空白报告？**

检查报告数据有以下几项功能：

* 检查使用的指标：有些报告默认为Reports&amp; Analytics中的收入。确保查看的量度与报表相关。
* 检查日期范围：日期范围(尤其是超出单位的数据保留策略)可以返回无数据。检查以确保正确设置日期范围。
* 检查内部URL过滤器：在正确定义内部URL过滤器之后，某些流量源报告才会起作用。

**为什么导航菜单中缺少某些报告？**

菜单中的任何报告都缺少来自受限权限或菜单自定义的最常见来源。请联系组织中的产品管理员以确保您有权访问所需的所有维度和指标，并且报告套件的菜单结构未进行自定义。

**为什么会切断一些长值？**

Adobe Analytics中几乎所有变量都有字符限制。页面名称有100个字符限制，而自定义转换变量(eVar)有255个字符限制。Adobe建议您确保发送给Adobe的值简洁，以防止截断。

**为什么我看到报告的主要延迟？**

实时报告允许某些流量计量在几分钟内可用，而转换和其他处理密集型数据通常在30-90分钟内可用。尽管 Experience Cloud 平台非常强大，但仍有少数情况会导致报告延迟。此延迟称为滞后时间。See [Latency](../../technotes/latency.md) in the Technotes user guide for more information.

**为什么看不到iPhone上的设备版本？**

Apple设备在用户代理字符串(而非设备版本)中报告固件版本。使用Adobe Analytics提供的信息确定iPhone设备版本很难。See [Comparing iPhone device versions](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) in the Analytics KB for more information.

**为什么在汇总值时，我的报告底部的总数不匹配？**

维度值通常可在多个位置应用；例如，跨午夜或属于单个订单的多个产品的访问。会在所有适用的行项目中报告维度值，但会在报告总数中取消重复。See [Compare sum of line items to report total](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) in the Analytics KB for more information.

**如何从我的报告套件中的特定IP地址排除数据？**

您可以从报表中消除来自内部网站活动的数据，如站点测试和员工使用情况。此功能可让您和您的同事在访问您的网站时不影响流量数据。See [Exclude by IP Address](../../admin/admin/exclude-ip.md) in the Admin user guide for more information.

**我是否可以删除报告套件？**

不能删除报表包。但是，在Adobe Analytics中的所有视图中都可以隐藏报表包。请注意，发送到隐藏报告套件的服务器调用仍计入您的每月合同限制。See [Hide report suites](../../admin/company/c-hide-report-suites.md) in the Admin user guide for more information.

**使用分段时，我应该使用哪个容器？Page view, visit, or visitor?**

您使用的区段容器取决于您要捕获数据的范围。页面查看容器只会引入匹配区段条件的点击，有助于筛选访问无关部分。访问容器将访问的所有点击带到一次访问中，其中一次或多点击匹配区段条件，对于查看一般会话很有用。访客容器引入了点击匹配的区段条件的所有访问，这有利于查看人员。作为分析师，您可以选择确定哪个细分容器最适合使用。See [Segmentation overview](../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

**为什么我的区段不显示在数据仓库中？**

由于数据仓库的独特处理架构，平台没有优化某些类型的数据，如路径。See [Data Warehouse segment compatibility](../../components/c-segmentation/seg-reference/seg-compatibility.md) in the Components user guide for more information.
