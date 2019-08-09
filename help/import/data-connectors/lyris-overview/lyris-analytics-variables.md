---
description: 介绍要为每个报表包实施保留的eVar和事件。
seo-description: 介绍要为每个报表包实施保留的eVar和事件。
seo-title: 为Lyris配置Adobe Analytics变量
solution: Analytics
title: 为Lyris配置Adobe Analytics变量
uuid: 12e150c4-052a-481c-8c27-ef45 ee801977
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 为Lyris配置Adobe Analytics变量{#configure-adobe-analytics-variables-for-lyris}

介绍要为每个报表包实施保留的eVar和事件。

此集成要求为每个报表包实施保留至少2个eVar。除了这些eVar之外，还可以根据您希望在Analytics中看到的Lyris数据保留一些事件。下列eVar和事件如下表所示：

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量类型 </th> 
   <th colname="col2" class="entry"> 变量名称 </th> 
   <th colname="col3" class="entry"> 变量的使用方式 </th> 
   <th colname="col4" class="entry"> 设置 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 消息ID </td> 
   <td colname="col3"> 捕获单个电子邮件营销活动标识 </td> 
   <td colname="col4"> <p>状态：已启用 </p> <p>分配：最近使用 </p> <p>到期后过期：“商业决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> 捕获单击电子邮件营销活动的客户的匿名身份识别 </td> 
   <td colname="col4"> <p>状态：已启用 </p> <p>分配：最近使用 </p> <p>到期后过期：“商业决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-发送电子邮件 </td> 
   <td colname="col3"> 存储无。从Lyris发送的电子邮件 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-已打开电子邮件 </td> 
   <td colname="col3"> 存储无。已打开的电子邮件 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-打开的唯一电子邮件 </td> 
   <td colname="col3"> 存储无。已打开的唯一电子邮件 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-电子邮件点击率 </td> 
   <td colname="col3"> 存储无。任何电子邮件的点击次数 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-电子邮件弹回 </td> 
   <td colname="col3"> 存储无。收到的电子邮件 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris-电子邮件退订 </td> 
   <td colname="col3"> 存储无。已禁用的电子邮件订阅 </td> 
   <td colname="col4">类型：数字 <p>参与：已启用 </p> </td> 
  </tr> 
 </tbody> 
</table>

