---
description: 在 Activity Map 或旧版 ClickMap 中，停止链接跟踪的步骤。
seo-description: 在 Activity Map 或旧版 ClickMap 中，停止链接跟踪的步骤。
seo-title: 停止链接跟踪
solution: Analytics
title: 停止链接跟踪
topic: Activity Map
uuid: e17fb7bd-d6 ed-45c3-a006-9150d5718 cff
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 停止链接跟踪

在 Activity Map 或旧版 ClickMap 中，停止链接跟踪的步骤。

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要在此处停止链接跟踪... </th> 
   <th colname="col2" class="entry"> 执行此操作... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> 从 Appmeasurement.js 文件删除以下内容：<code>/*起始活动地图模块下一模块在Adobe Analytics中启用活动地图跟踪。活动地图允许您查看链接和内容上的数据叠加，以了解用户如何与您的网站互动。如果您不打算使用Activity Map，则可以从AppMeasurement. js文件中删除以下代码块。
  Additional documentation on how to configure Activity Map is available at:
      https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
     */
     function AppMeasurement_Module_Activity Map(g){func
     ...
     /* END Activity Map MODULE */
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap（旧称访客 ClickMap） </td> 
   <td colname="col2"> <p>将 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="https" scope="external">trackInlineStats</a> 变量设置为 false（这是默认设置）。The syntax reads as follows: 
     <code>
       s.trackInlineStats=false
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

