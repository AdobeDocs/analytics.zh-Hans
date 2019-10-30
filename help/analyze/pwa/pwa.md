---
title: PWA for Analytics
seo-title: PWA for Analytics
description: 用于Adobe Analytics的渐进式Web应用程序
seo-description: 将PWA与Analytics结合使用
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# PWA for Analytics

本指南介绍如何将Adobe Analytics与渐进式Web应用程序(PWA)结合使用。

## 简介

PWA可以为网站提供本机应用程序体验以及脱机功能。 通常，PWA包括服务工作者、缓存配置和清单文件，所有这些都有助于加快加载时间、简化导航和响应式行为。

Adobe Analytics与PWA一样，与传统网站一样顺畅地运行。 尽管PWA对于其自身行为的渐进性要求更高，但在Analytics收集或报告数据的方式方面，它们并不会与传统网站有任何不同，因此也不存在任何障碍或限制。 事实上，由于Analytics已经包含离线跟踪功能，因此PWA可以帮助您比使用传统网站更轻松地利用这一内置功能。

## 获取PWA分析数据

要使用Analytics收集和分析PWA数据，您无需进行任何配置更改。 Analytics自动提供与传统网站相同的所有功能和功能。

## 添加离线跟踪以提高PWA有效性

您可以使用Analytics离线跟踪功能提高PWA [的有效性](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) 。 默认情况下，此功能处于关闭状态，但您可以将以下属性添加到AppMeasurement.js文件以将其打开： `s.trackOffline=true;`.

例如，在以下AppMeasurement.js文件中，该属性将添加到以下末尾 `CONFIG SECTION`:

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


有关编辑AppMeasurement.js文件的详细信息，请参 [阅将代码插入AppMeasurement.js文件](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)。

有关AppMeasurement.js文件中的配置示例，请参 [阅配置AppMeasurement.js文件](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)。

有关AppMeasurement.js文件特性的详细信息，请参阅 [Javascript实施概述](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。
