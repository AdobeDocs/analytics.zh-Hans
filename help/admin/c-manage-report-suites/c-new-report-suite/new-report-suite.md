---
description: 您可以通过选择预定义的模板或者使用某个现有报表包作为模型，来创建新的报表包。
title: 新报表包 - 设置
topic: Admin tools
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 新报表包 - 设置

您可以通过选择预定义的模板或者使用某个现有报表包作为模型，来创建新的报表包。

[创建报表包时](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)使用的元素的描述。

>[!NOTE][ 虚拟报表包文档](/help/components/vrs/c-workflow-vrs/vrs-create.md)说明了如何创建虚拟报表包。

<table id="table_F739FBD8DB8D409E916F12F61C5953D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 报表包 ID </span> </td> 
   <td colname="col2"> <p>指定一个唯一ID，它只能包含字母数字字符。 创建此ID后，无法更改它。 Adobe设置所需的ID前缀，也无法更改它。 </p> <p>在创建多个报表包时，请确保使用命名规则获得唯一的报表包 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 网站标题</span> </td> 
   <td colname="col2">在<span class="wintitle">管理工具</span>中标识报表包。此标题还可在包标头中的<span class="wintitle">报表包</span>下拉列表中使用。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 时区</span> </td> 
   <td colname="col2"> 计划事件和时间戳数据。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 基本 URL</span> </td> 
   <td colname="col2"> （可选）定义报表包的基本域。 如果您没有为报表包显式定义内部URL过滤器，则此URL将用作内部URL过滤器。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 默认页面</span> </td> 
   <td colname="col2"> <p>（可选）将<span class="wintitle">默认页面</span>值的发生次数从它遇到的 URL 中剥离开来。如果<span class="wintitle">最受欢迎页面</span>报表包含 URL 而不是页面名称，则此设置可以防止同一网页有多个 URL。 </p> <p>例如，URL <span class="filepath">https://mysite.com</span> 和 <span class="filepath">https://mysite.com/index.html</span> 通常是同一网页。您可以删除不重要的文件名，使得这两个 URL 在您的报表中都显示为 <span class="filepath">https://mysite.com</span>。 </p> <p>如果不设置此值，Analytics 将从 URL 中自动删除以下文件名：<span class="filepath">index.htm</span>、<span class="filepath">index.html</span>、<span class="filepath">index.cgi</span>、<span class="filepath">index.asp</span>、<span class="filepath">default.htm</span>、<span class="filepath">default.html</span>、<span class="filepath">default.cgi</span>、<span class="filepath">default.asp</span>、<span class="filepath">home.htm</span>、<span class="filepath">home.html</span>、<span class="filepath">home.cgi</span> 和 <span class="filepath"> home.asp</span>。 </p> <p>要禁用文件名剥离，请指定URL中从未出现的默认页面值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>起始日期 </p> </td> 
   <td colname="col2">通知Adobe您希望此报表包变为活动的日期。 如果您的部署计划有变动，请使用<a href="/help/admin/c-traffic-management/traffic-management.md">流量管理</a>中的<span class="wintitle">永久性预期流量</span>工具提供更新的流量预估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 估计每日页面查看次数</span> </td> 
   <td colname="col2"> 标识您预计此报表包一天内支持的页面视图数。 大流量需要较长的批准过程。 要避免处理延迟，请尽可能准确地使用此估计。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 基本货币</span> </td> 
   <td colname="col2"> <p>指定用于存储所有货币数据的默认货币。 分析报告使用接收数据时的当前转化率，将其他币种的事务处理转换为基本货币。 </p> <p> 分析报告使 <span class="varname"> 用currencyCode</span> JavaScript变量标识给定事务的货币。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">禁用多字节字符支持</span> </td> 
   <td colname="col2"> <p>禁用对报表包的多字节字符支持。 如果禁用多字节字符支持，则系统假定数据采用ISO-8859-1格式。 网页必须在charSet <span class="varname"></span> JavaScript变量中指定其字符集。 </p> <p>多字节字符支持使用UTF-8在报表包中存储字符。 收到后，系统会将网页字符集中的数据转换为UTF-8字符集，以便您可以在市场营销报告中使用任何语言。 </p> <p>请联系您的客户经理或客户关怀部门，更改现有报表包的多字节字符支持。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 激活此报表包的 Ad Hoc Analysis</span> </td> 
   <td colname="col2"> 当您执行 Ad Hoc Analysis 时启用查看此报表包。 </td> 
  </tr> 
 </tbody> 
</table>

