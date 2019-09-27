---
description: 向营销渠道报表中添加离线数据。
seo-description: 向营销渠道报表中添加离线数据。
seo-title: 添加脱机数据
solution: Analytics
subtopic: Marketing channels
title: 添加脱机数据
topic: Reports and Analytics
uuid: bbf4661a-b6b1-4a89-a3cf-ae8dd785d37d
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 添加脱机数据

向营销渠道报表中添加离线数据。

在线渠道可让您对通过搜索引擎、互联网广告、反向链接域或电子邮件促销活动来访的访客数据进行分类。离线渠道适用于通过电视广告、报纸或杂志广告发现您网站的访客。

**Integrate data sources into Marketing Channel reports**

如果要将[来自数据源的数据](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_faq.html)集成到营销渠道报表，请谨记以下几点：

* 通过 [transactionID](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_Transaction_ID.html) 传递给分析报表的任何标准点击通常通过营销渠道处理规则进行处理。
* 传递给分析的任何 `transactionID` 数据源都会自动与处理标准点击的同一营销渠道相关联。
* 来自数据源的任何其他数据都不会通过营销渠道处理规则。

有关数据源的详细信息，请参阅[数据源](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)帮助。

要对离线渠道数据分类，请激活“数据源”中的数据，然后下载并编辑该模板。

请参阅[数据源用户指南](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)中的“使用数据源”。

**添加脱机数据**

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1.  在“数据源”页面上，单击&#x200B;**[!UICONTROL 创建]。**
1. Under **[!UICONTROL 1. Select Category]**, select **[!UICONTROL Offline Channel Data]**.
1. Under **[!UICONTROL 2. Select Type]**, select **[!UICONTROL Offline Channel Data]**.
1. Click **[!UICONTROL Activate.]**
1. 按照“数据源激活向导”上的提示将离线量度映射至报表量度。
1. 下载模板文件并在编辑器（如 Excel）中进行编辑。

   请参阅[数据源用户指南](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)中的“创建数据源文件”。

1. 根据[数据源用户指南](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)中的“上载数据源文件”上载文件。
