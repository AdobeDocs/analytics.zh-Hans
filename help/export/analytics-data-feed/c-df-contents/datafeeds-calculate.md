---
description: 介绍如何使用数据馈送计算常见量度。
keywords: 数据馈送；作业；度量；预列；后列；机器人程序；日期过滤；事件字符串；常用；公式
seo-description: 介绍如何使用数据馈送计算常见量度。
seo-title: 计算量度
solution: Analytics
title: 计算量度
topic: Reports and Analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 2fc1a01aced4cf2b165b46353418fbee9b83bee5

---


# 计算量度

介绍如何使用数据馈送计算常见量度。

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## 机器人 {#section_06753B95800F47668AAF52E7227F27C8}

根据为报表包所定义的[机器人规则](https://marketing.adobe.com/resources/help/en_US/reference/bot_rules.html)，数据馈送不包括机器人。

## 数据过滤 {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

通过过滤 `date_time` 字段，可包括自您要涵盖的日期范围以来的行。The `date_time` field is human readable (for example, `YYYY-MM-DD HH:MM:SS`) and is adjusted to the time zone of the report suite. For example, `date_time starts with "2013-12"` includes hits from December 2013.

## 事件字符串 {#section_87B686512EFD4A6CA072165CB28A130A}

The event string in `event_list` and `post_event_list` contains a comma-delimited list of events, which may have a value and/or a unique ID. 我们建议对 `post_event_list` 执行所有处理，因为它删除了重复项，并且已应用逻辑来删除具有相同 ID 的重复事件（请参阅[事件序列化](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_event_serialization.html)）。

对于事件 ID 到名称的映射，请参阅随您的数据馈送一同提交的事件对照。

有关事件的详细信息，请参阅[事件](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_events.html)。

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
   <td colname="col1"> 页面查看次数 </td> 
   <td colname="col2"> <p> Page views can be calculated by counting when there is either a value in <code> post_pagename </code> or <code> post_page_url </code>. </p> 
    <p>您可以使用相似的逻辑来计算自定义链接： </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code> post_page_event = 100 </code> 以计算自定义链接数。 </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code> post_page_event = 101 </code> 以计算下载链接数。 </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code> post_page_event = 102 </code> 以计算退出链接数。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访问 </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5、8 和 9 是使用数据源上载的摘要行。7 表示不应包括在访问和访客计数中的交易 ID 数据源上载。请参阅 <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > 点击来源对照 </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D">合 <code> post_visid_high </code>并 <code> post_visid_low </code>、 <code> visit_num </code>和 <code> visit_start_time_gmt </code>*。 计算唯一组合数。 </li> 
    </ol> <p>*在个别情况下，网络异常、系统异常或使用自定义访客 ID 会导致同一个访客 ID 的不同<code> visit_num </code>访问<a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_visit.html"  >出现重复的 </a> 值。To avoid resulting issues, also include <code> visit_start_time_gmt </code> when counting visits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客 </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5、8 和 9 是使用数据源上载的摘要行。7 表示不应包括在访问和访客计数中的交易 ID 数据源上载。请参阅 <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > 点击来源对照 </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39">结合 <code> post_visid_high </code> 使用 <code> post_visid_low </code>。 计算唯一组合数。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件实例 </td> 
   <td colname="col2"> <p>When an event is set on a hit, <code> post_event_list </code> contains the event. The <code> post_event_list </code> is de-duplicated and is recommended to determine event instances. </p> <p>例如： </p> 
    <code>
      post_event_list = 1,200 
    </code> <p>Indicates an instance of <code> purchase </code> and <code> event1 </code>. </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB">Exclude all rows with <code> hit_source = 5,8,9 </code>. 这些是使用数据源上载的摘要行。请参阅 <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > 点击来源对照 </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD">Count the number of times the event lookup value appears in <code> post_event_list </code>. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar 实例 </td> 
   <td colname="col2"> <p>当在点击上设置 eVar 时，<code> event_list </code> 会包含该 eVar 的实例。 </p> <p>例如： </p> 
    <code>
      post_event_list&amp;nbsp;=&amp;nbsp;100,101,106 
    </code> <p>Indicates an instance of <code> eVar1 </code>, <code> eVar2 </code>, and <code> eVar7 </code>. 这表示在点击上设置了这三个 eVar 的值。 </p> <p>要计算 eVar 的实例，请使用上面<i>事件实例</i>中所述的相同逻辑，但是计算 eVar 对照在 <code> post_event_list </code> 中出现的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 逗留时间 </td> 
   <td colname="col2"> <p>要计算逗留时间，您必须按访问对点击进行分组，然后根据访问内的点击数对它们进行排序。 </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803">Group hits for a visit by concatenating <code> visid_high </code>, <code> visid_low </code>, and <code> visit_num </code>. </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B">Order hits for each visit by <code> visit_page_num </code>. </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0">Using <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-page-event.md"  > page_event </a>, filter the types of hits you want. </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">查找点击，其中已设置了想要用来跟踪逗留时间的值。例如：<code>
        hit&nbsp;1:&nbsp;post_prop1=red hit&nbsp;2:&nbsp;post_prop1=blue 
      </code> </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">Subtract the <code> post_cust_hit_time </code> for hit 1 from the <code> post_cust_hit_time </code> for hit 2 to determine the seconds between these two hits. The result is the time spent for <code> post_prop1=red </code>. 如果产生的是一个负数，则表示点击是按乱序接收的，并且应当放弃计算。 </li> 
    </ol> <p>可扩展此逻辑以计算其他值的逗留时间。When calculating time spent, Analytics calculates time spent based on the time the value was set in a <code> track </code> ( <code> page_event=0 </code>) or <code> trackLink </code> ( <code> page_event=10|11|12 </code>) call, to the time of the next page view ( <code> track </code> call). </p> <p>在报告特定时期的逗留时间时，Marketing Reports &amp; Analytics 和 Ad Hoc Analysis 会评估报告时间段范围以外的点击，以确定值在报表时间段内的逗留时间（除非时间段的开始和/或结束日期在每月的边界）。由于这些计算非常复杂，因此可能很难准确匹配逗留时间量度。Data Warehouse 不会评估超出报表时间段范围的点击。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收入、订购和件数 </td> 
   <td colname="col2"> <p>根据报表包的设置，货币转化会应用到 <code> post_product_list </code>，因此建议使用该列。 </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C">Exclude all rows with <code> hit_source = 5,8,9 </code>. 5-9 表示使用数据源上载的摘要行。请参阅 <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > 点击来源对照 </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733">Ignore purchase data for rows where <code> duplicate_purchase = 1 </code>. 此标记指示该购买是一个重复购买（这意味着已经记录了具有相同 <code> purchaseID </code> 的点击）。 </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p><code> post_product_list </code> 使用与 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/c_products.html"  >s.products</a> 相同的语法，因此您可以解析此字符串以计算量度。例如： </p> 
      <code>
        ;Cross Trainers;1;69.95,;Athletic Socks;10;29.99 
      </code> <p>通过解析此字符串，您可以确定以 69.95 美元的价格购买了一双多功能训练鞋，此次购买的总收入是 99.94 美元。 </p> </li> 
    </ol> <p>注意：Analytics 允许包含产品收入的货币事件通过事件字符串传递，因此您可能需要考虑不在产品字符串中的收入。请参阅 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/c_events.html"  >s.events</a> 中的<i>数值/货币事件</i>。 </p> </td> 
  </tr> 
 </tbody> 
</table>
