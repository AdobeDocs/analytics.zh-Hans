---
description: 要开始使用 Analytics，必须将数据发送到报表包才能在报表中进行显示。
keywords: Analytics实施；javascript；javascript实施；appasurement；下载AppMeasurement；标识服务；loc torapi. js；缓存；appasurement压缩
seo-description: 要开始使用 Analytics，必须将数据发送到报表包才能在报表中进行显示。
seo-title: JavaScript实施概述
solution: Analytics
title: JavaScript实施概述
topic: 开发人员和实施
uuid: bb661d8c-faf9-4454-ac3 c-0c1 a4 c0 a9336
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# JavaScript实施概述

要开始使用 Analytics，必须将数据发送到报表包才能在报表中进行显示。

The easiest and recommended way to send data to [!DNL Analytics] is by using [Dynamic Tag Management](../../implement/c-implement-with-dtm/dtm-implementation-overview.md). 但是，在有些情况下，您可能需要使用更传统的 JavaScript 方法来实施 Analytics。

>[!NOTE]
>
>本节介绍实施Analytics的传统方法。所有 Analytics 客户都具有访问[动态标签管理](https://marketing.adobe.com/resources/help/en_US/dtm/) 的权限，这是部署 Experience Cloud 标签的标准方法。

## 实施步骤 {#section_73961BAD5BB4430A95E073DE5C026277}

要成功对页面实施代码收集数据，必须拥有访问主机服务器的权限，这样才能将新内容上载到您的网站。在现有网站上实施代码时，此方法也非常有用。

以下步骤详细说明了如何进行基本的 Analytics 实施。

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> 步骤 </th> 
   <th colname="col1" class="entry"> 任务 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> 下载 AppMeasurement for JavaScript 和访客 ID 服务。 </td> 
   <td colname="col2"> <p>您可以在<a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=code_manager_admin" format="http" scope="external">代码管理器</a>中进行下载。 </p> <p>此下载 zip 文件中包含多个文件。其中，<code>AppMeasurement.js</code> 和 <code>VisitorAPI.js</code> 是实施 Analytics 时要用到的相关文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> 设置标识服务。 </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Identity Service for Analytics </a>. </p> 
    <draft-comment> 
     <p>在 <code>VisitorAPI.js</code> 中，将以下访客 ID 初始化代码添加至文件开头： </p> 
     <code class="syntax javascript">
     var rector= Performator. getInstance(“INSERT-MCORG-ID-HERE”)；folder. trackingServer=“INSERT-TRANING-SERVER-HERE”；//与s. trackingServer访问者trackingServerSecure=“INSERT-Secure-TRANSING-SERVER-HERE”相同；//sameas s. trackingServerSecure/*== DO NOT ANTER ANTH以下任何内容==
      </code>
   <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> “INSERT-MMG-ID-HERE </code> ”-(必需)在您的公司为Adobe Experience Cloud提供您的公司时，此Adobe Experience Cloud组织ID会发送给您的管理员。 </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code>"INSERT-TRACKING-SERVER-HERE"</code> -（必需）您的 Analytics 跟踪服务器。 </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code>"INSERT-SECURE-TRACKING-SERVER-HERE"</code> -（启用 ssl 时必需）您的 Analytics 安全跟踪服务器。 </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> 更新 <code>AppMeasurement.js</code>。 </td> 
   <td colname="col2"> <p>复制 <a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_4351543F2D6049218E18B48769D471E2" format="dita" scope="local">示例 AppMeasurement.js 代码</a>并将其粘贴至 <code>AppMeasurement.js</code> 文件的开头。请至少更新以下变量： </p> 
    <ul id="ul_62FA640BD2604E589650A92158272615"> 
     <li id="li_54E56B483B3A416EA27D7B540D60E39F"> <code> s.account="INSERT-RSID-HERE" </code> </li> 
     <li id="li_00A958289BB045379B436F13287E03D5"> <code> s.trackingServer="INSERT-TRACKING-SERVER-HERE" </code> </li> 
     <li id="li_C0779ADF780440ED876236AEB1FB5DCC"> <code> s.visitorNamespace = "INSERT-NAMESPACE-HERE" </code> </li> 
     <li id="li_93072B656C134D8C89195B7F2D7D8F05"> <code> s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE") </code> </li> 
    </ul> <p> See <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external"> Correctly populate the trackingServer and trackingServerSecure variable </a> or contact Client Care if you are unsure about any of these values. 如果这些值设置错误，那么将无法通过您的实施来收集数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> 托管 <code>AppMeasurement.js</code> 和 <code>VisitorAPI.js</code>。 </td> 
   <td colname="col2"> <p>这些核心 JavaScript 文件必须在一个您的所有站点页面都能访问的 Web 服务器上托管。下一步需要使用这些文件的路径。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> 在所有站点页面上引用 <code>AppMeasurement.js</code> 和 <code>VisitorAPI.js</code>。 </td> 
   <td colname="col2"> <p> 通过将下面一行代码添加至每个页面的 <code>&lt;head&gt;</code> 或 &lt;body&gt; 标记中来加入访客 ID 服务。<code>VisitorAPI.js</code> 必须在 <code>AppMeasurement.js</code> 之前加入： </p> 
    <code class="syntax html">&lt; script language=“JavaScript”type=“text/javascript”src=“https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js”&gt;&lt;/script&gt; </code>
  <p> 通过将下面一行代码添加至每个页面的 <code>&lt;head&gt;</code> 或 <code>&lt;body&gt;</code> 标记中来加入 AppMeasurement for JavaScript： </p> 
    <code class="syntax html">&lt; script language=“JavaScript”type=“text/javascript”src=“https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js”&gt;&lt;/script&gt; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step6_icon.png" id="image_1C4293CA98F04EE2ADA69EAB95BDE8B1" /> </td> 
   <td colname="col1"> 更新并部署页面代码。 </td> 
   <td colname="col2"> <p>复制<a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_042412C29CC249E298F19B2BC2F43CE7" format="dita" scope="local">示例页面代码</a>，并紧跟每个要跟踪的页面上的开始 <code>&lt;body&gt;</code> 标记进行粘贴。请至少更新以下变量： </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // for example, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step7_icon.png" id="image_A423CBF386AF4E5986E8CBB6E31CD3E5" /> </td> 
   <td colname="col1"> 使用 DigitalPulse 调试程序验证数据是否已发送。 </td> 
   <td colname="col2"> <p>安装<a href="../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2" format="dita" scope="local">Adobe Debugger</a> 小书签。安装完成后，载入某个您已部署页面代码的页面，然后打开调试程序。调试程序会显示有关已发送的收集数据的详细信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 缓存 {#section_4E2D1D962DF046418134C43CFC49AD4A}

JavaScript 文件首次加载后会缓存在访客的浏览器中，通常情况下，针对每个会话至多下载一次。即使网站上的每个页面都使用该文件，也不会为每个页面下载它。在大多数网站上，用户在每个会话内平均都会查看多个页面，因此将使用多次的 JavaScript 转移到此文件中可减少总体下载数据量。

## JavaScript for AppMeasurement 压缩 {#section_C10BBC84C81C414088F97363D29E021B}

如果您注重 H 代码的页面大小（AppMeasurement for JavaScript 1.0 已进行预压缩），Adobe 建议您考虑使用 GZIP 压缩文件。所有主要浏览器都支持 GZIP，而且与 JavaScript 压缩相比，其压缩和解压缩核心 [!DNL s_code.js] JavaScript 文件的效率更高。

以下链接可帮助说明在您的网站中如何使用 GZIP 功能压缩 [!DNL s_code.js] JavaScript 代码：

[Apache 模块 mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[通过 Tomcat 和 Flex 启用 gzip 压缩](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
