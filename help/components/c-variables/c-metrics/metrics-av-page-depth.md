---
description: 显示访问中触发每个值的平均深度。此量度用于确定一次访问中访客到达给定页面或 prop 值的深度。平均页面深度可用于任何启用了路径分析的变量。
seo-description: 显示访问中触发每个值的平均深度。此量度用于确定一次访问中访客到达给定页面或 prop 值的深度。平均页面深度可用于任何启用了路径分析的变量。
seo-title: 平均页面深度
solution: Analytics
title: 平均页面深度
topic: 量度
uuid: 4d8a3a3c-c698-4210dd8-a02 a1638483 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 平均页面深度

显示访问中触发每个值的平均深度。此量度用于确定一次访问中访客到达给定页面或 prop 值的深度。平均页面深度可用于任何启用了路径分析的变量。

例如，如果某次访问包含以下路径：页面 A &gt; 页面 B &gt; 页面 C &gt; 页面 D &gt; 页面 E &gt; 页面 F，则深度可指出某个页面所在的位置。例如，“页面 A”的深度为 0，“页面 F”的深度为 5。平均值基于所有访问的组合。值小于 1（例如 0.9）的页面深度是在目前页面之前访问的所有页面的平均值。

[!UICONTROL 页面深度]有助于您理解指定页面通常在用户路径中的位置，而无论该路径中的上一页面或下一页面如何。因此，利用该量度，您可以分析页面如何适应用户网站体验的总体状况。这在[!UICONTROL 页面]报表上是最直观的。

<table id="table_E92B185A487C40E28C70EA30EDF73A40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 流量 </td> 
   <td colname="col2"> <p>计算页面事件数与页面查看次数之和除以访问量的结果，可以表明页面的平均点击次数。请考虑相同的访问路径： </p> <p>A &gt; B &gt; B &gt; C &gt; D &gt; B </p> <p>每个页面和页面事件均计算了点击次数，包括“计算重复实例”选项启用时的重新载入次数（此选项在 Ad Hoc Analysis 中默认为开启，并且在市场 Marketing Reports &amp; Analytics 中始终开启）。在这次访问中，页面 A 收到的点击次数为 0。对于页面 B，点击次数为 1、2 和 5。计算平均值的方法是 [(1+2+5) / 3]，即页面 B 的平均页面深度为 2.67。 </p> <p>当禁用“计算重复实例”选项时，页面 B 收到的点击次数为 1 和 4。第二次将不会计算在内。计算结果为 [(1+4) / 2 = 2.5]。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 转化 </td> 
   <td colname="col2"> 不适用 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [页面深度报表](/help/components/c-variables/dimensionslist/reports-page-depth.md)

