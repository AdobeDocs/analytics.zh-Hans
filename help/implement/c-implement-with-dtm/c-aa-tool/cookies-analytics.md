---
description: 用于在 Adobe Analytics 中部署动态标签管理的“Cookie”全局设置的字段描述。
keywords: 动态标签管理；cookies；访客id；访客命名空间；域句点；fp域句点；事务ID;cookie生命周期
seo-description: 用于在 Adobe Analytics 中部署动态标签管理的“Cookie”全局设置的字段描述。
seo-title: Cookie
solution: Experience Cloud，分析，动态标签管理
title: Cookie
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Cookie

Field descriptions for the Cookies global settings used for deploying [!UICONTROL Dynamic Tag Management] in Adobe Analytics.

**[!UICONTROL *`Property`*]** &gt; **[!UICONCONTROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Cookies]**

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 访客 ID </td> 
   <td colname="col2"> <p>唯一值，表示同时位于在线和离线系统中的客户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客命名空间 </td> 
   <td colname="col2"> <p>用于识别设置 Cookie 的域的变量。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> 域名句点数量 </td> 
   <td colname="col2"> <p>在域中设置了 Analytics cookie（<code>s_cc</code> 和 <code>s_sq</code>），以此来确定页面 URL 的域中句点的数量。某些插件还会使用此变量来确定要设置插件 Cookie 的正确域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FP 域名句点 </td> 
   <td colname="col2"> <p>The <span class="term"> fpCookieDomainPeriods</span> variable is for cookies set by JavaScript (<code> s_sq</code>, <code> s_cc</code>, plug-ins) that are inherently first-party cookies, even if your implementation uses the third-party <span class="filepath"> 2o7.net</span> or <span class="filepath"> omtrdc.net</span> domains. </p> <p>请参 <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> 阅s.fpCookieDomainPeriods</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 交易 ID </td> 
   <td colname="col2"> <p>唯一值，表示产生离线活动的在线交易。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cookie 存留期 </td> 
   <td colname="col2"> <p>确定 Cookie 的生命周期。 </p> </td> 
  </tr> 
 </tbody> 
</table>

