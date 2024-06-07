---
description: 可使用处理规则读取和写入的维度（除非另有说明）。
subtopic: Processing rules
title: 可用于处理规则的维度
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: ht
source-wordcount: '729'
ht-degree: 100%

---

# 可用于处理规则的维度

可使用处理规则读取和写入的维度（除非另有说明）。

## 自定义值和上下文数据 {#section_7A5E1810CAC34B0BBC69F8F5F7C75AA5}

<table id="table_5011C501D5DC489E87A42FFC51DEB40D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 值 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>自定义值 </p> </td> 
   <td colname="col2"> <p>在处理规则的操作中直接键入的自定义文本或值。这些值可在后续条件和规则中使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>关联值 </p> </td> 
   <td colname="col2"> <p>通过将两个值组合所创建的值。例如，可以将类别和页面名称进行组合来创建子类别。这些值可在后续条件和规则中使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>修改的值 </p> </td> 
   <td colname="col2"> <p>如果使用处理规则更改变量值，则此更改的值可在后续条件和规则中使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上下文数据变量 </p> </td> 
   <td colname="col2"> <p>随点击发送的命名变量。 </p> <p>注意：上下文数据变量中包含的任何数据都必须复制到报表变量中才能显示在报表中。上下文数据变量不可在任何报表界面（包括点击流数据馈送）中查看。 </p> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> 将上下文数据变量复制到 eVar </a> </p> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md"> 使用上下文数据变量设置事件 </a> </p> <p> <a href="/help/implement/vars/page-vars/contextdata.md"> 上下文数据变量</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 流量变量 {#section_225156106F8B41F8BC1E68D58DDC2652}

<table id="table_575F618C59DC4933BC77F935518EAE39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>prop 1-75 </p> </td> 
   <td colname="col2"> <p> <code> prop1 - prop75</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>层次结构 1-5 </p> </td> 
   <td colname="col2"> <p> <code> hier1 - hier5</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>网站区域 </p> </td> 
   <td colname="col2"> <p> <code> s.channel </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>服务器 </p> </td> 
   <td colname="col2"> <p> <code> s.server </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 点击属性 {#section_07E69A86A47741A083FD84F112EB80D0}

<table id="table_9011B1FA462B4DBBAA58FC2D6D638DA1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 属性 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>报表包 ID（只读） </p> </td> 
   <td colname="col2"> <p>执行处理规则的报表包可能不是在 AppMeasurement 中指定的初始报表包。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面名称 </p> </td> 
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>注意：链接跟踪调用在其到达处理规则之前剥离 <code>pageName</code> 变量。如果使用处理规则重新插入页面名称值，则将点击视为页面查看而非链接跟踪调用。Adobe 建议检查以确保已设置页面名称，然后再修改它。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面 URL </p> </td> 
   <td colname="col2"> <code> s.pageURL</code> 或未指定 <code> s.pageURL</code> 时的当前页面 URL。 <p>注意：链接跟踪调用在其到达处理规则之前剥离 <code>pageURL</code> 变量。如果使用处理规则重新插入页面 URL 值，则将点击视为页面查看而非链接跟踪调用。Adobe 建议检查以确保已设置页面 URL，然后再修改它。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查询字符串参数 </p> </td> 
   <td colname="col2"> <p>当前 URL 中指定查询字符串参数的值或不存在参数时的 Null。对于 URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>，查询字符串参数 <span class="syntax codeph">cid</span> 的值为 <b>ad1</b>，并且查询字符串参数 <span class="syntax codeph">node</span> 的值为 <b>4</b>。 </p> <p>如果您运行 JavaScript AppMeasurement H.25.2 或更早版本，则页面 URL 可能会在 255 个字符后截断。JavaScript AppMeasurement H.25.3（2013 年 1 月发布）及更高版本为处理规则提供了完整的 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面路径 </p> </td> 
   <td colname="col2"> <p>页面 URL 的路径。URL <b>https://www.example.com/news/a.html?cid=ad1</b> 的路径是 <span class="syntax codeph">news/a.html</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面域 </p> </td> 
   <td colname="col2"> <p>在 URL 中指定的完整主机名。https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面根目录域 </p> </td> 
   <td colname="col2"> <p>页面主机名的最后两个部分。https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面查询字符串 </p> </td> 
   <td colname="col2"> <p>URL 的完整查询字符串。https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向链接*（只读） </p> </td> 
   <td colname="col2"> <p>HTTP 反向链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向链接查询字符串参数（只读） </p> </td> 
   <td colname="col2"> <p>反向链接 URL 中指定查询字符串参数的值或不存在参数时的 Null。对于 URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>，查询字符串参数 <span class="syntax codeph">cid</span> 的值为 <b>ad1</b>，并且查询字符串参数 <span class="syntax codeph">node</span> 的值为 <b>4</b>。 </p> <p>如果您运行 JavaScript AppMeasurement H.25.2 或更早版本，则页面 URL 可能会在 255 个字符后截断。JavaScript AppMeasurement H.25.3（2013 年 1 月发布）及更高版本为处理规则提供了完整的 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向链接域名（只读） </p> </td> 
   <td colname="col2"> <p>反向链接的完整主机名。https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向链接根目录域（只读） </p> </td> 
   <td colname="col2"> <p>反向链接主机名的最后两个部分。https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向链接查询字符串（只读） </p> </td> 
   <td colname="col2"> <p>反向链接 URL 中包含的查询字符串参数。https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP 地址（只读） </p> </td> 
   <td colname="col2"> <p>浏览器报告的 IP 地址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户代理（只读） </p> </td> 
   <td colname="col2"> <p>浏览器报告的用户代理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AppMeasurement 代码版本（只读） </p> </td> 
   <td colname="col2"> <p>用于发出请求的 AppMeasurement 库的版本。使用图像信标时，您可以借助使用处理规则读取的自定义值进行填充。此值显示在 URL 中的以下位置： </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/... </p> </td> 
  </tr> 
 </tbody> 
</table>

## 转化变量 {#section_311856B21B3B49DBAA0539CFA06C409F}

<table id="table_E28729026EDA485989178A3B887B5983"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>eVar 1-N </p> </td> 
   <td colname="col2"> <p> <code> evar1</code> — <code> evarN</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>营销活动跟踪代码 </p> </td> 
   <td colname="col2"> <p> <code> s.campaign</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>货币代码 </p> </td> 
   <td colname="col2"> <p> <code> s.currencyCode</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>列表变量 1-3 </p> </td> 
   <td colname="col2"> <p> <code> s.list1</code> — <code> s.list3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>购买 ID </p> </td> 
   <td colname="col2"> <p> <code> s.purchaseID</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>交易 ID </p> </td> 
   <td colname="col2"> <p> <code> s.transactionID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>访客所在州 </p> </td> 
   <td colname="col2"> <p> <code> s.state</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>访客 ZIP/邮政编码 </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 成功事件 {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

处理规则可以设置事件，但无法将其作为条件读取。

<table id="table_926ED12B58CA4FB685D799DC6EE567C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Event </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>事件 1-1000 </p> <p>（对于 SiteCatalyst 15 客户，事件 1-100。） </p> </td> 
   <td colname="col2"> <p> <code> event1</code> — <code> event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchase、scView、scAdd 和其他购物车事件 </p> </td> 
   <td colname="col2"> <p>预定义的事件。 </p> </td> 
  </tr> 
 </tbody> 
</table>
