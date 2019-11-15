---
description: 在 Activity Map 或旧版 ClickMap 中，停止链接跟踪的步骤。
solution: Analytics
title: 停止链接跟踪
topic: Activity map
uuid: e17fb7bd-d6ed-45c3-a006-9150d5718cff
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
   <td colname="col2"> 从 Appmeasurement.js 文件删除以下内容： 
    <code>
     /*
     &nbsp;START&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;The&nbsp;following&nbsp;module&nbsp;enables&nbsp;Activity&nbsp;Map&nbsp;tracking&nbsp;in&nbsp;Adobe&nbsp;Analytics.&nbsp;Activity&nbsp;Map
     &nbsp;allows&nbsp;you&nbsp;to&nbsp;view&nbsp;data&nbsp;overlays&nbsp;on&nbsp;your&nbsp;links&nbsp;and&nbsp;content&nbsp;to&nbsp;understand&nbsp;how
     &nbsp;users&nbsp;engage&nbsp;with&nbsp;your&nbsp;web&nbsp;site.&nbsp;If&nbsp;you&nbsp;do&nbsp;not&nbsp;intend&nbsp;to&nbsp;use&nbsp;Activity&nbsp;Map,&nbsp;you
     &nbsp;can&nbsp;remove&nbsp;the&nbsp;following&nbsp;block&nbsp;of&nbsp;code&nbsp;from&nbsp;your&nbsp;AppMeasurement.js&nbsp;file.
     &nbsp;Additional&nbsp;documentation&nbsp;on&nbsp;how&nbsp;to&nbsp;configure&nbsp;Activity&nbsp;Map&nbsp;is&nbsp;available&nbsp;at:
     &nbsp;https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
     */
     function&nbsp;AppMeasurement_Module_Activity&nbsp;Map(g){func
     ...
     /*&nbsp;END&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;*/
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap（旧称访客 ClickMap） </td> 
   <td colname="col2"> <p>将 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html"  >trackInlineStats</a> 变量设置为 false（这是默认设置）。语法如下所示：
     <code>
       s.trackInlineStats=false
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

