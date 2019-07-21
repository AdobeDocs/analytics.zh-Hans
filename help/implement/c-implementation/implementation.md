---
description: 'null'
seo-description: 'null'
seo-title: 实施路线图
title: 实施路线图
uuid: 988bcca5-67e-4e3f-97e6-6a42030b1962
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 实施路线图

## 新用户 {#section_77433E4FC5ED4C6BAFC1E72EB61C4503}

如果您是 Adobe Analytics 的新用户，可以使用 [Adobe Analytics 快速入门](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/)指南快速创建您的首个 Analytics 报表包（数据存储库）。Then, you can deploy Analytics code using [Experience Platform Launch](https://docs.adobelaunch.com/).

## 实施路线图 {#section_E3DD8D199B744FFB9E9B386A44220206}

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
   <td colname="col1"> 选择一种实施方法。 </td> 
   <td colname="col2"> <p>实施 Analytics 的常见方法包括： </p> <p> 
     <ul id="ul_A7475867861540EFBD77AEE8C6DAD418"> 
      <li id="li_035E2619670F4D04A7F708625A9C01EF"> <a href="https://docs.adobelaunch.com/" format="https" scope="external"> Experience Platform Launch( </a> 推荐) <p>本指南向您介绍了有关如何使用 Adobe 网站标签和移动 SDK 管理功能以及如何实施这些功能的所有所需信息。 </p> </li> 
      <li id="li_996FA2F5B0E149399CED391AB5235D8A"> <a href="../../implement/c-implement-with-dtm/dtm-implementation-overview.md" format="dita" scope="local"> Dynamic Tag Management </a> <p>本指南中包含特定于 Analytics 的信息，可引导您完成动态标签管理实施。 </p> </li> 
      <li id="li_18E6AD6D864246D0BA26DAA1D91DD811"> <a href="../../implement/js-implementation/javascript-implementation-overview.md" format="dita" scope="local"> JavaScript </a> <p>本指南包含数据收集变量的说明以及有关在 JavaScript 中实施数据收集代码的详细信息，包括<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_js" format="https" scope="external">视频</a>。 </p> </li> 
      <li id="li_85EC7A0AC5E04EE6981ED72A88C5D1FD"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html" format="html" scope="external"> Analytics SDK </a> <p>使用 Analytics SDK 可管理： </p> <p> 
        <ul id="ul_F67F2E1964724800A84445A36DFB8E86"> 
         <li id="li_9C43F051EB5B4EA7A4C14EC1513DB824"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/analytics_main.html" format="html" scope="external"> iOS 上的移动设备应用程序 </a> </li> 
         <li id="li_4354E44EB8B3494A88578C1621EF5BAC"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/analytics_main.html" format="html" scope="external"> Android 上的移动设备应用程序 </a> </li> 
        </ul> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> 设置标识服务。 </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Identity Service for Analytics </a>. </p> 
    <draft-comment> 
     <p>在 <code>VisitorAPI.js</code> 中，将以下访客 ID 初始化代码添加至文件开头： </p> 
     <code class="syntax javascript">var rector= Performator. getInstance(“INSERT-MCORG-ID-HERE”)；
folder. trackingServer=“INSERT-TRANING-SERVER-HERE”；//与s. trackingServer相同
folder. trackingServerSecure=“INSERT-Secure-TRANING-SERVER-HERE”；//sameas s. trackingServerSecure
/*
==============请勿更改此Line下的任何内容！============= </code>
  
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> “INSERT-MMG-ID-HERE </code> ”-(必需)在您的公司为Adobe Experience Cloud提供您的公司时，此Adobe Experience Cloud组织ID会发送给您的管理员。 </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code>"INSERT-TRACKING-SERVER-HERE"</code> -（必需）您的 Analytics 跟踪服务器。 </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code>"INSERT-SECURE-TRACKING-SERVER-HERE"</code> -（启用 ssl 时必需）您的 Analytics 安全跟踪服务器。 </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> 使用选定的实施方法更新和部署页面代码。 </td> 
   <td colname="col2"> <p>紧跟每个要跟踪的页面上的开始 <code>&lt;body&gt;</code> 标签放置页面代码。请至少更新以下变量： </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // for example, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> 验证实施。 </td> 
   <td colname="col2"> <p> <a href="../../implement/impl-testing/impl-validation/impl-validation.md" format="dita" scope="local">测试和验证</a>提供了有关如何验证实施的信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> 使用 Adobe Experience Cloud 调试器验证数据是否已发送。 </td> 
   <td colname="col2"> <p>Install the <a href="../../implement/impl-testing/debugger.md#topic_E05CEAF0682E483A9AB147D774CF2188" format="dita" scope="local"> Experience Cloud Debugger </a>. 安装完成后，载入某个您已部署页面代码的页面，然后打开调试程序。调试程序会显示有关已发送的收集数据的详细信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 更多信息 {#section_64B6A948DF4A4B5E9E1D22549F8C508B}

For information about the differences between [!UICONTROL Experience Platform Launch], [!UICONTROL Dynamic Tag Management], and JavaScript methods, see [Choose an Implementation Method](../../implement/c-implementation-methods/choose-implementation-method.md#concept_97CE27B16410422EB28B4B9CE3B9529B).

有关入门流程的简要概述以及有关快速设置首个 Analytics 报表包的帮助，请参阅“Analytics 快速入门”指南中的 [Analytics 实施快速入门](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html)。
