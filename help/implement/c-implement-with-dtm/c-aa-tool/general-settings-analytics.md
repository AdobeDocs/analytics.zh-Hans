---
description: 动态标签管理中用于部署 Adobe Analytics 的“常规”设置的字段描述。
keywords: Analytics 实施;实施方法;dynamic tag management;DTM;常规设置;EU 合规性;字符集;货币代码;跟踪服务器;SSL 跟踪服务器
seo-description: 动态标签管理中用于部署 Adobe Analytics 的“常规”设置的字段描述。
seo-title: 常规
solution: Analytics
title: 常规
topic: 开发人员和实施
uuid: 93008719-6fb6-4e39-9a75-c937fe3247b9
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 常规

DTM 中用于部署 Adobe Analytics 的“常规”设置的字段描述。

**[!UICONTROL &lt;属性&gt;]** &gt; ![](assets/settings_gear.png) **[!UICONTROL 编辑工具]** &gt; **[!UICONTROL 常规]**

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
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> 如果该 Cookie 不存在，或者如果该 Cookie 存在且设置为非 <span class="term">true</span> 的任何值，则在启用此设置的情况下会跳过该工具的加载。这表示，使用该工具的规则的任何部分均不适用。 </p> <p>如果某条规则具有启用 EU 合规性的 Analytics 和第三方代码，并且该 Cookie 设置为 <span class="term">false</span>，则第三方代码仍会运行。但是，不会设置 Analytics 变量。 </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> 如果该 Cookie 存在且设置为 <span class="term">true</span>，则该工具会正常加载。 </li> 
    </ul> <p>如果访客选择禁用，则由您负责将 <span class="filepath">sat_track</span>（或命名的自定义）Cookie 设置为 <span class="term">false</span>。您可以使用以下自定义代码实现此操作： </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"false"); 
     </code> </p> <p> 如果希望访客稍后能够选择加入，则还必须具有一种机制，以将该 Cookie 设置为 <span class="term">true</span>： </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"true"); 
     </code> </p> </td> 
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

