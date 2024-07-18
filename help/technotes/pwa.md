---
title: 适用于 Analytics 的 PWA
description: 适用于 Adobe Analytics 的渐进式 Web 应用程序
role: User, Admin
feature: Progressive Web Apps
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 100%

---

# 适用于 Adobe Analytics 的 PWA

本页介绍如何将 Adobe Analytics 与渐进式 Web 应用程序 (PWA) 结合使用。

## 简介

PWA 可以为网站提供本机应用程序体验和脱机功能。PWA 通常包括服务工作进程、缓存配置和清单文件，所有这些都有助于加快加载时间、简化导航和改善响应行为。

Adobe Analytics 可以像与传统网站结合使用一样，无缝地与 PWA 结合使用。尽管 PWA 对于其自身的渐进式行为要求较高，但它与传统网站没有任何不同，不会对 Analytics 从中收集或报告数据的方式制造任何障碍或限制。事实上，由于 Analytics 已经包含离线跟踪功能，因此 PWA 可以帮助您采用比传统网站更轻松的方式利用这项内置功能。

## 获取 PWA Analytics 数据

要使用 [!UICONTROL Analytics] 收集和分析 PWA 数据，您无需进行任何配置更改。[!UICONTROL Analytics] 会自动提供与传统网站结合使用时相同的所有功能和特性。

## 添加离线跟踪以提高 PWA 有效性

您可以将 Adobe Analytics [离线跟踪功能](/help/implement/vars/config-vars/trackoffline.md)与 PWA 结合使用，以提高其有效性。默认情况下，此功能处于关闭状态，但您可以将以下属性添加到 AppMeasurement.js 文件中以打开此功能：`s.trackOffline=true;`。

例如，在以下 AppMeasurement.js 文件中，将该属性添加到 `CONFIG SECTION` 的末尾：

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

有关配置 AppMeasurement.js 文件的更多信息，请参阅[配置变量概述](/help/implement/vars/config-vars/configuration-variables.md)和同一子章节中特定于单个变量的页面。

有关 AppMeasurement.js 文件的特征的更多信息，请参见 [JavaScript 实现概述](/help/implement/js/overview.md)。
