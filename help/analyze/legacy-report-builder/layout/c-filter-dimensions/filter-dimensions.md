---
description: 您可以对添加到“行标签”网格的维度进行筛选。 筛选器用于缩小由请求返回的数据，并可从透视或自定义布局应用。 从“引导布局”配置维过滤时，还可以指定单元格中的条目数。
title: 过滤条件维度概述
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
feature: Report Builder
role: User, Admin
exl-id: eded07d5-3c06-419b-92fd-1a48856ac293
TQID: https://experienceleague.adobe.com/yY1Sl6vEWRb-62SzM5e5qxt5lZPHeg-LU5ZiUNb5z8Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 16%

---

# 过滤条件维度概述

{{legacy-arb}}

您可以对添加到“行标签”网格的维度进行筛选。 筛选器用于缩小由请求返回的数据，并可从透视或自定义布局应用。 从“引导布局”配置维过滤时，还可以指定单元格中的条目数。

选定过滤器表单会根据Report Builder请求中选择的元素和量度进行填充。

## 定义过滤器 – 值和特殊字符 {#section_15840216A4044C40974945FAA435AD93}

有关&#x200B;**[!UICONTROL 最受欢迎筛选器]** > **[!UICONTROL 定义筛选器]**&#x200B;面板中的筛选器的信息。

![屏幕截图显示“定义筛选器”对话框，其中包含按应用程序、用户和项目筛选的选项。](/help/admin/tools/assets/filter.png)

下表提供了有关过滤器的示例和信息：

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 过滤器 </th> 
   <th colname="col02" class="entry"> 描述 </th> 
   <th colname="col2" class="entry"> 示例筛选条件 </th> 
   <th colname="col3" class="entry"> 匹配结果 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>包含所有词语 </p> </td> 
   <td colname="col02"> <p>包含任意顺序的每个以空格分隔的值。 </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>匹配<span class="term"> a b c</span>和<span class="term"> b a c</span>，依此类推。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>包含任何词语 </p> </td> 
   <td colname="col02"> <p>包含至少一个过滤器（以空格分隔）。 </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p>匹配<span class="term"> A1</span>、<span class="term"> B2</span>、<span class="term"> C3</span>，但不匹配<span class="term"> D4</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>包含该短语 </p> </td> 
   <td colname="col02"> <p>包含搜索筛选条件，可能还包含其他术语。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>匹配<span class="term"> abc</span>和<span class="term"> abc def</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不包含任何词语 </p> </td> 
   <td colname="col02"> <p>返回所有内容，除非它包含您输入的值。 </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>匹配<span class="term"> d e f</span>，但不匹配<span class="term"> c d e f</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不包含该短语 </p> </td> 
   <td colname="col02"> <p>返回不包含您的短语的所有内容。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>排除<span class="term"> abc</span>、<span class="term"> abc def</span>并匹配<span class="term"> def</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>等于 </p> </td> 
   <td colname="col02"> <p>返回一个完全匹配的项。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term">abc</span> 将是唯一返回的结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不等于 </p> </td> 
   <td colname="col02"> <p>返回与输入内容不完全匹配的任何内容。 </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>不匹配<span class="term"> a</span>。 </p> <p>匹配 <span class="term">a b c</span>。 </p> <p>匹配 <span class="term">abc</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>开始于 </p> </td> 
   <td colname="col02"> <p>返回以特定值开头的结果。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>匹配<span class="term"> abcd</span>，但不匹配<span class="term"> 1abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>结束于 </p> </td> 
   <td colname="col02"> <p>返回以特定值结束的结果。 </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>匹配 <span class="term">wxyz</span> 而不是 <span class="term">wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高级（特殊字符） </p> </td> 
   <td colname="col02"> <p>允许您使用正则表达式字符： </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Home*Page$" |运动 </p> </td> 
   <td colname="col3"> <p> 该操作定义了一个筛选器，该筛选器以<span class="term">主页</span>开头，然后查找零个或多个字符，最后以<span class="term">页面</span>结尾。 </p> <p>此外，它还定义了任何包含 <span class="term">sports</span> 的页面。 </p> <p>一些示例匹配： </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">主页 </li> 
     <li id="li_1351619156274092AEB2771D882AD357">主页和（其他字符）页面 </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">家庭运动 </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">体育页面 </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">运动 </li> 
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
   <td colname="col3"> <p>除非未与另一引号配对，否则不会转义。 例如，<span class="term"> 17" Display</span>不是短语。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> 通配符 </td> 
   <td colname="col3"> <p>与正则表达式中使用的星号相同。 </p> </td> 
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
   <td colname="col2"> 不为 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> | </td> 
   <td colname="col2"> 或 </td> 
   <td colname="col3"> <p>仅在<span class="term">高级（特殊字符）</span>筛选器中受支持。 </p> </td> 
  </tr> 
 </tbody> 
</table>
