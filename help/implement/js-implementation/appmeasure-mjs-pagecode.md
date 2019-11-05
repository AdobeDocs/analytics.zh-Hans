---
description: 本部分包含您的核心 JavaScript 文件及站点页面的示例代码。
keywords: Analytics 实施;appmeasurement.js 代码;页面代码示例
seo-description: 本部分包含您的核心 JavaScript 文件及站点页面的示例代码。
seo-title: 示例页面代码和全局配置
solution: Analytics
subtopic: JavaScript AppMeasurement
title: 示例页面代码和全局配置
topic: 开发人员和实施
uuid: e8880d77-172b-42e5-8187-ce371aa9eff9
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# 示例页面代码和全局配置

本部分包含您的核心 JavaScript 文件及站点页面的示例代码。

>[!IMPORTANT]
>
>此示例使用访客 ID 服务，该服务将作为 [JavaScript 实施](/help/implement/js-implementation/javascript-implementation-overview.md) 的一部分部署。如果在将访客 API JavaScript 文件加入所有站点页面前已经在 AppMeasurement 中启用了访客 ID 服务，则会导致重复的访客计数。要避免出现重复的访客计数，必须了解并遵循 [访客 ID 服务](/help/implement/js-implementation/c-unique-visitors/visid-service.md).

## 示例 AppMeasurement.js 代码 {#section_4351543F2D6049218E18B48769D471E2}

>[!IMPORTANT]
>
>配置变量应在 *`doPlugins`* 函数上方设置。

对于新的实施，您可以首先在 AppMeasurement.js 开头粘贴以下全局配置代码：

```js
//initialize AppMeasurement 
var s_account="INSERT-RSID-HERE" 
var s=s_gi(s_account) 
 
/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/ 
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE") 
 
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
 
/* uncomment below to use doPlugins */ 
/* s.usePlugins=true 
function s_doPlugins(s) { 
 
// use implementation plug-ins that are defined below 
// in this section. For example, if you copied the append 
// list plug-in code below, you could call: 
// s.events=s.apl(s.events,"event1",",",1); 
 
} 
s.doPlugins=s_doPlugins */ 
 
/* WARNING: Changing any of the below variables will cause drastic 
changes to how your visitor data is collected.  Changes should only be 
made when instructed to do so by your account manager.*/ 
s.trackingServer="INSERT-TRACKING-SERVER-HERE" 
s.trackingServerSecure="INSERT-SECURE-TRACKING-SERVER-HERE" 
 
/************************** PLUGINS SECTION *************************/ 
 
// copy and paste implementation plug-ins here - See "Implementation Plug-ins" @ 
// https://marketing.adobe.com/resources/help/en_US/sc/implement/#Implementation_Plugins 
// Plug-ins can then be used in the s_doPlugins(s) function above  
 
/****************************** MODULES *****************************/ 
 
// copy and paste implementation modules (Media, Integrate) here 
// AppMeasurement_Module_Media.js - Media Module, included in AppMeasurement zip 
// AppMeasurement_Module_Integrate.js - Integrate Module, included in AppMeasurement zip 
 
/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  
```

## 示例页面代码 {#section_042412C29CC249E298F19B2BC2F43CE7}

对于新的实施，您可以将以下页面代码粘贴到页面上要跟踪的开始 <body> 标记后：

```js
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
var s_code=s.t();if(s_code)document.write(s_code)//--></script>
```

请务必在每个页面上也加入 `AppMeasurement.js` 和 `VisitorAPI.js` 的引用。请参阅 [JavaScript 实施](/help/implement/js-implementation/javascript-implementation-overview.md)获取相关说明。
