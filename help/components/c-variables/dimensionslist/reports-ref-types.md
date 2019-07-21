---
description: 通过跟踪和记录访客每次访问的反向链接网站，可以确定访客每次访问时如何找到您的网站。
seo-description: 通过跟踪和记录访客每次访问的反向链接网站，可以确定访客每次访问时如何找到您的网站。
seo-title: 反向链接类型
solution: Analytics
title: 反向链接类型
topic: 报表
uuid: 7f63d327-d223-4537-a722-4780ae05 c2 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 反向链接类型

通过跟踪和记录访客每次访问的反向链接网站，可以确定访客每次访问时如何找到您的网站。

以下列表列出了有关不同类型反向链接的定义：

**其他网站**：在访客点击其他网站（并非定义为您网站的一部分）页面上的链接，然后转到您的网站时，会记录反向链接。

**搜索引擎**：在访客使用搜索引擎来访问您的网站时，会记录搜索引擎反向链接。反向链接值必须被 Adobe 视为搜索引擎，并且不能是不被视为搜索引擎的子域（例如 [!DNL mail.yahoo.com] 不是搜索引擎，因为此域名将用于电子邮件）。

**[!UICONTROL 社交网络]**：反向链接值必须被 Adobe 视为社交网络。请参阅[社交网络列表](https://helpx.adobe.com/analytics/kb/list-social-networks.html)。

**电子邮件**：当访客单击包含该协议 [!DNL imap://] 的电子邮件链接链接或 [!DNL mail://] 到达您的站点时，引用域将被视为电子邮件引用域。例如，由于协议为 [!DNL https://mail.yahoo.com]://，因此来自 [!DNL https://] 的任何消息均不会计为电子邮件反向链接。Outlook 电子邮件会报告于“键入/书签式”行上，而任何采用 HTTP 协议（域为已知搜索引擎）的反向链接均报告于“搜索引擎”行上。

**键入/书签**：在以下两种情形下记录反向链接：访客在其浏览器中直接键入您的网站的 URL，或者访客通过选择书签来访问您的网站。移动设备会报告&#x200B;*`typed/bookmarked`*&#x200B;类型的反向链接（如果访问的首次点击没有反向链接）。

**[!UICONTROL 网站内部]**：这些项目是由内部 URL 过滤器标记的 URL。These items are not counted as *`referrer instances`* but can be seen when reporting on other metrics.

## 按界面划分的反向链接类型 {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Marketing Reports &amp; Analytics (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 报告的反向链接类型 </td> 
   <td colname="col2"> 
    <ul id="ul_EFC8E81EC6DF4CC2AC0E290244FD5859"> 
     <li id="li_686FCAEB04054B9F8A7D2434E8C49F04">其他网站 </li> 
     <li id="li_C232868230AA4A54958B524F3D8FDA35"> 搜索引擎 </li> 
     <li id="li_A89BFD0468F74ED7822F64BE4A7332AE"> Social </li> 
     <li id="li_C824E6F7F6E748DD827A95B105ADBADD"> 键入/书签式 </li> 
    </ul> <p> 此报表仅显示两个预定义量度：“实例”和“独特访客”。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_FD81EB3C1BD949A39C5A9E9688D25271"> 
     <li id="li_6099E7E03F3843D484808258A332BBE9">其他网站 </li> 
     <li id="li_5AABC02DA7964D578BF8404DA819245D"> 搜索引擎 </li> 
     <li id="li_B18907AC7FA1429A893B57634EB7DC6F"> Social </li> 
     <li id="li_7674B67897994E1FA99BCD9B604BCB6E"> 键入/书签式 </li> 
    </ul> </td> 
   <td colname="col4"> 
    <ul id="ul_C37ADBEC31D04295BF5CDEA25DB5191A"> 
     <li id="li_81A642C96C674669BA00B2DACA534B8A">其他网站 </li> 
     <li id="li_29B9DA9F2AAD46A69886D34D5E6E43D4"> 搜索引擎 </li> 
     <li id="li_E381EEF111F248F99EE39600D616B7C2"> Social </li> 
     <li id="li_596377F4D3C248BEA5191EE2985A2B13"> 键入/书签式 </li> 
     <li id="li_A7A72D3D6B9A4CCFB43EDA77ABFDEDBC"> 网站内部 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 注释 {#section_B83A3571D64E4E7792712FAF740D7955}

* 反向链接、反向链接类型和反向链接域名会在首次访问点击时设置，或者当反向链接来自外部时，在访问期间设置（例如，如果访客离开网站，使用搜索引擎，然后在第一次访问过期之前回到网站）。这些值会同时设置，并在整个访问期间存在。
* 不是所有反向链接类型都在此报表中列出。这表示网站范围的访问数与此报表中的访问数不匹配。

## 报表历史记录 {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| 日期 | 更改 |
|---|---|
| 2014 年 1 月 16 日 | Data Warehouse 已更新，以匹配 Marketing Reports &amp; Analytics 所用的逻辑。在此日期之前，反向链接类型在整个访问期间不是持续值。 |

