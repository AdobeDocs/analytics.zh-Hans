---
description: 了解为什么区段生成器中创建的所有区段都不与Data Warehouse兼容。 了解支持的函数。
title: Data Warehouse 区段兼容性
feature: Segmentation
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 53%

---

# 数据仓库区段兼容性

区段生成器中创建的所有区段并非都与[!DNL Data Warehouse]兼容。 此表列出支持的功能。

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
   <td> 在任何级别都支持 </td> 
   <td> 仅在顶层的特殊情况下受支持 </td> 
  </tr> 
  <tr> 
   <td> <b>顺序区段</b> </td> 
   <td> 受支持 </td> 
   <td> 不受支持 </td> 
  </tr> 
  <tr> 
   <td> <b>AND和OR可以组合而不受限制</b> </td> 
   <td> 受支持 </td> 
   <td> 存在一些限制. 请参阅下表的*注释*。 </td> 
  </tr> 
  <tr> 
   <td> <b>嵌套容器</b> </td> 
   <td> 受支持 </td> 
   <td> 有些限制（范围必须缩小，例如，访客可以包含点击，反之则不行） </td> 
  </tr> 
  <tr> 
   <td> <b>维度</b> </td> 
   <td>将维度拖放到区段生成器的<span class="uicontrol">定义</span>字段中，以了解其产品兼容性的相关信息。 例如，仅在 Analysis Workspace、Reports &amp; Analytics 中支持这些维度： 
    <ul> 
     <li>登录服务器 </li> 
     <li>条目类别 </li> 
     <li>输入日期 </li> 
     <li>所有搜索页面排名 </li> 
    </ul> </td> 
   <td> 将维度拖放到区段生成器的<span class="uicontrol">定义</span>字段中，以了解其产品兼容性的相关信息。 例如，仅在Data Warehouse中支持以下维度： 
    <ul> 
     <li>IP 地址 </li> 
     <li>页面 URL </li> 
     <li>访客 ID </li> 
     <li>Experience Cloud 访客 ID </li> 
    </ul> <p>以下维度<b>不能</b>在 Data Warehouse 区段中使用： </p> 
    <ul> 
     <li>所有搜索页面排名 </li> 
     <li>上午/下午 </li> 
     <li>月中几号 </li> 
     <li>每周时间 </li> 
     <li>每年的某一天 </li> 
     <li>登录业务单元 </li> 
     <li>登入（以“登入”开头的所有维度，除“登入页面”之外） </li> 
     <li>退出（以“退出”开头的所有维度，但“退出链接”和“退出页面”除外） </li> 
     <li>层次结构（以层次结构开头的所有维） </li> 
     <li>点击深度 </li> 
     <li>点击类型 </li> 
     <li>小时日 </li> 
     <li>月份 </li> 
     <li>页面未找到 </li> 
     <li>付费搜索 </li> 
     <li>季度 </li> 
     <li>回访频率 </li> 
     <li>单页面访问次数 </li> 
     <li>发生事件之前逗留的时间 </li> 
     <li>页面逗留时间 — 分段统计 </li> 
     <li>每次访问逗留时间 — 分段统计 </li> 
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
    <td>不支持</td>
  </tr>
 </tbody> 
</table>

*注意：在使用 `AND/OR` 时，Data Warehouse 不支持使用 `exclusion` 或 `without` 容器的所有情况。 在使用此类组合时，Data Warehouse 仅支持那些可以重写为 `A AND NOT B`（或&#x200B;**包括此特征**&#x200B;和&#x200B;**排除此特征**）的区段。*
