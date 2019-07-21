---
description: Analytics 中使用的自定义变量列表。
keywords: Analytics 实施
seo-description: Analytics 中使用的自定义变量列表。
seo-title: 自定义变量
solution: Analytics
title: 自定义变量
topic: 开发人员和实施
uuid: 54adf622-7f05-49c0-b7 e6-702bb2 f17 b1 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 自定义变量

Analytics 中使用的自定义变量列表。

<table id="table_E8C7871F63F648A59644638FB56BD0E1"> 
 <thead> 
  <tr> 
   <th class="entry"> 变量 </th> 
   <th class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 流量变量 </td> 
   <td> 检查 prop1 至 75 的值。以下是要检查的项目清单。 
    <ul id="ul_0EE2D50BA90F4F21BD63268A5082F980"> 
     <li id="li_A6E4D66E8A03400491A26A08E4945908">所使用的大小写正确吗？“ValueA”与“valueA”是两个不同的记录。您可以全部使用小写，因为只有极少数的浏览器子集会将所有变量转换为小写。 </li> 
     <li id="li_65CBFB908E7B4ED5AF9518FE5B58D4E2">值的长度是否小于 100 个字符？如果不是，值可能会被截短。 </li> 
     <li id="li_CC506D114AFE44699D89AB84BBCCEBFC"> 单个属性变量中的所有值都相关吗，或是其中有某些值不相关？ </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> 转化变量 </td> 
   <td> <span class="wintitle">Econversion</span> 变量包含 eVar 1 - 75。以下是需要检查的问题清单。 
    <ul id="ul_CA10C5B9F24B4C49A64CA84A9DCE8E63"> 
     <li id="li_8CCD92F3AD5E49EBA91C9B008DA47016">所使用的大小写正确吗？“ValueA”与“valueA”是两个不同的记录。您可以全部使用小写，因为只有极少数的浏览器子集会将所有变量转换为小写。 </li> 
     <li id="li_5B6FDEDB2C32409AA59D6BB0DF2346CB">值的长度是否小于 255 个字符？如果不是，值可能会被截短。 </li> 
     <li id="li_C31AFBAC99D84E96A1244E795CE7765D">单个 eVar 中的所有值都相关吗，或是其中有某些值不相关？ </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> 自定义事件 </td> 
   <td> 事件包含标准值（<span class="wintitle">prodView</span>、<span class="wintitle">scOpen</span>、<span class="wintitle">scAdd</span>、<span class="wintitle">scCheckout</span>、<span class="wintitle">purchase</span>），以及从 event1 到 event100 的自定义事件。所有事件都以 events 变量发送。同一页面上的多个事件应以逗号隔开（无空格）。 
    <ul id="ul_2213CC9DE892433FAF6FC1F5A2B841B4"> 
     <li id="li_15E31A9FF1654DFA93C158F422B9EAE3">对于所有标准转化事件，products 同样应以适用的产品加以填充。对于除 purchase 之外的所有事件，可选项包括 qty 和 price 元素。 </li> 
     <li id="li_03ED9AAC45DA47A58AB482E2CEBF5108">对于<span class="wintitle"> purchase </span>事件，一次会话中只能设置一次，并且必须在购买完成并得到确认后进行。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

