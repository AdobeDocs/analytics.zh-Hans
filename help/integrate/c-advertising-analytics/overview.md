---
description: 'null'
title: Advertising Analytics 概述
uuid: 00e461ff-3e17-4071-818b-93fd1e4b36f1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Advertising Analytics 概述

通过 Advertising Analytics，您可以在 Adobe Analytics 中并排查看您在 Google 和 Bing 上的所有付费搜索数据。以前，您必须在 Adobe Advertising Cloud (AMO) 或 Google/Bing 中查看所有 Google AdWords/DFA 或 Microsoft Bing Ads 数据。现在，您可以在 Adobe Analytics 中直接从搜索引擎获取以下数据：展示次数、点击次数、成本、质量分数、平均位置以及 AMO ID 实例数（点击实例数）。

>[!NOTE] Microsoft Bing 已于 2019 年 3 月 31 日收购了 Yahoo Gemini。因此，现已不再提供 Yahoo Gemini 广告帐户选项。

通过在Adobe Analytics中将这些搜索引擎中的数据整合在一起，您可以利用分析工作区的强大功能分析相同的数据。 A new [Paid Search Performance](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) template in Workspace facilitates this analysis.

![](assets/aa_aw.png)

此集成针对以下受众:

* 需要 **为付费搜索** -营销人员收集绩效报告的分析师。
* 寻 **找以下问题答案的付费搜索营销人员** :我向我们的站点发送了多少流量，客户正在转换多少流量？ 我的广告活动有哪些经济有效？

## 先决条件 {#section_C25E0CA3474C4EDEAEAA9A5B8AAC9299}

* Advertising Analytics is available for Adobe Analytics [Select](https://www.adobe.com/cn/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/cn/data-analytics-cloud/analytics/prime.html), and [Ultimate](https://www.adobe.com/cn/data-analytics-cloud/analytics/ultimate.html) SKUs only.

* 此功能适用于非Advertising Cloud和非AMO客户。
* 您必须是Adobe Analytics管理员才能访问Advertising Analytics。 随后，您可以 [向非管理员](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) 授予访问权限。
* 如果您想在任意 Analytics 报表包中查看 Google/Bing 搜索数据，则必须将这些 Analytics 报表包[映射到您的 Experience Cloud 组织](https://marketing.adobe.com/resources/help/zh_CN/mcloud/report-suite-mapping.html)。
* For any report suite where you want to view Google/Bing search data, you must [enable those report suite/s for Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).

* 您需要具有与Adobe Analytics集成的搜索帐户（如Google帐户ID和密码）编辑权限的用户的登录凭据。
* 对于Bing Ads，您还需要Bing Customer ID。
* If you use Internet Explorer 11 (or earlier), you will not be able to successfully [set up an advertising account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) for any of the three search engines. 请改用其他Web浏览器。

## Advertising Analytics 权限 {#section_FCC58EB635954A32990D4E67B52B4369}

Analytics具有自动授予Analytics管理员的两个权限。 然后，管理员可以选择向非管理员授予这些权限。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 权限 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
   <th colname="col3" class="entry"> 在Adobe Analytics中授予权限 </th> 
   <th colname="col4" class="entry"> 如果您登录到Adobe Experience Cloud，请授予权限 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertising Analytics 管理 </p> </td> 
   <td colname="col2"> <p>允许用户设置／编辑/视图广告搜索帐户。 </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> 管理员</span> &gt; <span class="uicontrol">用户管理</span> &gt; <span class="uicontrol">群组</span> &gt; <span class="uicontrol">编辑全部报表访问</span> &gt; <span class="uicontrol">自定义 Analytics 工具</span> &gt; <span class="uicontrol">Advertising Analytics 管理</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> 登录到 adminconsole.adobe.com</span> &gt; <span class="uicontrol">产品</span> &gt; <span class="uicontrol">产品配置文件</span> &gt; <span class="uicontrol">权限选项卡</span> &gt; <span class="uicontrol">Analytics 工具</span> &gt; <span class="uicontrol">Advertising Analytics 管理</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertising Analytics 配置 </p> </td> 
   <td colname="col2"> <p>允许用户配置要为Advertising Analytics配置的报表包。 </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> 管理员</span> &gt; <span class="uicontrol">用户管理</span> &gt; <span class="uicontrol">群组</span> &gt; <span class="uicontrol">编辑全部报表访问</span> &gt; <span class="uicontrol">自定义报表包工具</span> &gt; <span class="uicontrol">Advertising Analytics 配置</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> 登录到 adminconsole.adobe.com</span> &gt; <span class="uicontrol">产品</span> &gt; <span class="uicontrol">产品配置文件</span> &gt; <span class="uicontrol">权限选项卡</span> &gt; <span class="uicontrol">报表包工具</span> &gt; <span class="uicontrol">Advertising Analytics 配置</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Advertising Analytics 维度和量度 {#section_C0DF4A08EA9E46ADABE9E465AFC11E32}

Advertising Analytics将以下维度和指标添加到分析工作区、Reports &amp; Analytics、Report Builder和Analytics报告API。

**维度**

>[!IMPORTANT]
>
>这项集成可通过 AMO ID 变量的分类创建一组新维度。这些新维度不会影响或修改您的现有营销渠道或活动跟踪变量维度。 当访客通过付费搜索广告登陆到网站时，AMO ID将连接到访客用户档案。 因此，AMO维度可用于细分由此集成提供的AMO度量以及由访客在下游捕获的任何数据(访问、访客、页面视图、弹出率、订单、收入、自定义事件等)。 在报告其他现场指标时，也可以按其他维度对它们进行细分。
>
>这些指标的分类每天都会更新。 因此，如果您在搜索引擎中对元数据进行了更改，则可能直到更新分类的次日才能看到这些更改。

| 分类（维）名称 | 定义 |
|--- |--- |
| 关键字匹配类型(AMO ID) | 关键字匹配类型。如果广告类型没有匹配类型，则值通常为宽、短语、精确或无值。 |
| 广告平台(AMO ID) | 搜索引擎名称。 值可能包括 Google AdWords 或 Microsoft Bing Ads。 |
| 帐户(AMO ID) | 要跟踪的搜索引擎帐户的名称。 |
| 活动(AMO ID) | 搜索引擎帐户中的活动名称。 |
| 广告组(AMO ID) | 搜索引擎活动中广告组的名称。 |
| 广告(AMO ID) | 广告中使用的广告标题 + 广告描述。 |
| 关键字(AMO ID) | 您的搜索引擎帐户的“关键字”值 |
| 匹配类型(AMO ID) | 分配给关键字的关键字匹配类型。该值通常为&quot;广泛&quot;、&quot;短语&quot;或&quot;精确&quot;；如果广告类型没有匹配类型，则为&quot;无&quot;。 |
| 广告类型(AMO ID) | 投放的广告类型，通常为&quot;文字广告&quot;。 |
| 广告标题(AMO ID) | 广告中使用的“标题”对象. |
| 广告说明(AMO ID) | 广告中使用的“广告描述”对象. |
| 广告显示URL(AMO ID) | 广告中使用的“广告显示 URL”对象. |
| 广告目标URL(AMO ID) | 分配给您的广告的登陆页面 URL 或最终 URL. |
| 网络(AMO ID) | 广告所服务的网络。 对于 Advertising Analytics，该值始终为“搜索”。 |
| 位置(AMO ID) | 指定式投放网站（适用于内容网络）。只有指定式投放 (Managed Placement) 才会使用此维度。 |
| 产品目标(AMO ID) | PLA广告中使用的产品目标名称（而非实际购买的产品）。 |
| 优化(AMO ID) | Advertising Analytics不使用此功能。 它仅供Advertising Cloud客户使用。 |
| 设备(AMO ID) | 今天不用。潜在未来产品增强的占位符，用于指示广告的目标设备类型（例如移动设备、桌面）(而非实际访客设备)。 |

**量度**

>[!IMPORTANT]
>
>Advertising Analytics 提供的量度（如下所列）是来自搜索引擎的概要级别的数据。它们与Analytics访客用户档案无关。 它们仅连接到AMO ID变量及其关联的分类维度。 因此，除基于AMO ID维度的维／区段外，不应报告这些维／区段。 这样做将导致Analytics显示数据的零。 您可以将这些计算量度包含在其他量度中，但这些计算量度也应仅按AMO ID维度细分。
>
>这些指标是每天收集的数据，因此它们没有当天的数据。 也不应以低于每日的粒度报告它们。
>
>在登陆页上设置AMO ID时，会设置AMO ID实例量度（即点进率）。 此量度在登陆页点击时实时捕获，并可用于登陆页中也设置了其他维度的细分。

| 量度名称 | 定义 |
|--- |--- |
| AMO 展示次数 | 搜索引擎报告的广告印象数。 |
| AMO 点击次数 | 搜索引擎报告的广告点击次数。 |
| AMO 成本 | 搜索引擎报告的每个关键字／广告的支付成本。 |
| 平均位置 | 反映搜索引擎报告的广告平均位置的计算量度。 |
| 平均质量分数 | 反映搜索引擎报告的平均质量分数的计算量度。 |
