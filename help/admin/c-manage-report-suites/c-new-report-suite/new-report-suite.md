---
description: 您可以通过选择预定义的模板或者使用某个现有报表包作为模型，来创建新的报表包。
title: 新报表包 - 设置
feature: Admin Tools
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 93%

---

# 新报表包 - 设置

您可以通过选择预定义的模板或者使用某个现有报表包作为模型，来创建新的报表包。

[创建报表包时](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)使用的元素的描述。

>[!NOTE]
>
>[虚拟报表包文档](/help/components/vrs/c-workflow-vrs/vrs-create.md)说明了如何创建虚拟报表包。

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
   <td colname="col2"> <p>指定一个唯一 ID，其中仅可包含字母数字字符。此 ID 一经创建，即无法更改。Adobe 会设置所需的 ID 前缀，该前缀也无法更改。 </p> <p>在创建多个报表包时，请确保使用命名规则获得唯一的报表包 ID。 </p> </td> 
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
   <td colname="col2"> （可选）定义报表包的基本域。如果没有为报表包明确定义内部 URL 过滤器，那么此 URL 将作为内部 URL 过滤器使用。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 默认页面</span> </td> 
   <td colname="col2"> <p>（可选）将<span class="wintitle">默认页面</span>值的发生次数从它遇到的 URL 中剥离开来。如果<span class="wintitle">最受欢迎页面</span>报表包含 URL 而不是页面名称，则此设置可以防止同一网页有多个 URL。 </p> <p>例如，URL<span class="filepath"> https://example.com</span>和<span class="filepath"> https://example.com/index.html</span>通常是同一页。 您可以删除无关的文件名，以便这两个URL在报表中都显示为<span class="filepath"> https://example.com</span>。 </p> <p>如果不设置此值，Analytics 将从 URL 中自动删除以下文件名：<span class="filepath">index.htm</span>、<span class="filepath">index.html</span>、<span class="filepath">index.cgi</span>、<span class="filepath">index.asp</span>、<span class="filepath">default.htm</span>、<span class="filepath">default.html</span>、<span class="filepath">default.cgi</span>、<span class="filepath">default.asp</span>、<span class="filepath">home.htm</span>、<span class="filepath">home.html</span>、<span class="filepath">home.cgi</span> 和 <span class="filepath"> home.asp</span>。 </p> <p>要禁止剥离文件名，可以输入永远不会在您的 URL 中出现的默认页面值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>起始日期 </p> </td> 
   <td colname="col2">通知 Adobe 您希望此报表包变为活动状态的日期。如果您的部署计划有变动，请使用<a href="/help/admin/c-traffic-management/traffic-management.md">流量管理</a>中的<span class="wintitle">永久性预期流量</span>工具提供更新的流量预估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 估计每日页面查看次数</span> </td> 
   <td colname="col2"> 确定您预计此报表包在一天内支持的估计页面查看次数。大流量需要的批准过程较长。为避免处理延迟，请尽量确保此估计值的准确性。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 基本货币</span> </td> 
   <td colname="col2"> <p>指定用于存储所有货币数据的默认货币。Analytics 报表可以使用收到数据时的最新货币兑换率，将使用其他货币进行的交易转换为基本货币。 </p> <p> Analytics 报表使用 <span class="varname">currencyCode</span> JavaScript 变量来标识指定交易的货币。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">禁用多字节字符支持</span> </td> 
   <td colname="col2"> <p>禁用对报表包的多字节字符支持。如果禁用多字节字符支持，则系统会假定数据为 ISO-8859-1 格式。网页必须在 <span class="varname">charSet</span> JavaScript 变量中指定其字符集。 </p> <p>多字节字符支持使用 UTF-8 将字符存储在报表包中。系统在接收数据之后会将其从您的网页字符集转换为 UTF-8 字符集，从而使您可以在市场营销报告中使用任何语言。 </p> <p>要将现有报表包更改为支持多字节字符，请联系您的客户经理或客户关怀。 </p> </td> 
  </tr>  
 </tbody> 
</table>
