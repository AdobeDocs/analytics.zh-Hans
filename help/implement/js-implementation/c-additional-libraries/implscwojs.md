---
description: 用 HTML 图像标记实施 Analytics（硬编码图像请求）。
keywords: Analytics实施；html图像标签；硬编码图像请求
seo-description: 用 HTML 图像标记实施 Analytics（硬编码图像请求）。
seo-title: 使用HTML图像标签实施Analytics
solution: Analytics
title: 使用HTML图像标签实施Analytics
topic: 开发人员和实施
uuid: 0c098a57-7c71-4362-812c-36e37848a5ae
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用HTML图像标签实施Analytics

用 HTML 图像标记实施 Analytics（硬编码图像请求）。

然后浏览器请求图像。数据通过图像请求查询字符串中的变量随此图像请求一起移动。JavaScript 将浏览器级别的变量与页面级别的变量相结合，形成全面的数据收集解决方案。有些情况下，适合使用完全由服务器创建的图像标记。下面列出了基于 JavaScript 的实施的标准元素：

<table id="table_20BBE4387F234CF199E6C99741AF265C"> 
 <tbody> 
  <tr> 
   <td> HTML 代码 </td> 
   <td> 此部分由 JavaScript 代码组成，被放置在设置 JavaScript 变量值的 HTML 页面（或模板）中。 </td> 
  </tr> 
  <tr> 
   <td> JavaScript 库 </td> 
   <td> <p>此文件包含常用代码： </p> 
    <ul id="ul_ED50D66F2B2B476E8D9063099995998D"> 
     <li id="li_E88F6F28EC8946469ADCEAFF2F0A4EBA">查询浏览器获取有关各种属性的信息，如 JavaScript 版本、操作系统版本、所用显示器的大小和分辨率，及其他变量 </li> 
     <li id="li_5CEBE37709D943B7921447FA7054A565">编码所有变量并连接到一个图像请求 (&lt;img&gt;)，以将这些变量传输到数据收集服务器。然后引用加载并执行的 JavaScript 库文件。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> &lt;noscript&gt; 标记 </td> 
   <td> &lt;noscript&gt; 标记中放置简化版的图像请求，在用户已禁用 JavaScript 或没有 JavaScript 功能时执行。此部分实施是可选的，一般适用于约 2% 的 Internet 用户。 </td> 
  </tr> 
 </tbody> 
</table>

JavaScript 可以检测不适用于服务器的浏览器设置，如浏览器窗口高度/宽度、显示器分辨率和 Netscape 插件。通过使用服务器端方法创建图像标记，将无法捕获这些变量。JavaScript 在图像请求中设置随机数以克服浏览器和代理服务器缓存。这样即可以准确跟踪所有页面查看。在特定情况下，服务器端代码优于基于 JavaScript 的代码，其好处包括：

* JavaScript 非常准确 (98-100%)。有时，所需的准确度极高，甚至用户会在 JavaScript 执行前快速点击另一个页面。通过服务器端创建图像标记可以将准确度级别提升几个百分点。
* 对于包含购买在内的跟踪转化事件，准确性相当重要。
* 此策略还可用于完整填充 <noscript> 用于跟踪不带JavaScript的用户或禁用JavaScript的用户。

>[!NOTE]
>
>使用服务器生成的图像标签需要额外的时间执行，并且更难以调试、部署和维护。Adobe 强烈鼓励客户尽可能在每个页面上使用基于 JavaScript 的数据收集。使用此实施方法无法收集或不支持各种报表和功能，其中包括访客点击图、下载链接、退出链接和基于浏览器的变量（浏览器宽度/高度等）。

