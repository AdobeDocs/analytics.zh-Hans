---
description: 区段生成器中创建的所有区段并非都与 Data Warehouse 兼容。此表列出支持的功能。
title: Data Warehouse 区段兼容性
feature: 区段划分
uuid: 370258c5-8614-4434-871c-41753ed77f5c
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 100%

---

# Data Warehouse 区段兼容性

区段生成器中创建的所有区段并非都与 [!DNL Data Warehouse] 兼容。此表列出支持的功能。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace、Reports &amp; Analytics </th> 
   <th> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td > <b>排除容器</b> </td> 
   <td> 在任何级别都受支持 </td> 
   <td> 只在顶级的特殊案例中受支持 </td> 
  </tr> 
  <tr> 
   <td> <b>顺序区段</b> </td> 
   <td> 受支持 </td> 
   <td> 不受支持 </td> 
  </tr> 
  <tr> 
   <td> <b>AND 和 OR 可自由组合不受限制</b> </td> 
   <td> 受支持 </td> 
   <td> 存在一些限制. 请参阅下表的*注释*。 </td> 
  </tr> 
  <tr> 
   <td> <b>嵌套的容器</b> </td> 
   <td> 受支持 </td> 
   <td> 一些限制（必须减小范围，例如访客可以包含点击，但点击不能包含访客） </td> 
  </tr> 
  <tr> 
   <td> <b>维度</b> </td> 
   <td>将维度拖动到区段生成器的“定义”<span class="uicontrol"></span>字段中，以便了解其产品兼容性的相关信息。例如，仅在 Analysis Workspace、Reports &amp; Analytics 中支持这些维度： 
    <ul> 
     <li>登录服务器 </li> 
     <li>登录类别 </li> 
     <li>登录日期 </li> 
     <li>所有搜索页面排名 </li> 
    </ul> </td> 
   <td> 将维度拖动到区段生成器的“定义”<span class="uicontrol"></span>字段中，以便了解其产品兼容性的相关信息。例如，这些维度只在“Data Warehouse”中受到支持： 
    <ul> 
     <li>IP 地址 </li> 
     <li>页面 URL </li> 
     <li>访客 ID </li> 
     <li>Experience Cloud 访客 ID </li> 
    </ul> <p>以下维度<b>不能</b>在 Data Warehouse 区段中使用： </p> 
    <ul> 
     <li>所有搜索页面排名 </li> 
     <li>上午/下午 </li> 
     <li>日期 </li> 
     <li>每周时间 </li> 
     <li>每年的某一天 </li> 
     <li>登录业务单位 </li> 
     <li>登录（以“登录”开头的所有维度，“登录页面”除外） </li> 
     <li>退出（以“退出”开头的所有维度，“退出链接”和“退出页面”除外） </li> 
     <li>层次结构（以层次结构开头的所有维度） </li> 
     <li>点击深度 </li> 
     <li>点击类型 </li> 
     <li>几点钟 </li> 
     <li>月份 </li> 
     <li>页面未找到 </li> 
     <li>付费搜索 </li> 
     <li>季度 </li> 
     <li>回访频度 </li> 
     <li>单页面访问量 </li> 
     <li>发生事件之前逗留的时间 </li> 
     <li>页面逗留时间 - 分段统计 </li> 
     <li>每次访问逗留时间 - 分段统计 </li> 
     <li>跟踪选择退出的原因 </li> 
     <li>美国各州 </li> 
     <li>工作日/周末 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <b>区段堆叠</b> </td> 
   <td> 受支持 </td> 
   <td> 受支持 </td> 
  </tr>
  <tr>
    <td><b>“等于以下任意一项”运算符和“不等于任一项”运算符</b></td>
    <td>受支持</td>
    <td>不受支持</td>
  </tr>
 </tbody> 
</table>

*注意：在使用 `AND/OR` 时，Data Warehouse 不支持使用 `exclusion` 或 `without` 容器的所有情况。在使用此类组合时，Data Warehouse 仅支持那些可以重写为 `A AND NOT B`（或&#x200B;**包括此特征**和&#x200B;**排除此特征**）的区段。*
