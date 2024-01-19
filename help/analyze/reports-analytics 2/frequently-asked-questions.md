---
description: 为一些最常见的 Analytics 问题提供答案和故障诊断建议。
keywords: 诊断 Analytics 故障
title: Reports & Analytics 常见问题解答
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 99702728-971f-484a-91f5-f3210b89485c
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 100%

---

# 常见问题解答

{{ra-eol}}

为 Reports &amp; Analytics 的一些最常见的 Analytics 问题，提供答案和故障诊断建议。有关常见的实施问题，请参阅实施用户指南中的[常见问题解答](/help/implement/faq.md)。

+++我的帐户已被锁定，怎样才能解锁？要重新激活帐户，请联系贵组织的管理员。另请参阅技术说明用户指南中的[对 Adobe Analytics 登录问题进行故障诊断](/help/technotes/troubleshoot-login.md)。
+++

+++即使已收集数据，为什么我仍会看到空白报告？若要对报告数据进行故障诊断，需要检查以下几项：

* 检查使用的量度：有些报告在 Reports &amp; Analytics 中默认使用“收入”量度。确保您查看的量度与报告相关。
* 检查日期范围：日期范围（尤其是超出贵组织的数据保留策略的日期范围）不会返回任何数据。检查以确保正确设置日期范围。
* 检查内部 URL 过滤器：某些流量源报告只有在您正确定义内部 URL 过滤器之后，才能正常工作。
+++

+++为什么导航菜单中缺少某些报告？任何与菜单中缺少报告有关的问题，通常都是因为权限受限或菜单自定义所致。请联系贵组织的产品管理员，以确保您有权访问所需的所有维度和量度，并且尚未自定义报告包的菜单结构。
+++

+++为什么会有一些较长的值被截断？几乎 Adobe Analytics 中的所有变量都存在着字符数限制。页面名称的字符数限制为 100 个字符，而自定义转化变量 (eVar) 的字符数限制为 255 个字符。Adobe 建议，请您确保向 Adobe 发送较为简短的值，以防遭遇截断。
+++

+++为什么报告会出现严重延迟？实时报告在几分钟之内即可显示一些流量量度；对于转化数据和其他处理密集型数据，则通常需要 30-90 分钟才能显示。尽管 Experience Cloud 平台非常稳健而强大，但仍有少数情况会导致报告延迟。这种延迟指的是滞后。有关更多信息，请参阅技术说明用户指南中的[滞后](/help/technotes/latency.md)。
+++

+++为什么在 iPhone 上看不到设备版本？Apple 设备在用户代理字符串中报告其固件版本，而并非设备版本。通过 Adobe Analytics 提供的信息将难以确定 iPhone 设备版本。有关更多信息，请参阅 Analytics KB 中的[比较 iPhone 设备版本](https://helpx.adobe.com/cn/analytics/kb/comparing-iphone-device-versions.html)。
+++

+++为什么在对值求和时，报告底部显示的总计与求和结果不一致？维度项目通常可以应用于多个位置；例如，跨午夜访问次数或属于单笔订单的多个产品。可以在所有适用的行项目中报告维度项目，但是，在报告总计中，维度项目会去除重复项。有关更多信息，请参阅 Analytics KB 中的[比较行项目总和与报告总计](https://helpx.adobe.com/cn/analytics/kb/sum-line-items-different-from-total.html)。
+++

+++如何从我的报告包中排除特定 IP 地址的数据？您可以从您的报告中排除与内部网站活动相关的数据（如网站测试和员工使用数据）。此功能可让您和您的同事在访问您的网站时不影响流量数据。有关更多信息，请参阅管理员用户指南中的[按 IP 地址排除](/help/admin/admin/exclude-ip.md)。
+++

+++可以删除报告包吗？无法删除报告包。但是，可以在 Adobe Analytics 的所有视图中隐藏报告包。请注意，发送到隐藏报告包的服务器调用仍会计入您的月度合同限制。有关更多信息，请参阅管理员用户指南中的[隐藏报告包](/help/admin/admin/company/c-hide-report-suites.md)。
+++

+++使用分段时，应选用哪个容器？页面查看、访问还是访客？您使用的区段容器取决于您打算捕获数据的范围。页面查看容器只计算与区段标准匹配的点击数，这对于过滤掉不相关的访问部分很有用。访问容器将计算访问的所有点击数，其中一个或多个点击与区段标准匹配，这对于查看常规会话很有用。访客容器计算所有访问次数，其中一个点击匹配区段标准，这对于查看人员很有用。作为分析师，您可以确定最适合选用的区段容器。有关更多信息，请参阅组件用户指南中的[分段概述](/help/components/segmentation/seg-overview.md)。
+++

+++为什么我的区段没有显示在 Data Warehouse 中？由于 Data Warehouse 独特的处理架构，该平台没有针对处理某些类型的数据（如路径）而进行优化。有关更多信息，请参阅组件用户指南中的 [Data Warehouse 区段兼容性](/help/components/segmentation/seg-reference/seg-compatibility.md)。
+++
