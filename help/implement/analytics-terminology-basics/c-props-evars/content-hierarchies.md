---
description: 内容层级的常见用法是显示访客到达某个页面、级别等时经过的不同路径。
keywords: Analytics实施；内容层次结构；Hier
seo-description: 内容层级的常见用法是显示访客到达某个页面、级别等时经过的不同路径。
seo-title: 计算内容层次结构
solution: Analytics
title: 计算内容层次结构
topic: 开发人员和实施
uuid: d41df92d-65fb-44de-bf46-8fac24303 add
translation-type: tm+mt
source-git-commit: 1bc1c7a1e00d7b59cd39f368ac9afb745bea9e47

---


# 计算内容层次结构

内容层级的常见用法是显示访客到达某个页面、级别等时经过的不同路径。

**我应该如何跟踪我的[!UICONTROL 内容层级]？**

您必须首先了解跟踪[!UICONTROL 内容层级]的报表要求。如果对跟踪内容层级的要求非常详细，通常建议使用层级&#x200B;*`hier`*) 建议使用变量。层级通常需要严格的预定义分类法，其中同一子节点极少会存在于多个父节点下。请仔细研究下面的示例：

[!UICONTROL 全局层级]

“所有网站”&gt;“区域”&gt;“国家/地区”&gt;“语言”&gt;“类别”

在本示例中，层级开始在语言级别划分。如果需要报告总“English”流量，可能会遇到问题，因为 English 在 USA、England、Australia 等之下。层级只允许向下钻取数据。要在多个层级中横向划分，最佳实践是使用[!UICONTROL 自定义流量变量] (prop)。

如果希望为用户提供向下钻取网站数据的功能（类似于用户浏览网站的方式）并在层级的每个级别报告[!UICONTROL 独特访客]，建议使用层级变量。

有时，可以同时使用 prop 和&#x200B;*`hier`*&#x200B;变量。以下是每种变量类型支持的 prop：

<table id="table_E960D100DA0F433A94A4B246D6EF0D0A"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> Prop </th> 
   <th class="entry"> hier </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 关联 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2A70A61A78024204B6CEE4FFF9A0851E" /> </p> </td> 
  </tr> 
  <tr> 
   <td> 路径分析 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_EE5ED36AC75F4D648F54858D796F82BD" /> </p> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 页面查看 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_5BB82776D41642E78C2ECFD71DD33164" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_18F34EE8957946AF9D6C2C9B492CEDB7" /> </p> </td> 
  </tr> 
  <tr> 
   <td> 独特访客 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_A475267547B94DB4A1EEFD903B2CA1EB" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_1E9E302D999146128CDBCE13E52BC38C" /> </p> </td> 
  </tr> 
  <tr> 
   <td> 分类 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_FC5FEFE7BA8C4475BA4F31D57302BE6B" /> </p> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

