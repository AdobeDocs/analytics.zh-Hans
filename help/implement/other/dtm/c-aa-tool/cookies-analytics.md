---
description: 用于在 Adobe Analytics 中部署动态标签管理的“Cookie”全局设置的字段描述。
keywords: Dynamic Tag Management;Cookie;访客 ID;访客命名空间;域名句点;FP 域名句点;交易 ID;Cookie 生命周期
solution: Experience Cloud,Analytics
title: Cookie
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
exl-id: 37e707b0-c42e-4226-82b1-0b63cbff46fb
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '189'
ht-degree: 100%

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
   <td colname="col2"> <p>唯一值，表示位于在线和离线系统中的客户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitor Namespace </td> 
   <td colname="col2"> <p>用于确定设置了 Cookie 的域的变量。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> 域名句点数量 </td> 
   <td colname="col2"> <p>在域中设置了 Analytics cookie（<code> s_cc</code> 和 <code> s_sq</code>），以此来确定页面 URL 的域中句点的数量。某些插件还会使用此变量来确定要设置插件 Cookie 的正确域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FP 域名句点 </td> 
   <td colname="col2"> <p> <span class="term"> fpCookieDomainPeriods</span> 变量是 JavaScript 设置的 Cookie（<code> s_sq</code>、<code> s_cc</code>、插件），它本身是第一方 Cookie，即使您的实施使用第三方 <span class="filepath">adobedc.net</span> 域或者旧版（但仍有效）<span class="filepath">2o7.net</span> 或 <span class="filepath">omtrdc.net</span> 域。 </p> <p>请参阅 <a href="/help/implement/vars/config-vars/fpcookiedomainperiods.md"  >s.fpCookieDomainPeriods</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 交易 ID </td> 
   <td colname="col2"> <p>唯一值，表示产生离线活动的在线交易。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cookie Lifetime </td> 
   <td colname="col2"> <p>确定 Cookie 的生命期限。 </p> </td> 
  </tr> 
 </tbody> 
</table>
