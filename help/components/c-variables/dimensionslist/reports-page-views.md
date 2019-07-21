---
description: “页面查看”报表是一个趋势报表，它显示选定时段（小时、日、周、月、季或年）内网站页面的查看次数。您可以利用此报表来跟踪网站中每个页面的查看次数，以及整个网站的页面查看次数总和。
seo-description: 页面查看报表是一个趋势报表，它显示选定时段（小时、日、周、月、季或年）内网站页面的查看次数。您可以利用此报表来跟踪网站中每个页面的查看次数，以及整个网站的页面查看次数总和。
seo-title: 页面查看次数
solution: Analytics
title: 页面查看次数
topic: 报表
uuid: c78260c6-9ad4-4b85-84fd-763627392e44
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 页面查看

“页面查看”报表是一个趋势报表，它显示选定时段（小时、日、周、月、季或年）内网站页面的查看次数。您可以利用此报表来跟踪网站中每个页面的查看次数，以及整个网站的页面查看次数总和。

[页面查看](../../../components/c-variables/c-metrics/metrics-page-view.md#concept_ABB4C6725E844B13970D6BD625654F26)是对完整页面文档的请求，而不是页面的某个元素，如图像或视频。例如，如果一个访客在一次访问中查看 15 个页面，则将计为 15 次页面查看。如果一位访客在一次访问期间三次查看同一页面，将计为三次页面查看。

**报表属性**

* 此报表引用了 [s.t()](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_the_s.t()function) 函数在您的网站上被调用的次数。
* Custom [link tracking](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linktracking) calls (such as custom links, file downloads, and exit links) use the [!DNL s.tl()] function and are not counted in this report.

* 由于图像请求会在用户刷新页面或单击返回按钮时发送，因此，此报表也包含这些操作。
* 小时划分是基于报表包的时区。
* 此报表不包含行项目。因此，仅能以趋势格式查看此报表。
* 可应用“小时”、“日”、“周”、“月”、“季”和“年”粒度。该粒度的可用性取决于报表的日期范围。

**产品特定的信息**

<table id="table_61F964F47D1D43508B271999F495F7F9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> 网站内容</span> &gt; <span class="uicontrol">页面查看</span> </p> <p>此报表可使用区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad hoc analysis </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DB66B8F9F6BF473A83EC7668F59776D0"> 
     <li id="li_D1CB486058F040859560D5BFDF3972EE"> 按所有其他报表和变量划分此报表中的每个项目，因此可按任何粒度显示划分结果。 </li> 
     <li id="li_BAADA9ADDD6F47B08D129FD30CD8EF2E">您可以在此报表中使用所有转化和流量量度，以及对所有转化量度进行不同的分配。 </li> 
     <li id="li_3696CA6E0BD54305B3609CCC80F851BA">此报表可使用多个非常高级的区段。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

