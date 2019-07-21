---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
seo-title: 动态变量
solution: Analytics
subtopic: 变量
title: 动态变量
topic: 开发人员和实施
uuid: 1c6db083-5770e-4bc4-858d-84cf46e7bec8
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 动态变量

通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。

动态变量用于同时捕获多个变量中的相同数据（例如促销活动跟踪代码）。当不同的报表提供了唯一且重要的量度时，通常会使用动态变量。例如，通过捕获[!UICONTROL 自定义转化]变量和[!UICONTROL 自定义流量]变量中的内部搜索关键词，您可以分别查看与这些关键词关联的[!UICONTROL 收入]和[!UICONTROL 每周独特访客]量度。

动态变量还可用于在多种报表条件下查看数据。可在多个具有不同分配和 Cookie 过期设置的 eVar 中捕获促销活动跟踪代码。这就允许用户自行选择将转化量度分配到这些促销活动的方式。

>[!NOTE]
>
>与cookie(s_ cc、s_ sq、s_ fid、s_ vi和由插件设置的任何cookie)一起不支持动态变量。`D=<cookie value>`您无法使用。

动态变量的一个重要优势是能够捕获多个变量中的数据的长字符串，而且无需重复地实际传递这些长字符串。部分浏览器限定了 HTTP GET 请求（包括 Adobe 图像请求）的最大长度。在多个变量之间存在重复数据的情况下，使用动态变量可确保通过降低 Adobe 服务器请求的长度，从而捕捉所有数据。。

在页面查看期间发生的 Adobe 图像请求中，如果使用动态变量将 [!UICONTROL Custom Traffic ] 的值复制到 [!UICONTROL Custom Conversion ]，则会显示 `v1=D=c1`1=1。如果 eVar1 收到之前在请求中的值，则 Adobe 服务器会在数据处理过程中将 [!UICONTROL Custom Traffic 1] 的值动态复制到 [!UICONTROL Custom Conversion 1]。这样，最初使用 [!UICONTROL Custom Traffic 1] 传递的值也会出现在 [!UICONTROL Custom Conversion 1] 报表中。

通过将一个变量设置为所需的值，然后将其他变量设置为 `D=[variable abbreviation]`]，可传递动态变量。For abbreviations for each variable, see [Data Collection Query Parameters](../../../implement/js-implementation/data-collection/query-parameters.md). 动态变量可以从以下位置提取数据：

* 其他查询字符串变量
* HTTP 头（Cookie HTTP 头除外）

要创建动态变量，请在值开头添加一个特殊的前缀。默认前缀为 "D="。标记动态变量有两种方法：

* 使用默认前缀 D=（如：s.prop1="D=User-Agent"）
* 对于非 JavaScript 实施，您可以使用 "D" 查询字符串参数定义一个自定义前缀。For example, if the query-string parameter is `"&D=$"`, you can create a dynamic variable with the following command: `s.prop1="$User-Agent"` .

使用的变量缩写必须与图像请求中传递的变量参数名称匹配。一些变量在不同情况下使用多个可接受的参数。For example, `pageName=` and `gn=` both pass the page name, but the latter is most often used in mobile and hard-coded implementations. If the image request uses `pageName=` to pass the page name, then `D=pageName` is acceptable but `D=gn` is not. If the image request uses `gn=`, then `D=gn` is acceptable, but `D=pageName` is not.

以下信息适用于动态变量：

* 动态变量可与所有版本的 AppMeasurement 代码一起使用。
* 动态变量区分大小写。
* 动态变量支持外加引号的文字字符串。
* 动态变量替换在规则处理、VISTA 和其他处理之前进行。
* 动态变量前缀 "D=" 必须置于变量值开头，而不是中间。For example, use `c2='D="test7"+User-Agent'` rather than `c2='"test7"+D=User-Agent'` .

* 与所有的实施技术一样，Adobe 强烈建议先在开发环境下对动态变量实施进行大量测试，然后再部署到生产。由于所复制的完整字符串在客户端调试工具中不可见，因此需要检查受影响的 Analytics 报表，以确认实施成功。
* 在采用了不同最大长度限制的变量之间复制值时，请注意，复制的值如果超出目标变量的最大长度，会导致截断。例如，[!UICONTROL 自定义流量]变量的长度限制为 100 个字符，[!UICONTROL 自定义转化]变量的长度限制为 255 个字符。在使用动态变量将一个 150 字符的值从 s.eVar1 复制到 s.prop1 时，该值会在[!UICONTROL 自定义流量]报表中被截断为 100 字符。

## 动态变量示例 {#section_5CE4468D978540FBA384B9D6477C92EC}

<!-- 

dynvars_examples.xml

 -->

可以在 Analytics 中使用的动态变量示例。

在页面查看期间发生的 Adobe 图像请求中，如果使用动态变量将 [!UICONTROL Custom Traffic ] 的值复制到 [!UICONTROL Custom Conversion ]，则会显示 `v1=D=c1`1=1。如果 eVar1 收到之前在请求中的值，则 Adobe 服务器会在数据处理过程中将 [!UICONTROL Custom Traffic 1] 的值动态复制到 [!UICONTROL Custom Conversion 1]。这样，最初使用 [!UICONTROL Custom Traffic 1] 传递的值也会出现在 [!UICONTROL Custom Conversion 1] 报表中。

Note that the `D=[variable]` value should be in quotes. Analytics 代码会将它视为一个字符串。当字符串传输至 Analytics 时，它将成为一个经过编码的 URL（如果您在 DigitalPulse Debugger 或类似工具中查看请求，则会看到此 URL）。这是正常的。Adobe's servers recognize the `D=[variable]` construction and will copy the appropriate value when they encounter this string.

>[!NOTE]
>
>使用图像请求跟踪链接时，必须定义链接类型(download= lnk_ d、exit= lnk_ e或custom link= lnk_ o)，与链接URL/名称(pev2)一样。Links require manual implementation by inserting code within the `<a href>` tag.

>[!NOTE]
>
>与cookie(s_ cc、s_ sq、s_ fid、s_ vi和由插件设置的任何cookie)一起不支持动态变量。`D=<cookie value>`您无法使用。

<table id="table_A25D5EA2A8C446F5A55AB32955B9848C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> JavaScript 示例 </th> 
   <th colname="col2" class="entry"> 说明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. eVar1=“D= pageName” </code>
  </td> 
   <td colname="col2"> <p>捕获 eVar1 中的 pageName 值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop1='D= v2+”：“+ c2”&amp; amp；nbsp； </code>
  </td> 
   <td colname="col2"> <p>将 eVar2:prop2 串联至 prop1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop1= s. eVar1=“D= g”&amp; amp；nbsp； </code>
  </td> 
   <td colname="col2"> <p>将页面 URL 传递到 prop1 和 eVar1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. eVar1=“D= v0” </code>
  </td> 
   <td colname="col2"> <p>捕获 eVar 1 中的促销活动。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop1='D= User-Agent+'；-“+接受语言” </code>
  </td> 
   <td colname="col2"> <p>串联 prop1 中的用户代理和接受语言头。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>s. prop1=“D= User-Agent” </code>
  </td> 
   <td colname="col2"> <p>捕获 prop1 中的用户代理。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_DD0B7F0648054E01A5F98CDF18D745E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 图像请求示例 </th> 
   <th colname="col2" class="entry"> 说明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">/b/ss/rsid/？gn= Home&amp; D=~~&amp; c1=~ v0/b/ss/rsid/？gn= Home&amp; D=~~&amp; c1=~~ campaign/b/ss/rsid/？gn= Home&amp; c1= D%3dv0%d是/b/ss/rsid/吗？gn=主页&amp; c=%5b%5bv0%d%5d%5b5b </code>
  </td> 
   <td colname="col2"> <p>将 prop1 设置为促销活动的四种方法 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>/b/ss/rsid/？gn= Home&amp; D=~~&amp; c2=~~ x-up-subno </code>
  </td> 
   <td colname="col2"> <p> 将 x-up-subno 头提取到 prop2 中 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>c1= D%3DUser-Agent </code>
  </td> 
   <td colname="col2"> <p> 将 prop1 作为以 HTTP 头用户代理填充的动态变量 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c1= D%3D%22test%22 </code>
  </td> 
   <td colname="col2"> <p> 将 prop1 作为以字符串“test”填充的动态变量。当与使用 + 运算符的串联结合使用时，此操作的用处更大。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c1= D%3D%22US%3A%20%22Buser-Agent </code>
  </td> 
   <td colname="col2"> <p> 将 prop1 作为以前缀“UA:”加用户代理填充的动态变量 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">vid= D%3DX-TM-ANDID </code>
  </td> 
   <td colname="col2"> <p> 此示例会搜索唯一头，在本例中为 X-TM-ANTID。 </p> </td> 
  </tr> 
 </tbody> 
</table>
