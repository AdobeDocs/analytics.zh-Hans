---
title: DFA集成 — 生命周期结束信息
description: 为什么Adobe终止DFA Data Connector，还有哪些备选项？
translation-type: tm+mt
source-git-commit: 6669f678c1327b6af4a5b67c8033a9b7d8c9dbcf
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# DFA集成 — 生命周期结束信息

Adobe最近宣布了[其终止Data Connector计划](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/data-connectors-eol.html)，这是用于集成第三方数据（如ESP、VOC等）的传统工具集 Adobe Analytics。

## 为什么数据连接器将进入生命周期？

合作伙伴集成支持的平台是[Adobe Exchange](https://exchange.adobe.com/experiencecloud)，旨在促进Adobe Digital Experience应用程序集成、第三方CXM集成，并在未来支持客户和合作伙伴的各种数据需求。 许多已使用Data Connectors构建集成的合作伙伴已经将这些集成迁移到Adobe Exchange，计划这样做的合作伙伴更多。

## 为什么DFA集成即将进入生命周期？

2020年1月，Google宣布将在2022年前逐步淘汰Chrome中的第三方Cookie。 [](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html)这符合Apple和Mozilla分别为其Safari和Firefox浏览器制定的行业标准。 DFA集成严重依赖第三方Cookie，因此在跨三大因特网浏览器删除第三方Cookie时将变得无效和过时。 Google [在2021年3月](https://blog.google/products/ads-commerce/a-more-privacy-first-web)宣布将不发布替代解决方案，从而强化了这一立场。

不幸的是，拥有DFA集成的谷歌不太可能在Adobe Exchange平台上复制它。 因此，我们将在以下假设下继续前进：一旦Data Connectors脱机，现有集成将停止运行，并且不会进行按产品分类的替换。

DFA集成的“视图穿越”功能是一个重要且额外的因素。 它使Adobe Analytics能够跟踪用户看到展示广告、未点击但随后访问网站的情况。 “视图”基于第三方Cookie，在2021年将继续逐步取消。 这是一个全市场问题，而不仅仅是一个Adobe问题。 目前，没有复制此数据的替代方法。

## 你还有什么选择？

对于有兴趣将展示广告数据(无“视图率”)集成到Adobe Analytics的客户，我们目前有以下选项：

* Adobe Advertising Cloud DSP客户可以利用与Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/ad-cloud/introduction-to-the-analytics-for-advertising-cloud-dsp-integration.html?lang=en#integrations)的按产品分类集成来设置从Google到Adobe Analytics的展示广告数据。 [此集成是我们的最佳选择，是我们向客户推荐的。 Ad Cloud DSP允许客户跨所有广告渠道（包括付费搜索、展示、视频等）提供互联体验。 在[这里](https://experienceleague.adobe.com/docs/advertising-cloud/dsp/introduction/dsp-about.html?lang=en#introduction)了解更多。但是，Ad Cloud DSP也将受到第三方Cookie丢失的影响。
* Adobe Experience Platform和[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en)，它们提供有关显示以及与其他数据源的集成的功能。 客户可以从付费搜索提供商下载其显示数据，并将该数据上传到Experience Platform。 然后，他们将数据直接导入CJA，与其他数据集一起分析。
* Adobe咨询（工程架构师）可以构建自定义解决方案，将展示广告指标引入Adobe Analytics。 此解决方案仍在开发中，欢迎任何有兴趣加入测试版的客户参与。 在功能、可用性和成本可用时，将提供更多详细信息。
* 您可以使用Adobe Analytics中的数据源功能和分类管理自己的展示广告集成。 使用[数据源和分类手动导入您的付费搜索和显示数据，如](https://experienceleague.adobe.com/docs/analytics/import/use-cases/paid-search-metrics.html?lang=en#use-cases)中所述。 (注：此文档指付费搜索，但用例和概念是相同的，可用于显示)。

如需其他问题或支持，请联系[Adobe客户关怀](https://helpx.adobe.com/contact/enterprise-support.ec.html)。