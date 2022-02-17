---
description: 数据源在处理作为标准服务器调用的数据时，支持以下变量（普通 > 完全处理）。
title: 完全处理
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 9eb8c754-f4de-4483-934e-3f79134516ca
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 100%

---

# 完全处理

>[!IMPORTANT]
>
>Adobe 推荐使用 [Bulk Data Insertion API (BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) 来取代 Full Processing Data Sources。Adobe 将在 2022 年 1 月 31 日弃用 Full Processing Data Sources。[了解详情](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md)

数据源在处理作为标准服务器调用的数据时，支持以下变量（普通 > 完全处理）。

完全处理数据源数据会像 Adobe 服务器在指定的时间接收到该数据一样进行处理（每个点击包含一个时间戳）。

* [访客资料](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_6065627D0C144506965F562C80AE67F8)
* [列引用](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_92BAE76639E3404E97276B1BE0581078)

## 访客资料 {#section_6065627D0C144506965F562C80AE67F8}

完全处理数据源数据使用单独的访客资料进行处理，因此即使上载数据中的访客 ID 与使用 JavaScript 或其他 AppMeasurement 库收集的数据匹配，访客资料也不会通过 eVar 分配进行关联。

例如，访客 ID 为 `"user@example.com"` 的用户通过名为“春季促销”的市场营销活动访问您的网站，该活动存储在营销活动变量中。如果您稍后使用相同的访客 ID 上载一个交易，则“春季促销”活动不会收到使用完全处理数据源上载的任何收入或成功事件的积分。

## 列引用 {#section_92BAE76639E3404E97276B1BE0581078}

<table id="table_AAC04491D643467B9C80FDEF88130B13"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> JavaScript 变量 </th> 
   <th colname="col2" class="entry"> 完全处理列变量 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>campaign </p> </td> 
   <td colname="col2"> <p>营销活动 </p> </td> 
   <td colname="col3"> <p>转化营销活动跟踪代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>channel </p> </td> 
   <td colname="col2"> <p>频道 </p> </td> 
   <td colname="col3"> <p>渠道字符串（例如，体育专栏）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>currencyCode </p> <p>注意：此变量还受到作为 <code> currency code </code> 的标准数据源支持。 </p> </td> 
   <td colname="col3"> <p>收入货币代码（例如 USD）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timestamp </p> </td> 
   <td colname="col2"> <p>日期 </p> </td> 
   <td colname="col3"> <p>使用 ISO 8601 日期格式 <code> YYYY-MM-DDThh:mm:ss±UTC_offset </code>（例如，<code> 2013-09-01T12:00:00-07:00 </code>），或 Unix 时间格式（自 1970 年 1 月 1 日起经过的秒数）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar<i>N</i> </p> </td> 
   <td colname="col2"> <p>eVar<i>N</i>，例如 &lt;eVar2&gt;…&lt;/eVar2&gt; </p> </td> 
   <td colname="col3"> <p>转化 eVar 名称。您最多可有 75 个 eVar (<span class="varname">eVar1</span> - <span class="varname">eVar75</span>)。 </p> <p>您可以指定 eVar 名称 (eVar12) 或一个易记名称（广告活动 3）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>events </p> </td> 
   <td colname="col2"> <p>事件 </p> </td> 
   <td colname="col3"> <p>事件字符串，使用与 <a href="https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=zh-Hans"  >s.events</a> 变量相同的语法进行格式设置。 </p> <p>例如： </p> 
    <code>
      scAdd,event1,event7 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hier<i>N</i> </p> </td> 
   <td colname="col2"> <p>hier<i>N</i>，例如 &lt;hier2&gt;…&lt;/hier2&gt; </p> </td> 
   <td colname="col3"> <p>层级名称。您最多可有 5 个层级 (<span class="varname">hier1</span> - <span class="varname">hier5</span>)。 </p> <p>您可以指定默认的层级名称 (<span class="varname">hier2</span>) 或一个易记名称（<span class="term">北方人</span>）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkName </p> </td> 
   <td colname="col2"> <p>linkName </p> </td> 
   <td colname="col3"> <p>链接名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkType </p> </td> 
   <td colname="col2"> <p>linkType </p> </td> 
   <td colname="col3"> <p>链接类型。支持的值包括： </p> 
    <ul id="ul_E441013055A9447AB6C3FB05B6099F7D"> 
     <li id="li_A33F66F30B60479284F72AE3AD4BF499"> <b>d</b>：下载链接 </li> 
     <li id="li_182F695AA2D044DAB036BAFE38BC3915"> <b>e</b>：退出链接 </li> 
     <li id="li_4FD4D542D1774607860BEF41C1B090D1"> <b>o</b>：自定义链接。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkURL </p> </td> 
   <td colname="col2"> <p>linkURL </p> </td> 
   <td colname="col3"> <p>链接的 HREF。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageName </p> </td> 
   <td colname="col2"> <p>pageName </p> </td> 
   <td colname="col3"> <p>页面名称 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageType </p> </td> 
   <td colname="col2"> <p>pageType </p> </td> 
   <td colname="col3"> <p>页面类型（“错误页面”）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageUrl </p> </td> 
   <td colname="col2"> <p>pageUrl </p> </td> 
   <td colname="col3"> <p>页面 URL（例如 <code>https://www.example.com/index.html)</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>products </p> </td> 
   <td colname="col2"> <p>产品 </p> </td> 
   <td colname="col3"> <p>产品列表（例如，<code> "Sports;Ball;1;5.95"</code>）。每行最多可容纳 4096 字节的值。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prop1 - prop75 </p> </td> 
   <td colname="col2"> <p>prop<i>N</i>，例如 &lt;prop2&gt;…&lt;/prop2&gt; </p> </td> 
   <td colname="col3"> <p>属性编号字符串（例如<span class="term">体育区域</span>）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchaseID </p> </td> 
   <td colname="col2"> <p>purchaseID </p> </td> 
   <td colname="col3"> <p>购买 ID 号码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>s_account </p> </td> 
   <td colname="col2"> <p>reportSuiteID </p> </td> 
   <td colname="col3"> <p>要点击的报表包 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server </p> </td> 
   <td colname="col2"> <p>服务器 </p> </td> 
   <td colname="col3"> <p>服务器字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>state </p> </td> 
   <td colname="col2"> <p>state </p> </td> 
   <td colname="col3"> <p>转化州字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zip </p> </td> 
   <td colname="col2"> <p>zip </p> </td> 
   <td colname="col3"> <p>转化邮政编码。 </p> </td> 
  </tr> 
 </tbody> 
</table>

下表包含在使用 JavaScript 库时自动填充的流量变量。这些属性没有关联的变量，但是可以使用数据源导入。

<table id="table_FDBC5BD225644AA09078C0570BE709FE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>完全处理列变量 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>browserHeight </p> </td> 
   <td colname="col2"> <p>浏览器高度，以像素为单位（例如，768）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>browserWidth </p> </td> 
   <td colname="col2"> <p>浏览器宽度，以像素为单位（例如，1024）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>charSet </p> </td> 
   <td colname="col2"> <p>您的网站所支持的字符集。例如，UTF-8、ISO-8859-1 等。 </p> <p>请参阅<a href="https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/configuration-variables.html?lang=zh-Hans#concept_E65B9A8F75C3482C87D0D455805F89BD"  >多字节字符集</a>（国际化）白皮书，以了解完整列表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickAction </p> </td> 
   <td colname="col2"> <p>访客点击图的对象标识符 (oid) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickActionType </p> </td> 
   <td colname="col2"> <p>访客点击图的对象标识符类型 (oidt) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContext </p> </td> 
   <td colname="col2"> <p>访客点击图的页面标识符 (pid) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContextType </p> </td> 
   <td colname="col2"> <p>访客点击图的页面标识符类型 (pidt) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickSourceID </p> </td> 
   <td colname="col2"> <p>访客点击图的源索引 (oi) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickTag </p> </td> 
   <td colname="col2"> <p>访客点击图的对象标记名称 (ot) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>colorDepth </p> </td> 
   <td colname="col2"> <p>显示器颜色深度，以位为单位（例如，24）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>connectionType </p> </td> 
   <td colname="col2"> <p>访客的连接类型（<span class="term">lan</span> 或<span class="term">调制解调器</span>）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cookiesEnabled </p> </td> 
   <td colname="col2"> <p>Y 或 N，访客是否支持第一方会话 Cookie。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>您的网站所使用的默认货币代码。 </p> <p>例如，USD = 美元、EUR = 欧元、JPY = 日元等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>homePage </p> </td> 
   <td colname="col2"> <p>Y 或 N - 当前页面是否为访客的主页。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaEnabled </p> </td> 
   <td colname="col2"> <p>Y 或 N - 访客是否已启用 Java。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaScriptVersion </p> </td> 
   <td colname="col2"> <p>JavaScript 版本（例如 1.3）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>plugins </p> </td> 
   <td colname="col2"> <p>由分号分隔的浏览器插件名称列表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>propN </p> </td> 
   <td colname="col2"> <p>属性的属性值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>referrer </p> </td> 
   <td colname="col2"> <p>页面反向链接的 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>resolution </p> </td> 
   <td colname="col2"> <p>显示器分辨率（例如 1024x768）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>scXmlVer </p> </td> 
   <td colname="col2"> <p>市场营销报表 XML 请求版本号（例如 1.0）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timezone </p> </td> 
   <td colname="col2"> <p>访客所在时区与格林威治时间的小时差（例如 -8）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorID </p> </td> 
   <td colname="col2"> <p>访客 ID 号码。 </p> </td> 
  </tr> 
 </tbody> 
</table>
