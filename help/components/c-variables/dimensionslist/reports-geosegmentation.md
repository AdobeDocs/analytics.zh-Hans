---
description: 显示有关访客位置的数据。 地域划分报告包括国家、地区、城市、美国州和美国DMA（数字营销区域）。 已为所有客户启用地域划分报表。
title: 地域划分
topic: Reports
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# 地域划分

显示有关访客位置的数据。 地域划分报告包括国家、地区、城市、美国州和美国DMA（数字营销区域）。 已为所有客户启用地域划分报表。

在Reports &amp; Analytics的其他位置，您可以使用的所有指标都会自动包含在国家、地区、城市、美国州和DMA报告中：基于转化和访问的指标以及计算的指标。 For more information, see this Adobe [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) post.

<table id="table_566CFFC82E1149D8BAFE6641627FCF1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 报表 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 国家/地区 </td> 
   <td colname="col2"> <p> 最大的地理部门。 除了大多数报表中提供的“排名”和“趋势”标准视图外，还有一种“地图”视图，这种视图会根据不同国家/地区对网站总流量的相对贡献为其设置颜色代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地区 </td> 
   <td colname="col2"> <p> 比国家小但比城市大的地理区域。 在一些国家，地区是州、省或州。 在其他地区，它是组成国家、部门或都市区。 在显示的每个区域的右侧，该区域的国家也显示在括号中。 </p> <p>在表详细信息中，单击“运行此区域的城市报告”（放大镜）以运行报告，其中显示选定区域中的城市与该区域其他城市相比的表现。 </p> <p>See <a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  > GeoSegmentation Regions and Postal Code usage by Country</a> to see which countries use regions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 城市 </td> 
   <td colname="col2"> <p> 最小的地理区域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 美国各州 </td> 
   <td colname="col2"> <p> 一张热图显示了美国各州的访客。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 美国 DMA </td> 
   <td colname="col2"> <p> （数字营销区）美国广播和电视媒体市场部门。 您可以过滤报表以仅显示特定状态中的营销区域。 此数据是Adobe与Nielsen Media Research, Inc.通过合作提供的。 </p> <p>注意：美国 DMA 报表中的未指定条目表示无法与特定 DMA 关联的访客。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 报告准确性 </td> 
   <td colname="col2"> <p>Adobe与IP智能和身份验证解决方案的领先提供商Digital Envoy携手优惠GeoSegmentation，这是一种基于最终用户IP地址的地理测量功能。 虽然基于各个数据集的准确性可能不同，但Digital Envoy通常在国家一级优惠的准确性超过99%，在区域一级估计的准确性超过97%，在城市一级估计的准确性超过90%。 </p> <p>Note: These numbers assume that <a href="/help/admin/admin/general-acct-settings-admin.md">the setting</a> to remove the last octet of the IP address is NOT enabled. </p> <p>IP 地址会被映射到邮政编码，并且每个城市也会按邮政编码进行定义，邮政编码是由“地方当局”为该城市定义的组成部分。例如，柏林的定义中不包含柏林的郊区，但是每个城镇/城市会单独列出，这样 IP 地址便可以准确地映射到其中某个城镇的邮政编码。 </p> <p>影响GeoSegmentation数据的因素包括： </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">代表公司代理的IP地址。 这些流量可能显示为通过用户的公司网络的流量，如果用户远程工作，则实际上可能是另一个位置。 </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">移动IP地址。 移动IP定位在不同的级别工作，具体取决于位置和网络。 许多运营商通过集中或区域POP回传IP流量。 </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">属于卫星ISP用户的IP地址。 识别这些用户的特定位置很困难，因为他们通常看起来来自上行链路的位置。 </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">军事和政府知识产权。 这往往代表在世界各地旅行，从本地而不是他们目前驻地的基地或办公室进入的人员。 </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">我们的GeoSegmentation/IP数据由第三方供应商提供，并根据ISP和其他网络来源提供的信息定期更新。 IP查询本身就具有波动性，因为它们在世界各地经常买卖。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

