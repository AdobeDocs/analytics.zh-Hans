---
description: Adobe 要求预先通知新帐户设置、流量尖峰和流量增长。硬件必须预先进行分配，以最大程度减小延迟以及对整体系统可能造成的负面影响。
title: 流量增长必需的前置时间
feature: Admin Tools
uuid: aa3fb882-51b0-458f-917b-7c54d5659623
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 100%

---

# 流量增长必需的前置时间

Adobe 要求预先通知新帐户设置、流量尖峰和流量增长。硬件必须预先进行分配，以最大程度减小延迟以及对整体系统可能造成的负面影响。

硬件的分配是由通过 Reports &amp; Analytics 用户界面提交的警报所驱动的。

>[!IMPORTANT]
>
> Adobe 无法处理“占位符”流量更改请求。除非另有指示，否则尽可能地遵循建议的前置时间，这包括不要过早地发送警报。请参阅[计划流量尖峰](/help/admin/c-traffic-management/t-traffic-schedule-spike.md)或[指定永久性流量增长](/help/admin/c-traffic-management/t-traffic-permanent.md)。

使用以下准则来确定您必须提前多久提交流量警报：

## 硬件分配前置时间

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 每日流量估计（点击） </th>
   <th colname="col2" class="entry"> <p>所需的前置时间（一月至十月） </p> </th>
   <th colname="col3" class="entry"> <p>所需的前置时间（十一月至十二月） </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 最高 1,000,000 </td>
   <td colname="col2"> 无需前置时间 </td>
   <td colname="col3"> 无需前置时间 </td>
  </tr>
  <tr>
   <td colname="col1"> 1,000,000 - 5,000,000 </td>
   <td colname="col2"> 两个工作日 </td>
   <td colname="col3" morerows="3"> 定于十一月至十二月发生的所有流量增长都应在 9 月 1 日之前提交。这样就有充裕的时间来购买足以满足假期流量需要的容量。 </td>
  </tr>
  <tr>
   <td colname="col1"> 5,000,000 - 10,000,000 </td>
   <td colname="col2"> 一个日历周 </td>
  </tr>
  <tr>
   <td colname="col1"> 10,000,000 - 25,000,000 </td>
   <td colname="col2"> 两个日历周 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>高于 25,000,000 </p> </td>
   <td colname="col2"> 一个或多个月 </td>
  </tr>
 </tbody>
</table>

其他考虑事项：

* 如果您的多个报表包一开始具有或逐渐增加到上面所列数量，则可应用前置时间，以作为每个报表包的预计流量总和。
* 获取以下信息以提交流量更改：

   * 报表包 ID
   * 预计的每日点击量
   * 起始日期

* 当流量减少或报表包被弃用时，也需要客户端警报。

## 由于未实现的流量导致的硬件取消分配

如果客户端警报中的预计流量没有在“起始日期”后的 4 周内实现，则对应新帐户、流量尖峰和流量增长的硬件将被取消分配。如果流量仍然预计会实现，则在流量增长时必须生成一个新的客户端警报。
