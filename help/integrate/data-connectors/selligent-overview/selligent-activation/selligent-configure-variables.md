---
description: 此集成需要为每个报表包实施保留个eVar。
seo-description: 此集成需要为每个报表包实施保留个eVar。
seo-title: 为Seriagent配置Analytics变量
solution: Analytics
title: 为Seriagent配置Analytics变量
uuid: 3b7b8b4b-7614-4439-bcb0-dpc5304844
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configure Analytics Variables for Selligent{#configure-analytics-variables-for-selligent}

此集成需要为每个报表包实施保留个eVar。

除了这些eVar之外，还可能保留一些事件，具体取决于Serigent中的数据，您希望在Analytics中查看这些事件。下列eVar和事件如下所述：

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量类型 </th> 
   <th colname="col2" class="entry"> 变量名称 </th> 
   <th colname="col3" class="entry"> 如何使用它 </th> 
   <th colname="col4" class="entry"> 设置 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 消息ID </td> 
   <td colname="col3"> 捕获单个电子邮件营销活动标识。 </td> 
   <td colname="col4"> <p><b>状态</b>：已启用 </p> <p><b>分配</b>：最近使用 </p> <p><b>到期后</b>过期：“商业决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> EV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> 捕获单击电子邮件营销活动的客户的匿名标识。 </td> 
   <td colname="col4"> <p><b>状态</b>：已启用 </p> <p><b>分配</b>：最近使用 </p> <p><b>到期后</b>过期：“商业决策” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 已发送 </td> 
   <td colname="col3"> 存储从Seriligent发送的电子邮件数量。 </td> 
   <td colname="col4"> <p><b>类型</b>：数字 </p> <p><b>参与</b>：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 已交付 </td> 
   <td colname="col3"> 存储已送达电子邮件的数量。 </td> 
   <td colname="col4"> <p><b>类型</b>：数字 </p> <p><b>参与</b>：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 查看次数 </td> 
   <td colname="col3"> 存储已查看的唯一电子邮件数。 </td> 
   <td colname="col4"> <p><b>类型</b>：数字 </p> <p><b>参与</b>：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 点击次数 </td> 
   <td colname="col3"> 存储任何电子邮件的点击次数。 </td> 
   <td colname="col4"> <p><b>类型</b>：数字 </p> <p><b>参与</b>：已启用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 退回 </td> 
   <td colname="col3"> 存储退回的电子邮件数。 </td> 
   <td colname="col4"> <p><b>类型</b>：数字 </p> <p><b>参与</b>：已启用 </p> </td> 
  </tr> 
 </tbody> 
</table>

