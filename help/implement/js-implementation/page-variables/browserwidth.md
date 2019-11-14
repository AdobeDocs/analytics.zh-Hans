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



# browserWidth

 变量显示浏览器窗口的宽度。

<!-- 

browserwidth.xml

 -->

此变量填充在页面代码之后，运行 *`doPlugins`* 之前。

> [!NOTE]此变量只可读取，不得设置。

您可以读取这些值，并将它们复制到 prop/eVar，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

**参数**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>查询参数</b> </p> </td> 
   <td> <p> <b>值</b> </p> </td> 
   <td> <p> <b>示例</b> </p> </td> 
   <td> <p> <b>受影响的报表</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>正整数 </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>“流量”&gt;“技术”&gt;“浏览器宽度” </p> </td> 
  </tr> 
 </tbody> 
</table>
