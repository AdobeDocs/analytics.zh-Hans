---
description: 动态标签管理中用于部署 Adobe Analytics 的“常规”设置的字段描述。
keywords: Analytics实施；实施方法；动态标签管理；dm；一般设置；欧盟合规性；字符集；货币代码；跟踪服务器；SSL跟踪服务器
seo-description: 动态标签管理中用于部署 Adobe Analytics 的“常规”设置的字段描述。
seo-title: 常规
solution: Analytics
title: 常规
topic: 开发人员和实施
uuid: 93008719-6fb6-4e399a75-c937 fe3247 b9
translation-type: tm+mt
source-git-commit: 49c81e50ff10060ef7a3debe82132d1099e25118

---


# 常规

DTM中的“常规”设置的字段描述，用于部署Adobe Analytics。

**[!UICONTROL &lt;属性&gt;]** &gt; ![](assets/settings_gear.png)**[!UICONTROL 编辑工具]** &gt; **[!UICONTROL 常规]**

<table id="table_DD8DA303698041D296DD5DB080AF7971"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>为 <span class="keyword">Adobe Analytics</span> 启用 EU 合规性  </p> </td> 
   <td colname="col2"> <p> 基于 EU 隐私 Cookie，启用或禁用跟踪。 </p> <p>在加载页面时，系统会检查是否设置了名为 <span class="filepath">sat_track</span> 的 Cookie（或在“<span class="wintitle">编辑属性</span>”页面中指定的自定义 Cookie 名称）。请考虑以下信息： </p> 
    <ul id="ul_42A6D728F0BC4FBABB0069EFB66DCB01"> 
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> 如果该 Cookie 不存在，或者如果该 Cookie 存在且设置为非 <span class="term"> true </span>，在启用此设置时将跳过工具的加载。这表示，使用该工具的规则的任何部分均不适用。 </p> <p>如果某条规则具有启用 EU 合规性的 Analytics 和第三方代码，并且该 Cookie 设置为<span class="term"> false </span>，第三方代码仍会运行。但是，不会设置 Analytics 变量。 </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> 如果该 Cookie 存在且设置为 <span class="term"> true </span>，该工具正常加载。 </li> 
    </ul> <p>You are responsible for setting the <span class="filepath"> sat_track </span> (or custom named) cookie to <span class="term"> false </span> if a visitor opts out. 您可以使用以下自定义代码实现此操作： </p> <p> 
     <code>_ site. setCookie(“sat_ track”，&amp; amp；nbsp；“false”)； </code>
  </p> <p> You must also have a mechanism to set that cookie to <span class="term"> true </span> if you want a visitor to be able to opt in later: </p> <p> 
     <code>_ site. setCookie(“sat_ track”，&amp; amp；nbsp；“true”)； </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>字符集 </p> </td> 
   <td colname="col2"> <p>显示可用的字符编码集。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>货币代码 </p> </td> 
   <td colname="col2"> <p>显示可选择的受支持货币代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>跟踪服务器 </p> </td> 
   <td colname="col2"> <p>在其中写入图像请求和 Cookie 的域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL 跟踪服务器 </p> </td> 
   <td colname="col2"> <p>在其中写入图像请求和 Cookie 的域。用于安全页面。如果未定义，SSL 数据将转至 <span class="term"> trackingServer </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数据中心 </p> </td> 
   <td colname="col2"> <p>用于数据收集的 Adobe 数据中心。 </p> </td> 
  </tr> 
 </tbody> 
</table>

