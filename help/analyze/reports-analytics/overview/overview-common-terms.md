---
description: 有关市场营销报告中常用 Web 分析术语的介绍。
seo-description: 有关市场营销报告中常用 Web 分析术语的介绍。
seo-title: 常用术语
solution: Analytics
title: 常用术语
topic: Reports & Analytics
uuid: 0560dc7d-9f92-46d4-848b-3cf297073382
translation-type: tm+mt
source-git-commit: bf9152741507c75e1f92e8d5d515127eadf5d590

---


# 常用术语{#common-terms}

常用Adobe Analytics条款的简介。

<table id="table_58F5D292485F45F9902B372E4E1E3103"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 术语 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 报表包 </p> </td> 
   <td colname="col2"> <p>报表包定义所选网站、网站集，或网站页面子集的完整独立报告。通常情况下，报表包是一个网站，但也可能是为获得总数而合并若干个网站数的全局区段。另外，报表包也可能比网站小（如果是对网站的一部分运行报表）。 </p> <p>例如，如果登录用户和非登录用户以不同方式使用网站，且有不同人查看每个群组的相关报表，可以根据需要验证的页面和不需要验证的页面对报表包分类。 </p> <p>当您登录时，可以选择一个要使用的报表包（使用组合报表包的汇总报表包时除外）。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>量度 </p> </td> 
   <td> <p>有关网站活动的量化信息，包括查看次数、点击量、重新加载次数、平均逗留、时间、日期和件数等。 </p> <p>有关详细信息，请参阅 <a scope="local" href="../../../analyze/reports-analytics/metrics.md#concept_EB00207C07BD4481AB116E62EC24E686" type="concept" format="dita"> 量度</a>. </p> </td> 
  </tr> 
  <tr> 
   <td> <p> 维度 </p> </td> 
   <td> <p>可以查看和比较的量度数据的描述或特性，例如性别、月份、年份、忠诚度、显示器分辨率等。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p> 报表 </p> </td> 
   <td> <p>市场营销报告功能的基础。您可以对收集的所有数据运行在线报表。 </p> <p>有关详细信息，请参阅 <a href="../../../analyze/reports-analytics/reports.md#concept_54DA0D426E2B49F3BF0E707FE83932A6" type="concept" format="dita" scope="local"> 报表类型</a>. </p> </td> 
  </tr> 
  <tr> 
   <td> <p> 页面查看 </p> </td> 
   <td> <p>访客浏览器中加载的单个网页。一次页面查看是指执行一次该页面的 JavaScript。即使访客频繁刷新页面或使用<span class="uicontrol">返回</span>和<span class="uicontrol">重新加载</span>浏览器按钮，系统仍能准确计算页面加载次数。页面查看计算整个页面，而不是个别元素或点击。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>访问 </p> </td> 
   <td> <p>表示一系列的页面查看操作。访问仅会在 30 分钟不活动或 12 小时持续活动后结束。（此时间测量是 Web 分析行业标准。）访问量是通过 Cookie 进行跟踪的。访问从访客访问页面开始。一次访问有时是指一个<span class="term"> 会话</span>，但它不是浏览器会话。转到其他网站、关闭浏览器甚至重新启动计算机并不结束访问。 </p> <p> 如果在访客阅读网页时发生不活动状态超时，则该访问将结束并被处理。新访问在访客点进另一页面时开始。 </p> <p>如果在访问期间日期改变，如在午夜访问网站，该访问将属于访问开始的那一天。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p> 页面查看次数 </p> </td> 
   <td> <p>“独特访客”报表指示在所选时间内访问网站的不同访客人数。有六种不同的“独特访客”报表： </p> 
    <ul id="ul_863B8DE8B9E74DE4A93C2C2931EEFB6D"> 
     <li id="li_21C835B71EF64B4DA821B674416C8B85">每小时 </li> 
     <li id="li_36A498AE7D7A455C8DEB3AA0F025B597">每日 </li> 
     <li id="li_30F26F8DAC664E1FA823B7BDDB7B0F8B">每周 </li> 
     <li id="li_09263F6B1E114A8DB477793B560A0417">每月 </li> 
     <li id="li_A0B2CA3D44564045B02B55AF6E392F76">每季 </li> 
     <li id="li_296BC5B02921460690F35128B1192800">每年 </li> 
    </ul> <p>尽管访客可能在特定时段内访问网站多次，但“独特访客”报表仍将该访客记录为一个独特访客。 </p> <p> <b>消除重复访客</b>：数据收集基于报表标题消除重复访客，与日历选择无关。例如，分别在一个报表周的四天中进行访问的访客在<span class="wintitle">每周独特访客报表</span>中将被计算一次。在跨越该周的<span class="wintitle">每日独特访客报表</span>中，同一访客将被计算四次。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>转化（成功）事件 </p> </td> 
   <td> <p>转化事件是网站上您想要访客执行的活动（关键绩效指标）。对于电子商务网站，转化事件可能是详细产品查看、结帐或购买。对于潜在客户开发网站，这可能是填写表单。将在网站上为这些转化事件计数，并生成可显示其发生次数的报表。这些事件也可以作为其他报表中的量度，可以显示转化事件的发生原因，或促使其发生的因素。 </p> <p>购买事件是一个事件成为一个量度规则的特例，它会产生三个量度：收入、订购数目和件数。 </p> <p>还有许多此处未定义的转化量度，而转化量度构成了网站分析的基础，从而得以创建其他量度和报表。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>渠道 </p> </td> 
   <td> <p> 网站上定义的区域或类别。包括两个主要类别（如<span class="term"> 天气</span> 和 <span class="term"> 新闻</span>，有两个渠道。您可以对网站任何渠道中发生的所有页面查看的统计数据进行分组。 </p> </td> 
  </tr> 
 </tbody> 
</table>

