---
description: “查找方法”页面可确定各种查找方法报表如何接收网站上转化成功事件的信用。 例如，如果搜索引擎将访客引用到您进行购买的站点，则“查找方法”将指定搜索引擎接收引用信用的方式。
title: 查找方法
topic: Admin tools
uuid: 1053993e-7fc4-4874-84fa-367ecdcd7b45
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 查找方法

“查找方法”页面可确定各种查找方法报表如何接收网站上转化成功事件的信用。 例如，如果搜索引擎将访客引用到您进行购买的站点，则“查找方法”将指定搜索引擎接收引用信用的方式。

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Finding Methods]**.

## 查找方法描述 {#section_8B6278DB75224EAB9F49D89A86274E8A}

<table id="table_8ABC1C9BD63F419082E4C4C69E401526"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 要修改的查找方法 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分配 </td> 
   <td colname="col2"> 指定如何为转诊申请信用。 支持的分配选项包括： <p> <span class="uicontrol">最近（上一个）：</span>将所有信用提供给最后一个反向链接（默认）。 </p> <p> <span class="uicontrol">原始值：</span>将所有信用给予第一个反向链接。 </p> <p> <span class="uicontrol">线性：</span>将信用平均分配到所有反向链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 过期时间 </td> 
   <td colname="col2"> 
    <ul id="ul_95EB224CAD164E9997B148E08AFA5F9B"> 
     <li id="li_C240460C21E14AA498D2EA62B9354710"> <span class="uicontrol">访问：</span>在特定的非活动状态时间段后；通常约为 30 分钟。 </li> 
     <li id="li_A3AE5438919E44B68DF99BEEA60C44EE"> <span class="uicontrol">页面查看：</span>您网站的任何页面打开后。 </li> 
     <li id="li_D5E20FEF313E4C5B99E7097CA175761A"> <span class="uicontrol">分钟：</span>1 分钟非活动状态后。 </li> 
     <li id="li_7315AA3EDDBB47A2BEA3C173881378A1"> <span class="uicontrol">购买：</span>购买之时。 </li> 
     <li id="li_C0CF07581654472C9C9EC944E6F18164"> <span class="uicontrol">产品查看：</span>访客查看产品网页时。 </li> 
     <li id="li_A1B04065150B407491D2EC78EC0DBDF5"> <span class="uicontrol">购物车打开：</span>访客打开新的在线购物车时。 </li> 
     <li id="li_2AA50C6B9CB14500B67909CDF2AA700C"> <span class="uicontrol">购物车结账：</span>访客为在线购物车结账时。 </li> 
     <li id="li_F58CE6FB8DCE4BE4927FFCB35A6D8E31"> <span class="uicontrol">购物车加货：</span>访客加货至在线购物车时。 </li> 
     <li id="li_AD7C846F46604FC48E0919ACB7515E14"> <span class="uicontrol">购物车减货：</span>访客从在线购物车减货时。 </li> 
     <li id="li_EB66E0563F564C9F985BE922DABD0A56"> <span class="uicontrol">购物车打开：</span>访客查看在线购物车内容时。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE] 访问结束时，所有“查找方法”都会过期。如果您选择在其他事件（例如，购物车结帐）后过期，则在访问期间发生购物车结帐时，查找方法将过期。 如果访问期间未发生购物车结帐，则在访问结束时，查找方法仍会过期。

