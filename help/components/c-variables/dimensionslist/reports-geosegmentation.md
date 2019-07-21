---
description: 显示有关访客位置的数据。地域划分报表包括国家、地区、城市、美国各州和美国 DMA（数字营销区域）。已为所有客户启用了地域划分报表。
seo-description: 显示有关访客位置的数据。地域划分报表包括国家、地区、城市、美国各州和美国 DMA（数字营销区域）。已为所有客户启用了地域划分报表。
seo-title: 地域划分
solution: Analytics
title: 地域划分
topic: 报表
uuid: 66aa22c4-dcbc-491a-b23 c-0c3 d87444 d23
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 地域划分

显示有关访客位置的数据。地域划分报表包括国家、地区、城市、美国各州和美国 DMA（数字营销区域）。已为所有客户启用了地域划分报表。

您在“Reports &amp; Analytics”中的其他位置可使用的所有量度会自动包含在“国家”、“地区”、“城市”、“美国各州”和“DMA”报表内：基于转化和访问的量度以及计算量度。有关详细信息，请参阅此 Adobe [博客](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/)文章。

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
   <td colname="col2"> <p> 最大的地理分区。除了大多数报表中提供的“排名”和“趋势”标准视图外，还有一种“地图”视图，这种视图会根据不同国家/地区对网站总流量的相对贡献为其设置颜色代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地区 </td> 
   <td colname="col2"> <p> 比国家小但比城市大的地理区域。在某些国家，地区是一个州、省或专区。在其他地区，它是一个成员国、辖区或大都市地区。此外，在显示的每个地区右侧，会在括号内显示地区所在的国家。 </p> <p>在报表详细信息中，点击“为此地区运行城市报表”（放大镜）以运行报表，显示所选地区中的一些城市与该地区中其他城市的比较情况。 </p> <p>请参阅<a href="../../../components/c-variables/dimensionslist/reports-geosegmentation-reference.md#concept_F7D998B418544B39ACD8838B48B732F1" format="dita" scope="local">按国家/地区的地域划分地区和邮政编码使用情况</a>，以了解哪些国家/地区使用地区。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 城市 </td> 
   <td colname="col2"> <p> 最小的地理分区。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 美国各州 </td> 
   <td colname="col2"> <p> 显示美国每个州的访客的热图。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 美国 DMA </td> 
   <td colname="col2"> <p> （数字营销区域）整个美国的广播和电视媒体市场分区。您可以过滤报表，仅显示特定州的营销区域。此数据由 Adobe 和 Nielsen Media Research, Inc. 合作提供。 </p> <p>注意：美国 DMA 报表中的未指定条目表示无法与特定 DMA 关联的访客。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 报表准确性 </td> 
   <td colname="col2"> <p>Adobe 与全球领先的 IP 智能和身份验证解决方案提供商 Digital Envoy 合作推出了“地域划分”功能，该功能基于最终用户 IP 地址进行地理位置上的测量。虽然基于各数据集的准确性可能会有所不同，但通常情况下，Digital Envoy 在国家/地区级别可提供 99% 以上的准确性，在地区级别可提供 97％ 以上的准确性，在城市级别提供 90% 以上的准确性。 </p> <p>注意：这些数字假定未启用[设置](/help/admin/admin/general-acct-settings-admin. md)删除IP地址的最后八位字节。 </p> <p>IP 地址会被映射到邮政编码，并且每个城市也会按邮政编码进行定义，邮政编码是由“地方当局”为该城市定义的组成部分。例如，柏林的定义中不包含柏林的郊区，但是每个城镇/城市会单独列出，这样 IP 地址便可以准确地映射到其中某个城镇的邮政编码。 </p> <p>可能会影响地域划分数据的一些因素包括： </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">表示企业代理的 IP 地址。这些 IP 地址可以显示为通过用户企业网络的流量，但如果用户正在远程工作，则这些 IP 地址实际可能为其他位置。 </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">移动设备 IP 地址。移动设备 IP 定位会根据不同位置和网络以不同级别运行。许多运营商通过集中式或区域式 POP 回传 IP 流量。 </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">属于卫星 ISP 用户的 IP 地址。识别这些用户的具体位置十分困难，因为他们通常显示为来自上行位置。 </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">军方和政府 IP。此类 IP 通常表示全球各地的差旅人员通过其本地地址进入，而非他们目前驻扎的基地或办公室。 </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">我们的地域划分/IP 数据由第三方供应商提供，并会根据 Internet 网络服务提供商 (ISP) 和其他网络服务来源所提供的信息定期更新。IP 查询服务具有内在的不稳定性，因为此类服务在世界范围内频繁地进行着买卖交易。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

