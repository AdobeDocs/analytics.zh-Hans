---
description: 对“管理员”中报表包“一般帐户设置”的字段描述。
seo-description: 对“管理员”中报表包“一般帐户设置”的字段描述。
seo-title: 一般帐户设置
solution: Analytics
title: 一般帐户设置
topic: 管理工具
uuid: c1ab5c34-2c41-4d12-a706-0e760 dff8 a95
translation-type: tm+mt
source-git-commit: 01ac0011f2e47e6798a520df8ffe5d8393ac0c3c

---


# 一般帐户设置

对“管理员”中报表包“一般帐户设置”的字段描述。

**[!UICONTROL “分析]** ”&gt;“ **[!UICONTROL 管理员]** ”&gt; **[!UICONTROL “报表包]** ”&gt; **[!UICONTROL “编辑设置]** ”&gt; **[!UICONTROL “常规]** ”&gt; **[!UICONTROL “一般帐户设置”]**

这些设置包含基本报表包功能的编辑选项，例如名称和时区。

<table id="table_5448A694DC0A48D2B20C7F1332509F6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选项 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 网站标题</span> </td> 
   <td colname="col2"> <p>标识您的网站。为每个报表包提供一个唯一的网站标题。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 基本 URL</span> </td> 
   <td colname="col2"> <p>指定报表包的主网站。由于基本 URL 不影响反向链接过滤。请改为使用<a href="../../admin/admin/internal-url-filter-admin.md#concept_D6BB8358DB7643F0B13E5DC9B7607998" format="dita" scope="local">内部 URL 过滤器</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 时区</span> </td> 
   <td colname="col2"> <p>确定与报表数据相关联的日期和时间。 </p> <p>更改实时报表包的时区会在报表数据中产生尖峰或间隙。为了尽可能减少影响，Adobe 建议在非高峰时间更改时区以免影响数据的准确性。 </p> <p>例如，如果在 3:00pm 将报表包时区从中部时间改为太平洋时间，报表包的当前时间将变为 1:00pm。由于报告已经收集了 1:00 的数据，因此报表会在 1:00pm 到 3:00pm 之间出现流量尖峰。 </p> <p>或者，如果在 3:00pm 将报表包时区从中部时间改为东部时间，报表包的当前时间将变为 4:00pm。报表显示在更改时间当天 3:00pm 到 4:00pm 没有数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 转化级别</span> </td> 
   <td colname="col2"> <p> 启用或禁用电子商务变量，如 eVar 和促销活动。若您的网站上没有购物车，请使用<span class="uicontrol">已启用，无购物车</span>选项来隐藏所有购物车报表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 默认页面</span> </td> 
   <td colname="col2"> <p> 如果<span class="wintitle">最受欢迎页面报表</span>包含 URL 而不是页面名称，则此设置可以防止多个 URL 表示同一网页。For example, the URLs <span class="filepath"> https://mysite.com</span> and <span class="filepath"> https://mysite.com/index.html</span> are typically the same page. You can remove default filenames so that these two URLs would both show up as <span class="filepath"> https://mysite.com</span>. </p> <p>若留为空白，将从 URL 中删除以下文件名：<span class="filepath">index.htm</span>、<span class="filepath">index.html</span>、<span class="filepath">index.cgi</span>、<span class="filepath">index.asp</span>、<span class="filepath">default.htm</span>、<span class="filepath">default.html</span>、<span class="filepath">default.cgi</span>、<span class="filepath">default.asp</span>、<span class="filepath">home.htm</span>、<span class="filepath">home.html</span>、<span class="filepath">home.cgi</span> 和 <span class="filepath">home.asp</span>。 </p> <p>要完全禁止删除文件名，请输入一个永远不会出现在您 URL 中的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> 将 IP 地址的最后八位字节替换为 0 </span> </td> 
   <td colname="col2"> <p>删除最后八位字节在 IP 过滤之前完成。这样，最后八位字节将被替换为 0，并且应当更新 IP 排除规则以匹配末尾为 0 的 IP 地址。匹配 * 应当匹配 0。 </p> <p>选中此选项表示在处理 IP 地址之前先对它进行更改。例如，IP 地址 134.123.567.780 更改为 134.123.567.0。地域划分数据不会像使用整个 IP 地址时那样精确。具体而言，城市准确性会受到国家或地区准确性的影响。机器人规则和 VISTA 规则均会受到影响，因为这些功能不能使用完整的 IP 地址。此外，基于 IP 的所有处理规则均受此设置影响，包括营销渠道规则和报表包处理规则。 </p> <p>注意：对于 2019 年 1 月之后在伦敦数据中心创建的所有新报表包，默认情况下都会启用此设置，但前提是这些报表包的设置复制自 Admin Console 中列出的模板。设置复制自其他报表包的报表包将继承选定报表包的所有设置。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> IP 模糊处理</span> </td> 
   <td colname="col2"> <p>将 IP 地址转换为不可识别的字符串，实质上是将它们从 Adobe 数据存储库中删除。启用“IP 模糊处理”后，原始 IP 地址将永久丢失。 </p> <p>注意：IP 地址在 Analytics 中的所有地方均被模糊处理，包括 Data Warehouse。但是，Target 中的 IP 设置是单独控制的，因此该设置不对 Target 产生任何影响。 </p> <p>如果启用了 IP 模糊处理，则在 IP 地址被模糊处理之前会发生 IP 排除，这样客户就无需在启用 IP 模糊处理时更改任何内容。 </p> <p>选中<span class="uicontrol">禁用</span>会保留数据中的 IP 地址。 </p> <p>选中<span class="uicontrol">模糊处理 IP 地址</span>会将 IP 更改为哈希值（例如，234abc6493872038）。 </p> <p>选中<span class="uicontrol">删除 IP 地址</span>会在地理查找之后，将数据中的 IP 地址替换为 x.x.x.x。 </p> <p>注意：此设置可能需要更改自定义 <a href="../../admin/admin/bot-removal/bot-rules.md#concept_A306689C65EB4D0F9AE65E3FD48ED5F7" format="dita" scope="local"> 机器人规则</a> 或<a href="../../admin/admin/exclude-ip.md#concept_265A95A803F740629CAAAA7EB8BE81A4" format="dita" scope="local"> IP排除</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 交易 ID 存储</span> </td> 
   <td colname="col2"> <p>可让您使用<a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_Transaction_ID" format="https" scope="external">交易 ID</a> 数据源。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> 激活 Ad Hoc Analysis</span> </td> 
   <td colname="col2"> <p>指示所涉及的报表包是否显示为 Ad Hoc Analysis 中的可用报表包。使用此设置可限制哪些报表包显示为 Ad Hoc Analysis 的选项。例如，您可以对开发和 QA 报表包禁用 Ad Hoc Analysis。 </p> </td> 
  </tr> 
  <tr> 
   <td><span class="wintitle"> 启用 Data Warehouse</span> </td> 
   <td colname="col2"> <p>在<span class="uicontrol">工具</span> &gt; <span class="uicontrol">Data Warehouse</span> 下启用 Data Warehouse 用户界面。 </p> </td> 
  </tr> 
 </tbody> 
</table>

