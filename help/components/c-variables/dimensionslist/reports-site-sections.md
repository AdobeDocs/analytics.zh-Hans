---
description: 显示访客经常访问的网站区域。网站区域可以包括定义的产品组，它与类别类似。例如，可以包括页面的“照相机”组、“计算机”组等。“转化网站区域”报表的数据会从“流量”组中的“网站区域”报表导入，后者从跟踪代码中的 channel 变量接收信息。您可以使用此报表确定不同网站区域中的项目对网站统计信息的最大影响。
seo-description: 显示访客经常访问的网站区域。网站区域可以包括定义的产品组，它与类别类似。例如，可以包括页面的“照相机”组、“计算机”组等。“转化网站区域”报表的数据会从“流量”组中的“网站区域”报表导入，后者从跟踪代码中的 channel 变量接收信息。您可以使用此报表确定不同网站区域中的项目对网站统计信息的最大影响。
seo-title: 网站区域
solution: Analytics
title: 网站区域
topic: 报表
uuid: 6839c566-f88 f-4979-9cf5-52a77 c0 b0416
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 网站区域

显示访客经常访问的网站区域。网站区域可以包括定义的产品组，它与类别类似。例如，可以包括页面的“照相机”组、“计算机”组等。“转化网站区域”报表的数据会从“流量”组中的“网站区域”报表导入，后者从跟踪代码中的 channel 变量接收信息。您可以使用此报表确定不同网站区域中的项目对网站统计信息的最大影响。

* 此报表直接引用来自贵网站上实施的 [s.channel](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_channel) 变量中的数据。
* 此报表可通过趋势和排名两种格式查看。
* 此报表可使用搜索过滤器来查找特定的行项目。
* 分类可用于此报表，允许您重新命名并整合行项目。
* 关联可通过管理工具创建，以与其他任何流量变量产生关联。
* 此报表可使用以下量度：

   * **页面查看**：[pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_pagename) 变量或 URL 被定义的次数（设置为默认量度）

   * **所有路径量度**：访问量、平均页面深度、平均页面逗留时间、登录、退出、重新载入和单次存取
   * 根据贵组织和报表包设置：此报表可启用每日、每周、每月和每季独特访客。
   * **所有标准电子商务量度**：收入、订购、件数、购物车、购物车查看、结账、购物车加货、购物车减货。
   * **所有自定义事件**：事件 1-80、事件 81-100（使用 H22 代码或更高版本的代码时）。

[!UICONTROL 网站区域报表]中的所有转化事件均使用最近分配。您将看到转化被划分到实施中不包含成功事件的页面。这不同于[页面报表](../../../components/c-variables/dimensionslist/reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5)，后者使用的是线性分配。

**产品特定的信息**

<table id="table_525FDF95C8ED4BF2A1E25BE2DA971EFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 界面 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reports &amp; Analytics </td> 
   <td colname="col2"> <p> <span class="uicontrol"> 网站内容</span> &gt; <span class="uicontrol">网站区域</span> </p> <p>除了关联之外，此报表还可利用以下划分： </p> 
    <ul id="ul_9CD009D89B134C53807332E3C88D3C44"> 
     <li id="li_566417EB074D425C9A1F4FB28AA7FAB4"> 
      <ul id="ul_3795C7AAE6DA4B7E96FCDC7F3211DFBB"> 
       <li id="li_50B295E961724CFB83D222DE9B4C7FF2">基于此报表的任何已分类报表 </li> 
       <li id="li_697682892D8841BC8120BEC0E1AE9753"> <span class="wintitle"> 跟踪代码报表</span> </li> 
       <li id="li_F6D893FCBA7A4B3EB04715833CA41022"> <span class="wintitle"> 产品</span>和<span class="wintitle">类别</span>报表 </li> 
       <li id="li_9F379E61DB4F4753AE1FFFC8F9C17347"> <span class="wintitle"> 客户忠诚度报表</span> </li> 
       <li id="li_64A6A06F9265410ABB425DA4AF50C440">任何完全子相关的转化变量 </li> 
       <li id="li_907DDFCC35AB48EEA5B169B4A2598FB1"> <span class="wintitle"> 首次联系和最近联系营销渠道</span> </li> 
       <li id="li_B08A0DCB40154152AF1033B7629A5B5A"> <span class="uicontrol">Target</span> &gt; <span class="uicontrol">促销活动</span>报表（如果启用） </li> 
       <li id="li_6D4E65DD6E2B49C9A8C12181D23F185A">每次访问逗留时间 </li> 
       <li id="li_C6D3AD5A534243A8A6E17C663FEBA6BA">网站区域 </li> 
       <li id="li_E1F46EED5CE2425D83200A2FCB686EE5">登录页面 </li> 
       <li id="li_1201EE0EBF13476C9A9525E0700F30F3">大部分流量源报表 </li> 
       <li id="li_563E07858FB1473BB22C2B191E8BE620">访问量 </li> 
       <li id="li_1CAD77ABA6A2454282A4DA7E88C047E8">许多访客资料报表 </li> 
       <li id="li_D3A04E4CD8EC4646AAB90BF19F0AFA8A">所有转化变量和列表变量 </li> 
       <li id="li_01C194CE0F3E4C0694A34B4C6697F385">可以使用访问以及每日、每周、每月、每季和任意独特访客。 </li> 
      </ul> </li> 
    </ul> <p>此报表可使用区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Hoc Analysis </td> 
   <td colname="col2"> 
    <ul id="ul_DFF9BFC01FC1424B8905C2D2C0EFD156"> 
     <li id="li_65FDF1C165C84F729E0EE84FF671B5E4">Ad Hoc Analysis 可通过市场营销报告界面中的几乎所有其他报表来划分网站区域报表。 </li> 
     <li id="li_2159DE10C52D40AA89E4C934FC184641">除前面提到的所有事件外，还可使用所有转化和流量量度，以及对所有转化量度进行不同的分配。 </li> 
     <li id="li_3A23C6286D314B5D814612469F4F77C5">此报表可使用多个非常高级的区段。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

