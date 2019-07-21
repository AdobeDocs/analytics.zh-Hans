---
description: 此参考数据表定义您在“营销渠道处理规则”页面上可选择的字段、选项和点击属性。
seo-description: 此参考数据表定义您在“营销渠道处理规则”页面上可选择的字段、选项和点击属性。
seo-title: 营销渠道处理规则-定义
solution: Analytics
subtopic: 营销渠道
title: 营销渠道处理规则-定义
topic: Reports & Analytics
uuid: e71ff5b-912a-4dc0-9c22-4be74c5e3cc0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 营销渠道处理规则-定义

此参考数据表定义您在“营销渠道处理规则”页面上可选择的字段、选项和点击属性。

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>术语 </p> </th> 
   <th colname="col2" class="entry"> <p>定义 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>全部 </p> </td> 
   <td colname="col2"> <p>当编号规则中所有规则都正确时激活此渠道。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>任何 </p> </td> 
   <td colname="col2"> <p>当规则集中任何规则都正确时激活此渠道。仅当编号规则中存在一条以上规则时，此选项才可用。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>AMO ID </p> </td> 
   <td colname="col2"> <p>Advertising Cloud和Advertising Analytics集成使用的主要跟踪代码。启用其中一种集成后，跟踪代码前缀可用于标识Advertising Cloud特定渠道。使用“AMO ID”以“AR”开头，“AC”为“AC”，或“AO”(用于Social)开始。当AMO ID在营销渠道中使用时，单击/成本/印象指标可归于正确的渠道(未配置时，这些指标将转到直接或无)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMO ED ID </p> </td> 
   <td colname="col2"> <p>Advertising Cloud使用的二级跟踪代码。此跟踪代码的主要目的是充当将数据发送回Ad Cloud的关键。但是，如果您希望将其视为两个单独的营销渠道，还可用于标识显示点击率与显示视图。这可以通过设置“AMO EF ID”的营销渠道逻辑来完成”：d“显示点击率”或“AMO EF ID”结束”：i"用于显示视图。如果不希望将Display拆分为两个渠道，请改用AMO ID维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>转化变量 </p> </td> 
   <td colname="col2"> <p>由为本报表包启用的 eVar 组成，并且只在通过网页上的 Adobe 代码设置变量时才适用。 </p> <p>请参阅<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/oms_sc_implement.pdf" scope="external" format="html">实施指南</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>存在 </p> </td> 
   <td colname="col2"> <p>可使用若干选项，包括： </p> <p> 
     <ul id="ul_FE39B5F36235441FB757CC73CA2C4F51"> 
      <li id="li_6DC09918D69B443091AB94DB773D5189"> <p> <span class="uicontrol">不存在</span>：指定请求上不存在点击属性。例如在反向链接域中，如果用户键入一个 URL 或单击一个书签，则该反向链接域属性不存在。 </p> </li> 
      <li id="li_3AB958F997974682824E85014CA266D6"> <p> <span class="uicontrol">为空</span>：指定点击属性存在，通常为 eVar 或查询字符串参数，但没有任何与点击属性相关的值。 </p> </li> 
      <li id="li_25EDA39748D141BA8173CC4C41035ABA"> <p> <span class="uicontrol"> 不包含 </span>：允许您指定引用域不包含特定值(与使用选择 <span class="term"> 中包含 </span>的内容相反)。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将渠道识别为 </p> </td> 
   <td colname="col2"> <p>将规则与您添加到<span class="wintitle">“营销渠道管理器”</span>页面上的营销渠道相关联。 </p> <p>See <a href="../../components/c-marketing-channels/c-channels.md#task_98C9D3F5DBBC4B198E0A9ED4D3891E03" type="task" format="dita" scope="local"> Add marketing channels </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>匹配付费搜索检测规则 </p> </td> 
   <td colname="col2"> <p>Adobe 检测的付费搜索。付费搜索是指公司向列出它们网站的搜索引擎支付费用。付费搜索通常出现在搜索结果顶部或右侧。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>匹配免费搜索检测规则 </p> </td> 
   <td colname="col2"> <p>Adobe 报表检测的免费搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>引用网站与内部 URL 筛选器匹配 </p> </td> 
   <td colname="col2"> <p> 按照“管理工具”中对报表包的定义，页面 URL 与内部 URL 筛选器匹配的访问。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>引用网站与内部 URL 筛选器不匹配 </p> </td> 
   <td colname="col2"> <p>按照“管理工具”中对报表包的定义，引用 URL 与内部 URL 筛选器不匹配。您可以将此设置与<span class="term"> “页面URL </span> ”和 <span class="term"> “存在” </span> 用于设置所有规则，以便在报告的“已识别 <a href="../../components/c-marketing-channels/c-faq.md#section_451E42994DA247A8A7B8559C715A5EE7" type="section" format="dita" scope="local"> 渠道” </a> 部分中没有访问登陆。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>忽略与内部 URL 过滤器匹配的点击量 </p> </td> 
   <td colname="col2"> <p>（关于反向链接）只跟踪来自外部引用网站的点击量。通常，将此设置保留为启用状态，除非您希望包括内部流量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>是访问第一页 </p> </td> 
   <td colname="col2"> <p>Adobe 报表检测到的访问第一页。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面 </p> </td> 
   <td colname="col2"> <p>网站上使用 Adobe 网络信标标记的网页名称。该值等同于 <span class="varname"> s.pageName </span>. Examples include <span class="varname"> Home Page </span> and <span class="varname"> About Us </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面域 </p> </td> 
   <td colname="col2"> <p>访客所登陆页面的域，如 <span class="filepath">products.example.co.uk</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面域和路径 </p> </td> 
   <td colname="col2"> <p>域和路径，如 <span class="filepath">products.example.co.uk/mens/pants/overview.html</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面根目录域 (TLD+1) </p> </td> 
   <td colname="col2"> <p>访客所登陆页面的根目录域，如 <span class="filepath">example.co.uk</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面 URL </p> </td> 
   <td colname="col2"> <p>网站上网页的 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向链接域 </p> </td> 
   <td colname="col2"> <p>访客访问您的网站之前来自的域，例如反向链接来自 <span class="filepath">abcsite.com</span> 和 <span class="filepath">xyzsite.com</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查询字符串参数 </p> </td> 
   <td colname="col2"> <p>If a page URL on your site looks like <span class="filepath"> https://example.com/?page=12345&amp;cat=1 </span>, then page and cat are both query string parameters. (See <span class="filepath"> https://en.wikipedia.org/wiki/Query_string </span>.) </p> <p>您只可为每个规则集指定一个查询字符串参数。要添加额外的查询字符串参数，可使用 <span class="uicontrol">ANY</span> 作为您的运算符，然后将新的查询字符串参数添加到规则中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向链接 </p> </td> 
   <td colname="col2"> <p>访客在访问您的网站前所在的网页位置（完整的 URL）。反向链接存在于所定义域的外部。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>引荐域和路径 </p> </td> 
   <td colname="col2"> <p>引荐域和 URL 路径的组合。示例包括： </p> <p> <span class="filepath"> www.example.com/products/id/12345 </span> </p> <p> <span class="filepath"> ad.example.com/foo </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>引荐参数 </p> </td> 
   <td colname="col2"> <p>反向链接 URL 上的查询字符串参数。例如，如果您的访客来自 <span class="filepath">example.com/?page=12345&amp;cat=1</span>，则 page 和 cat 为引荐参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>引荐根目录域 </p> </td> 
   <td colname="col2"> <p>引荐的根目录域。反向链接存在于所定义域的外部。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜索引擎 </p> </td> 
   <td colname="col2"> <p>Google 或 Yahoo! 等引导访客进入您网站的搜索引擎。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜索关键词 </p> </td> 
   <td colname="col2"> <p>用于在搜索引擎上执行搜索的单词。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜索引擎 + 关键词 </p> </td> 
   <td colname="col2"> <p>唯一识别搜索引擎的搜索关键词和搜索引擎组合。例如，如果您搜索 computer 这个词，搜索引擎和关键词识别如下： </p> 
    <code>搜索跟踪代码=”&lt; search_ type&gt;：&lt;搜索引擎&gt;：&lt; search keyword&gt;“where search_ type=”n"或“p”，search_ engine=“Google”，and search_ keyword=“computer” </code>
  <p><b>注意：</b> n=自然；p=付费 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将渠道值设置为 </p> </td> 
   <td colname="col2"> <p>除了解哪些营销渠道为网站带来访客外，您还可以知道访客的网站活动应归功渠道中哪些横幅广告、搜索关键词或电子邮件促销活动。此 ID 是一个与渠道一起存储的渠道值。通常此值为嵌入在登陆页或反向链接 URL 中的促销活动 ID；在其他情况下，它是搜索引擎和搜索关键词的组合，或是准确从特定渠道中识别访客的反向链接 URL。 </p> </td> 
  </tr> 
 </tbody> 
</table>



