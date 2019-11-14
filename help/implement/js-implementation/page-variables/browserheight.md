---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# browserHeight

 变量显示浏览器窗口的高度。

<!-- 
browserheight.xml
-->

此变量填充在页面代码之后，运行 *`doPlugins`* 之前。

> [!NOTE]此变量只可读取，不得设置。

您可以读取这些值，并将它们复制到 prop/eVar，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

**参数**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> 查询参数 </th> 
   <th class="entry"> 值 </th> 
   <th class="entry"> 示例 </th> 
   <th class="entry"> 受影响的报表 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>正整数 </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>“流量”&gt;“技术”&gt;“浏览器高度” </p> </td> 
  </tr> 
 </tbody> 
</table>

