---
description: 用于在 Adobe Analytics 中部署动态标签管理的“Cookie”全局设置的字段描述。
keywords: Dynamic Tag Management;cookies;visitor id;visitor namespace;domain periods;fp domain periods;transaction id;cookie lifetime
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Cookie
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: ht
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Cookie

用于在 Adobe Analytics 中部署 [!UICONTROL Dynamic Tag Management] 的“Cookie”全局设置的字段描述。

*`Property`* > 编辑工具 >  Cookie

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
   <td colname="col1"> Visitor Namespace </td> 
   <td colname="col2"> <p>用于识别设置 Cookie 的域的变量。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> 域名句点数量 </td> 
   <td colname="col2"> <p>在域中设置了 Analytics cookie（<code> s_cc</code> 和 <code> s_sq</code>），以此来确定页面 URL 的域中句点的数量。某些插件还会使用此变量来确定要设置插件 Cookie 的正确域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FP 域名句点 </td> 
   <td colname="col2"> <p><span class="term">fpCookieDomainPeriods</span> 变量适用于由 JavaScript 设置的内置第一方 Cookie（<code> s_sq</code>、<code> s_cc</code>、插件），即使您的实施使用的是第三方 <span class="filepath">2o7.net</span> 或 <span class="filepath">omtrdc.net</span> 域。 </p> <p>请参阅 <a href="/help/implement/vars/config-vars/fpcookiedomainperiods.md"  >s.fpCookieDomainPeriods</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 交易 ID </td> 
   <td colname="col2"> <p>唯一值，表示产生离线活动的在线交易。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cookie Lifetime </td> 
   <td colname="col2"> <p>确定 Cookie 的生命周期。 </p> </td> 
  </tr> 
 </tbody> 
</table>

