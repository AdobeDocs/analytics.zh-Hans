---
title: 用于Analytics的PAs
seo-title: 用于Analytics的PAs
description: Adobe Analytics渐进式Web应用程序
seo-description: 将PAs与Analytics结合使用
translation-type: tm+mt
source-git-commit: f64e5d9977bebd0e9db4af0f7118e9e64978c1c7

---


# 用于Analytics的PAs

本指南介绍如何将Adobe Analytics与渐进式Web应用程序(PASE)结合使用。

## 简介

PASE可以为网站提供本机应用程序体验以及离线功能。通常PAs包括服务工作者、缓存规定和清单文件，所有这一切都可以帮助您更快地加载加载时间、更轻松地导航和响应行为。

Adobe Analytics与传统网站一样无缝地使用PAs。虽然Pas有一些额外的行为要求，它们本身并不存在任何障碍，但对于Analytics收集或报告数据的方式与传统网站有任何不同。事实上，由于Analytics已经包含离线跟踪功能，因此PASE能够比传统网站更方便地利用这一内置功能。

## 获取您的PWA Analytics数据

要使用Analytics收集和分析您的PWA数据，您无需进行任何配置更改。Analytics自动提供与传统网站相同的功能和功能。

## 添加离线跟踪以提高PWA有效性

您可以使用Analytics [离线跟踪功能](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) 来提高PWA的有效性。默认情况下，此功能处于关闭状态，但您可以将以下属性添加到AppMeasurement. js文件以将其打开： `s.trackOffline=true;`。

例如，在下面的AppMeasurement. js文件中，该属性添加 `CONFIG SECTION`到：

```
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
s.trackOffline=true
***
    
```


有关编辑AppMeasurement. js文件的更多信息，请参阅 [将代码插入AppMeasurement. js文件](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)。

有关AppMeasurement. js文件中的配置示例，请参阅 [配置AppMeasurement. js文件](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)。

有关AppMeasurement. js文件特性的更多信息，请参阅 [Javascript实施概述](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。
