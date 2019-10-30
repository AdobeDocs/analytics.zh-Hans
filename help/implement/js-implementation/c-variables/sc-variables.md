---
description: Analytics 提供了多个变量来收集 Analytics 数据。例如，pageName 变量中的值是将报告的网页的名称。本部分列出了 AppMeasurment 支持的变量。
keywords: Analytics 实施;Appmeasurement 变量
seo-description: Analytics 提供了多个变量来收集 Analytics 数据。例如，pageName 变量中的值是将报告的网页的名称。本部分列出了 AppMeasurment 支持的变量。
seo-title: 变量概述
solution: Analytics
subtopic: 变量
title: 变量概述
topic: 开发人员和实施
uuid: 067d0135-572a-4a44-af9e-445d3c4e9271
translation-type: ht
source-git-commit: 40e9872126114588961a1e84e6be85bb945050a4

---


# 变量概述

Analytics 提供了多个变量来收集 Analytics 数据。例如，pageName 变量中的值是将报告的网页的名称。本部分列出了 AppMeasurement 支持的变量。

有关页面变量的详细信息，请转到[此处](/help/implement/js-implementation/c-variables/page-variables.md)。
有关配置变量的详细信息，请转到[此处](/help/implement/js-implementation/c-variables/configuration-variables.md)。

## 如何设置变量 {#section_E52CF9E8FDF74164A1511E0D9D31884D}

AppMeasurement 要求在初次调用 track 函数 *`t()`* 之前设置所有配置变量。如果在调用 *`t()`* 之后设置配置变量，则可能会发生意外结果。

配置变量在 *`doPlugins`* 函数中设置，该函数在执行 track 函数时调用。导致此问题的特定配置变量为 *`trackInlineStats`*，该变量会启用 ClickMap 数据收集。这会让 ClickMap 模块处于不确定的状态，导致首个跟踪调用会在 Adobe Analytics 信标后面附加“未定义”字符串，进而影响货币代码。

要解决此问题，请将所有配置变量移到 doPlugins 函数前面。

```
/************************** CONFIG SECTION **************************/ 
/* Ensure these variables are correct before deploying */ 
var s_account="[INSERT-REPORT-SUITE-ID-HERE]" 
var s=s_gi(s_account) 
s.trackingServer="[INSERT-TRACKING-SERVER-HERE]" 
s.visitorNamespace="[INSERT-VISITOR-NAMESPACE-HERE]" 
s.charSet="ISO-8859-1" 
s.currencyCode="USD" 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" 
s.linkInternalFilters="javascript:,three,two,one,dev16,.,nike" 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.debugTracking=true 
 
s.usePlugins=true; 
function s_doPlugins(s) { 
    //add your custom plugin code here 
} 
s.doPlugins=s_doPlugins; 
 
/* 
============== DO NOT ALTER ANYTHING BELOW THIS LINE ! =============== 
 
AppMeasurement for JavaScript version: 1.5.3 
Copyright 1996-2016 Adobe, Inc. All Rights Reserved 
More info available at https://www.omniture.com 
*/ 
function AppMeasurement(){var a=this;a.version="1.5.3";var k=window;k.s_c_in||(k.s_c_il=[],k.s_c_in=0);a._il=k.s_c_il;a._in=k.s_c_in;a._il[a._in]=a;k.s_c_in++;a._c="s_c";var q=k.AppMeasurement.zb;q||(q=null);var r=k,n,t;try{for(n=r.parent,t=r.location;n&&n.location&&t&&""+n.location!=""+t&&r.location&&""+n.location!=""+r.location&&n.location.host==t.host;)r=n,n=r.parent}catch(u){}a.ob=function(a){try{console.log(a)}catch(b){}};a.za=function(a){return""+parseInt(a)==""+a};a.replace=function(a,b,d){return!a|| 
0>a.indexOf(b)?a:a.split(b).join(d)};a.escape=function(c){var b,d;if(!c)return c;c=encodeURIComponent(c);for(b=0;7>b;b++)d="+~!*()'".substring(b,b+1),0<=c.indexOf(d)&&(c=a.replace(c,d,"%"+d.charCodeAt(0).toString(16).toUpperCase()));return c};a.unescape=function(c){if(!c)return c;c=0<=c.indexOf("+")?a.replace(c,"+"," "):c;try{return decodeURIComponent(c)}catch(b){}return unescape(c)};a.gb=function(){var c=k.location.hostname,b=a.fpCookieDomainPeriods,d;b||(b=a.cookieDomainPeriods);if(c&&!a.cookieDomain&& 
```

