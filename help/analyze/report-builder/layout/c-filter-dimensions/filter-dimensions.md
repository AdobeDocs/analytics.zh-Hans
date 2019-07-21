---
description: 您可以过滤添加到“行标签”网格中的维度。过滤器可减少请求返回的数据，并且可以从引导布局或自定义布局中进行应用。通过引导布局配置维度过滤时，您还可以指定单元格中的条目数。
seo-description: 您可以过滤添加到“行标签”网格中的维度。过滤器可减少请求返回的数据，并且可以从引导布局或自定义布局中进行应用。通过引导布局配置维度过滤时，您还可以指定单元格中的条目数。
seo-title: 过滤器维度概述
solution: Analytics
title: 过滤器维度概述
topic: Report Builder
uuid: c54d5add-f278-476d-8f14-73f1 c2 e37671
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 过滤器维度概述

您可以过滤添加到“行标签”网格中的维度。过滤器可减少请求返回的数据，并且可以从引导布局或自定义布局中进行应用。通过引导布局配置维度过滤时，您还可以指定单元格中的条目数。

选定过滤器表单会基于 Report Builder 请求中选择的元素和量度来填充。

## Define filter - values and special characters {#section_15840216A4044C40974945FAA435AD93}

Information about filters in the **[!UICONTROL Most Popular Filter]** &gt; **[!UICONTROL Define Filter]** panel.

![](assets/define_filter.png)

以下各表提供了有关过滤器的示例和信息：

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 过滤器 </th> 
   <th colname="col02" class="entry"> 描述 </th> 
   <th colname="col2" class="entry"> 示例过滤器 </th> 
   <th colname="col3" class="entry"> 匹配结果 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>包含所有词语 </p> </td> 
   <td colname="col02"> <p>包含按任意顺序排列的每个以空格分隔的值。 </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>匹配<span class="term"> b cand</span><span class="term"> b a c</span>，依此类推。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>包含任何词语 </p> </td> 
   <td colname="col02"> <p>包含其中至少一个过滤器（以空格分隔）。 </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p>匹配<span class="term"> A</span>1、 <span class="term"> B</span>2、 <span class="term"> C3</span>，但不 <span class="term"> 是D4</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>包含该短语 </p> </td> 
   <td colname="col02"> <p>包含搜索过滤器，同时也可能包含其他词语。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>匹配<span class="term"> abc</span> 和 <span class="term"> abc def</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不包含任何词语 </p> </td> 
   <td colname="col02"> <p>返回所有不包含输入值的结果。 </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>匹配<span class="term"> d e f</span> 但not <span class="term"> c d e f</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不包含该短语 </p> </td> 
   <td colname="col02"> <p>返回所有不包含该短语的结果。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>不包含<span class="term"> abc</span>、 <span class="term"> abc def</span> 和匹配 <span class="term"> def</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>等于 </p> </td> 
   <td colname="col02"> <p>返回精确匹配结果。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> is return，no other. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不等于 </p> </td> 
   <td colname="col02"> <p>返回任何与输入值不精确匹配的结果。 </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>不匹配 <span class="term"> a</span>. </p> <p>Matches <span class="term"> a b c</span>. </p> <p>Matches <span class="term"> abc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>开始于 </p> </td> 
   <td colname="col02"> <p>返回以特定值开头的结果。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>匹配<span class="term"> abcd</span> 但不 <span class="term"> 是abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>结束于 </p> </td> 
   <td colname="col02"> <p>返回以特定值结尾的结果。 </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>匹配<span class="term"> wxyz</span> 但not <span class="term"> wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高级（特殊字符） </p> </td> 
   <td colname="col02"> <p>允许您使用以下正则表达式字符： </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Home*Page$" | sports </p> </td> 
   <td colname="col3"> <p> 它定义以<span class="term"> 主页，</span>然后查找零个或多个字符，然后以 <span class="term"> 页面结尾</span>。 </p> <p>Also, any page with <span class="term"> sports</span> in it. </p> <p>以下是一些匹配示例： </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">HomePage </li> 
     <li id="li_1351619156274092AEB2771D882AD357">Home（其他字符）Page </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">Home sports </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">sports Page </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">sports </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">xyz sports abc </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_8BBB06C8860745DEA41B39673699DC0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 特殊字符 </th> 
   <th colname="col2" class="entry"> 用途 </th> 
   <th colname="col3" class="entry"> 注释 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> " " </td> 
   <td colname="col2"> 等于 </td> 
   <td colname="col3"> <p>不会转义，除非引号未配对使用。例如，<span class="term"> 17“显示</span> 不是短语。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> 通配符 </td> 
   <td colname="col3"> <p>与正则表达式中使用的星号用途相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ^ </td> 
   <td colname="col2"> 开始于 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> $ </td> 
   <td colname="col2"> 结束于 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> - </td> 
   <td colname="col2"> 非 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> | </td> 
   <td colname="col2"> 或 </td> 
   <td colname="col3"> <p>仅在<span class="term"> 高级(特殊字符)</span> 筛选器。 </p> </td> 
  </tr> 
 </tbody> 
</table>