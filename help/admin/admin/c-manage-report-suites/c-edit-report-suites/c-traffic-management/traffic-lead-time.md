---
description: Adobe 要求预先通知新帐户设置、流量尖峰和流量增长。硬件必须预先进行分配，以最大程度减小延迟以及对整体系统可能造成的负面影响。
title: 流量增长必需的前置时间
feature: Traffic Management
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 6f7f46b0fee46e572a65f639ea511478c0118f4e
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 78%

---

# 流量增长必需的前置时间

Adobe 要求预先通知新帐户设置、流量尖峰和流量增长。硬件必须预先进行分配，以最大程度减小延迟以及对整体系统可能造成的负面影响。

硬件的分配是由通过 Reports &amp; Analytics 用户界面提交的警报所驱动的。

>[!IMPORTANT]
>
>Adobe 无法满足“占位”流量更改请求。除非另有指示，否则尽可能地遵循建议的前置时间，这包括不要过早地发送警报。请参阅[安排流量尖峰](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)或[指定永久性流量增长](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)。

使用以下准则来确定您必须提前多久提交流量警报：

## 硬件分配前置时间


<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 流量更改类型 </th>
   <th colname="col2" class="entry"> 所需前置时间 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 新帐户设置 </td>
   <td colname="col2"> <ul><li>3个工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 与过去30天相比，日均流量的流量激增或突然永久性流量增长高达25%</td>
   <td colname="col2"> <ul><li>每日点击量&lt; 100M的报表包：无需通知</li><li>每日点击量超过1亿次的报表包：5个工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 与过去30天相比，日均流量的流量激增或突然永久性增长超过25%</td>
   <td colname="col2"> <ul><li>5个工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 假日事件10月至12月 </td>
   <td colname="col2"> <ul><li>一个日历月</li></ul> </td>
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
