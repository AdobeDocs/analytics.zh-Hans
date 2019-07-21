---
description: 介绍如何使用数据馈送计算常见量度。
keywords: 数据馈送；工作；指标；pre column；post column；机器人；日期筛选；event string；common；公式
seo-description: 介绍如何使用数据馈送计算常见量度。
seo-title: 计算指标
solution: Analytics
title: 计算指标
topic: Reports & Analytics
uuid: a45ea5bb-7c83-468f-b94 a-63add78931 d7
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 计算指标

介绍如何使用数据馈送计算常见量度。

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## 机器人 {#section_06753B95800F47668AAF52E7227F27C8}

根据为报表包所定义的[机器人规则](https://marketing.adobe.com/resources/help/en_US/reference/?f=bot_rules)，数据馈送不包括机器人。

## 数据过滤 {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

通过过滤 `date_time` 字段，可包括自您要涵盖的日期范围以来的行。`date_time` 字段为人类可读性(例如， `YYYY-MM-DD HH:MM:SS`)并调整至报表包的时区。For example, `date_time starts with "2013-12"` includes hits from December 2013.

## 事件字符串 {#section_87B686512EFD4A6CA072165CB28A130A}

The event string in `event_list` and `post_event_list` contains a comma-delimited list of events, which may have a value and/or a unique ID. 我们建议对 `post_event_list` 执行所有处理，因为它删除了重复项，并且已应用逻辑来删除具有相同 ID 的重复事件（请参阅[事件序列化](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_event_serialization)）。

对于事件 ID 到名称的映射，请参阅随您的数据馈送一同提交的事件对照。

有关事件的详细信息，请参阅[事件](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_events)。

## 常用量度的公式 {#section_E26A01C234484857BF8C74443222AE41}

下表包含有关计算几个常用量度的说明。

<table id="table_814EA73C01EE4B2CA3CEB2839E19ADF9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 计算方法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 页面查看 </td> 
   <td colname="col2"> <p> 当 <code>post_pagename</code> 或 <code>post_page_url</code> 中存在值时，可以通过计数来计算页面查看次数。 </p> 
    <p>您可以使用相似的逻辑来计算自定义链接： </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code>post_page_event = 100</code>，用于计算自定义链接。 </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code>post_page_event = 101</code>，用于计算下载链接。 </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code>post_page_event = 102</code>，用于计算退出链接。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访问次数 </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325">排除 <code>exclude_hit &gt; 0</code> 的所有行。 </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5">排除 <code>hit_source = 5,7,8,9</code> 的所有行。5、8 和 9 是使用数据源上载的摘要行。7 表示不应包括在访问和访客计数中的交易 ID 数据源上载。请参阅 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> 点击来源对照 </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D">将 <code>post_visid_high</code>、<code>post_visid_low</code>、<code>visit_num</code> 与 <code>visit_start_time_gmt</code> 组合到一起*。计算唯一组合数。 </li> 
    </ol> <p>*在个别情况下，网络异常、系统异常或使用自定义访客 ID 会导致同一个访客 ID 的不同<code>访问</code>出现重复的 <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=metrics_visit" format="http" scope="external">visit_num</a> 值。为避免出现问题，请在计算访问次数时也将 <code>visit_start_time_gmt</code> 包含在内。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客 </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D">排除 <code>exclude_hit &gt; 0</code> 的所有行。 </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527">排除 <code>hit_source = 5,7,8,9</code> 的所有行。5、8 和 9 是使用数据源上载的摘要行。7 表示不应包括在访问和访客计数中的交易 ID 数据源上载。请参阅 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> 点击来源对照 </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39">将 <code>post_visid_high</code> 与 <code>post_visid_low</code> 组合到一起。计算唯一组合数。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件实例 </td> 
   <td colname="col2"> <p>当在点击上设置事件时，<code>post_event_list</code> 会包含该事件。<code>post_event_list</code> 删除了重复项，建议用于确定事件实例。 </p> <p>例如： </p> 
    <code>post_ event_ list=1,200 </code>
  <p>指示 <code>purchase</code> 和 <code>event1</code> 的实例。 </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A">排除 <code>exclude_hit &gt; 0</code> 的所有行。 </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB">排除 <code>hit_source = 5,8,9</code> 的所有行。这些是使用数据源上载的摘要行。请参阅 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> 点击来源对照 </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD">计算事件对照值在 <code>post_event_list</code> 中出现的次数。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar 实例 </td> 
   <td colname="col2"> <p>当在点击上设置 eVar 时，<code>event_list</code> 会包含该 eVar 的实例。 </p> <p>例如： </p> 
    <code>post_ event_ list&amp; amp；nbsp；=&amp; amp；nbsp；100,101,106 </code>
  <p>指示 <code>eVar1</code>、<code>eVar2</code> 和 <code>eVar7</code> 的实例。这表示在点击上设置了这三个 eVar 的值。 </p> <p>要计算 eVar 的实例，请使用上面<i>事件实例</i>中所述的相同逻辑，但是计算 eVar 对照在 <code>post_event_list</code> 中出现的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 逗留时间 </td> 
   <td colname="col2"> <p>要计算逗留时间，您必须按访问对点击进行分组，然后根据访问内的点击数对它们进行排序。 </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F">排除 <code>exclude_hit &gt; 0</code> 的所有行。 </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803">通过连接 <code>visid_high</code>、<code>visid_low</code> 和 <code>visit_num</code>，对某次访问的点击进行分组。 </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B">按 <code>visit_page_num</code> 对每次访问的点击进行排序。 </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0">Using <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-page-event.md#concept_A3AC076C3728445EB4CC572A6EDA5263" format="dita" scope="local"> page_event </a>, filter the types of hits you want. </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">查找点击，其中已设置了想要用来跟踪逗留时间的值。例如：<code>点击1：post_ prop1=红色点击2：post_ prop= blue </code>
  </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">从点击 2 的 <code>post_cust_hit_time</code> 中减去点击 1 的 <code>post_cust_hit_time</code>，以确定这两次点击之间的秒数。结果为 <code>post_prop1=red</code> 的逗留时间。如果产生的是一个负数，则表示点击是按乱序接收的，并且应当放弃计算。 </li> 
    </ol> <p>可扩展此逻辑以计算其他值的逗留时间。在计算逗留时间时，Analytics 会根据 <code>track</code> (<code>page_event=0</code>) 或 <code>trackLink</code> (<code>page_event=10|11|12</code>) 调用中设置的时间值来计算逗留时间，进而得到下一页面查看的时间（<code>track</code> 调用）。 </p> <p>在报告特定时期的逗留时间时，Marketing Reports &amp; Analytics 和 Ad Hoc Analysis 会评估报告时间段范围以外的点击，以确定值在报表时间段内的逗留时间（除非时间段的开始和/或结束日期在每月的边界）。由于这些计算非常复杂，因此可能很难准确匹配逗留时间量度。Data Warehouse 不会评估超出报表时间段范围的点击。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收入、订购和件数 </td> 
   <td colname="col2"> <p>根据报表包的设置，货币转化会应用到 <code>post_product_list</code>，因此建议使用该列。 </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16">排除 <code>exclude_hit &gt; 0</code> 的所有行。 </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C">排除 <code>hit_source = 5,8,9</code> 的所有行。5-9 表示使用数据源上载的摘要行。请参阅 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> 点击来源对照 </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733">忽略 <code>duplicate_purchase = 1</code> 的行的购买数据。此标记指示该购买是一个重复购买（这意味着已经记录了具有相同 <code>purchaseID</code> 的点击）。 </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p><code>post_product_list</code> 使用与 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_products" format="http" scope="external">s.products</a> 相同的语法，因此您可以解析此字符串以计算量度。例如： </p> 
      <code>；交叉培训师；1；69.95；运动技巧；10；29.99 </code>
  <p>通过解析此字符串，您可以确定以 69.95 美元的价格购买了一双多功能训练鞋，此次购买的总收入是 99.94 美元。 </p> </li> 
    </ol> <p>注意：Analytics 允许包含产品收入的货币事件通过事件字符串传递，因此您可能需要考虑不在产品字符串中的收入。请参阅 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_events" format="http" scope="external">s.events</a> 中的<i>数值/货币事件</i>。 </p> </td> 
  </tr> 
 </tbody> 
</table>
