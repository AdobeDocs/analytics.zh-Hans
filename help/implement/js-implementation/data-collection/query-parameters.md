---
description: 下表列出的查询参数包含每个要发送到数据收集的分析变量的值。
keywords: Analytics 实施
seo-description: 下表列出的查询参数包含每个要发送到数据收集的分析变量的值。
seo-title: 数据收集查询参数
solution: Analytics
title: 数据收集查询参数
topic: 开发人员和实施
uuid: 4d5af486-df27-42fe-bb9c-28938dddf2b2
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 数据收集查询参数

下表列出的查询参数包含每个要发送到数据收集的分析变量的值。

可使用该信息的情况包括使用[数据包分析程序](../../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258)进行调试、手动构建图像请求或使用[动态变量](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262)。

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> 参数 </th> 
   <th class="entry"> Analytics 变量 </th> 
   <th class="entry"> 已填充的报表 </th> 
   <th class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> 无 </td> 
   <td colname="col3"> 无 </td> 
   <td colname="col4"> Audience Manager 位置提示（用于 Experience Cloud 共享配置文件集成） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> 无 </td> 
   <td colname="col3"> 无 </td> 
   <td colname="col4"> Audience Manager Blob（用于 Experience Cloud 共享配置文件集成） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> 无 </td> 
   <td colname="col3"> 无 </td> 
   <td colname="col4"> Analytics 访客 ID </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> 无 </td> 
   <td> 无 </td> 
   <td> 指示图像请求的开始 </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> 无 </td> 
   <td> 无 </td> 
   <td> 指示图像请求的结束，这表明该请求未被截断 </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | 浏览器高度 </td> 
   <td> 浏览器窗口高度（像素） </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | 浏览器宽度 </td> 
   <td> 浏览器窗口宽度（像素） </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | 显示器颜色深度 </td> 
   <td> 颜色质量（位） </td> 
  </tr> 
  <tr> 
   <td> </td><td><p></p></td><td><p></p></td><td><p></p><p><code> &lt;my.a&gt;red&lt;/my.a&gt; </code></p><p></p><p><code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code></p><p><code> my.a = red </code></p><p><code> c.&my.a=red </code></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td><code> D </code></td><td></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p><code> t </code></p><code>
      dd/mm/yyyy&amp;nbsp;hh:mm:ss&amp;nbsp;D&amp;nbsp;OFFSET 
    </code><p><code> 0-6 </code><code> OFFSET </code></p><code>
      offset&amp;nbsp;from&amp;nbsp;GMT&amp;nbsp;in&amp;nbsp;hours&amp;nbsp;*&amp;nbsp;60&amp;nbsp;*&amp;nbsp;-&amp;nbsp;1 
    </code><p></p><code>
      23/09/2016&amp;nbsp;14:00:00&amp;nbsp;1&amp;nbsp;420 
    </code></td></tr><tr><td><code> ts </code></td><td><p></p></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td><p></p></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p></p></td></tr></tbody></table>

