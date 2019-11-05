---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
seo-title: 动态变量
solution: Analytics
subtopic: 变量
title: 动态变量
topic: 开发人员和实施
uuid: 1c6db083-570e-4bc4-858d-84cf46e7bec8
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# 动态变量

通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。

动态变量用于同时捕获多个变量中的相同数据（例如促销活动跟踪代码）。当不同的报表提供了唯一且重要的量度时，通常会使用动态变量。例如，通过捕获[!UICONTROL 自定义转化]变量和[!UICONTROL 自定义流量]变量中的内部搜索关键词，您可以分别查看与这些关键词关联的[!UICONTROL 收入]和[!UICONTROL 每周独特访客]量度.

动态变量还可用于在多种报表条件下查看数据。可在多个具有不同分配和 Cookie 过期设置的 eVar 中捕获促销活动跟踪代码。这就允许用户自行选择将转化量度分配到这些促销活动的方式。

> [!NOTE]不支持同时使用动态变量与 Cookie（s_cc、s_sq、s_fid、s_vi 以及插件设置的任何 Cookie）。您无法使用 `D=<cookie value>`。

动态变量的一个重要优势是能够捕获多个变量中的数据的长字符串，而且无需重复地实际传递这些长字符串。部分浏览器限定了 HTTP GET 请求（包括 Adobe 图像请求）的最大长度。在多个变量之间存在重复数据的情况下，使用动态变量可确保通过降低 Adobe 服务器请求的长度，从而捕捉所有数据。.

在页面查看期间发生的 Adobe 图像请求中，如果使用动态变量将 [!UICONTROL Custom Traffic ] 的值复制到 [!UICONTROL Custom Conversion ]，则会显示 `v1=D=c1`1=1。如果 eVar1 收到之前在请求中的值，则 Adobe 服务器会在数据处理过程中将 [!UICONTROL Custom Traffic 1] 的值动态复制到 [!UICONTROL Custom Conversion 1]。这样，最初使用 [!UICONTROL Custom Traffic 1] 传递的值也会出现在 [!UICONTROL Custom Conversion 1] 报表中。

通过将一个变量设置为所需的值，然后将其他变量设置为 `D=[variable abbreviation]`]，可传递动态变量。有关每个变量的缩写，请参阅[数据收集查询参数](/help/implement/js-implementation/data-collection/query-parameters.md)。动态变量可以从以下位置提取数据：

* 其他查询字符串变量
* HTTP 头（Cookie HTTP 头除外）

要创建动态变量，请在值开头添加一个特殊的前缀。默认前缀为 "D="。标记动态变量有两种方法：

* 使用默认前缀 D=（如：s.prop1="D=User-Agent"）
* 对于非 JavaScript 实施，您可以使用 "D" 查询字符串参数定义一个自定义前缀。例如，如果查询字符串参数为 `"&D=$"`，那么您可以使用以下命令创建一个动态变量：`s.prop1="$User-Agent"`。

使用的变量缩写必须与图像请求中传递的变量参数名称匹配。一些变量在不同情况下使用多个可接受的参数。例如，`pageName=` 和 `gn=` 均可传递页面名称，但后者多用于移动设备和硬编码的实施。如果图像请求使用 `pageName=` 传递页面名称，则可接受 `D=pageName`，但无法接受 `D=gn`。如果图像请求使用 `gn=`，则可接受 `D=gn`，但无法接受 `D=pageName`。

以下信息适用于动态变量：

* 动态变量可与所有版本的 AppMeasurement 代码一起使用。
* 动态变量区分大小写。
* 动态变量支持外加引号的文字字符串。
* 动态变量替换在规则处理、VISTA 和其他处理之前进行。
* 动态变量前缀 "D=" 必须置于变量值开头，而不是中间。例如，使用 `c2='D="test7"+User-Agent'` 而不使用 `c2='"test7"+D=User-Agent'`。

* 与所有的实施技术一样，Adobe 强烈建议先在开发环境下对动态变量实施进行大量测试，然后再部署到生产。由于所复制的完整字符串在客户端调试工具中不可见，因此需要检查受影响的 Analytics 报表，以确认实施成功。
* 在采用了不同最大长度限制的变量之间复制值时，请注意，复制的值如果超出目标变量的最大长度，会导致截断。例如，[!UICONTROL 自定义流量]变量的长度限制为 100 个字符，[!UICONTROL 自定义转化]变量的长度限制为 255 个字符。在使用动态变量将一个 150 字符的值从 s.eVar1 复制到 s.prop1 时，该值会在[!UICONTROL 自定义流量]报表中被截断为 100 字符。

## 动态变量示例 {#section_5CE4468D978540FBA384B9D6477C92EC}

<!-- 

dynvars_examples.xml

 -->

可以在 Analytics 中使用的动态变量示例。

在页面查看期间发生的 Adobe 图像请求中，如果使用动态变量将 [!UICONTROL Custom Traffic ] 的值复制到 [!UICONTROL Custom Conversion ]，则会显示 `v1=D=c1`1=1。如果 eVar1 收到之前在请求中的值，则 Adobe 服务器会在数据处理过程中将 [!UICONTROL Custom Traffic 1] 的值动态复制到 [!UICONTROL Custom Conversion 1]。这样，最初使用 [!UICONTROL Custom Traffic 1] 传递的值也会出现在 [!UICONTROL Custom Conversion 1] 报表中。

注意，`D=[variable]` 的值应当用引号括起来。Analytics 代码会将它视为一个字符串。当字符串传输至 Analytics 时，它将成为一个经过编码的 URL（如果您在 DigitalPulse Debugger 或类似工具中查看请求，则会看到此 URL）。这是正常的。Adobe 的服务器将辩别 `D=[variable]` 结构，在遇到该字符串时，复制相应的值。

> [!NOTE]使用图像请求跟踪链接时必须定义链接类型（download=lnk_d、exit=lnk_e 或 custom link=lnk_o），其定义方式与链接 URL/名称 (pev2) 相同。实施需要通过在 `<a href>` 标记内插入代码的方式进行手动实施。

> [!NOTE]不支持同时使用动态变量与 Cookie（s_cc、s_sq、s_fid、s_vi 以及插件设置的任何 Cookie）。您无法使用 `D=<cookie value>`。

<table id="table_A25D5EA2A8C446F5A55AB32955B9848C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> JavaScript 示例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.eVar1="D=pageName" 
    </code> </td> 
   <td colname="col2"> <p>捕获 eVar1 中的 pageName 值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1='D=v2+":"+c2'&amp;nbsp; 
    </code> </td> 
   <td colname="col2"> <p>将 eVar2:prop2 串联至 prop1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1=s.eVar1="D=g"&amp;nbsp; 
    </code> </td> 
   <td colname="col2"> <p>将页面 URL 传递到 prop1 和 eVar1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.eVar1="D=v0" 
    </code> </td> 
   <td colname="col2"> <p>捕获 eVar 1 中的促销活动。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1='D=User-Agent+" ;- "+Accept-Language' 
    </code> </td> 
   <td colname="col2"> <p>串联 prop1 中的用户代理和接受语言头。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      s.prop1="D=User-Agent" 
    </code> </td> 
   <td colname="col2"> <p>捕获 prop1 中的用户代理。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_DD0B7F0648054E01A5F98CDF18D745E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 图像请求示例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      /b/ss/rsid/?gn=Home&amp;D=~~&amp;c1=~~v0 /b/ss/rsid/?gn=Home&amp;D=~~&amp;c1=~~campaign /b/ss/rsid/?gn=Home&amp;c1=D%3dv0%3d&nbsp;is /b/ss/rsid/?gn=Home&amp;c1=%5b%5bv0%5d%5d%5b
    </code> </td> 
   <td colname="col2"> <p>将 prop1 设置为促销活动的四种方法 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      /b/ss/rsid/?gn=Home&amp;D=~~&amp;c2=~~x-up-subno 
    </code> </td> 
   <td colname="col2"> <p> 将 x-up-subno 头提取到 prop2 中 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      c1=D%3DUser-Agent 
    </code> </td> 
   <td colname="col2"> <p> 将 prop1 作为以 HTTP 头用户代理填充的动态变量 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;c1=D%3D%22test%22 
    </code> </td> 
   <td colname="col2"> <p> 将 prop1 作为以字符串“test”填充的动态变量。当与使用 + 运算符的串联结合使用时，此操作的用处更大。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;c1=D%3D%22US%3A%20%22%2BUser-Agent 
    </code> </td> 
   <td colname="col2"> <p> 将 prop1 作为以前缀“UA:”加用户代理填充的动态变量 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;vid=D%3DX-TM-ANTID 
    </code> </td> 
   <td colname="col2"> <p> 此示例会搜索唯一头，在本例中为 X-TM-ANTID。 </p> </td> 
  </tr> 
 </tbody> 
</table>
