---
description: Adobe 要求预先通知新帐户设置、流量尖峰和流量增长。硬件必须预先进行分配，以最大程度减小延迟以及对整体系统可能造成的负面影响。
title: 流量增长必需的前置时间
feature: Report Suite Settings
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 100%

---

# 流量增长必需的前置时间

Adobe 要求预先通知新帐户设置、流量尖峰和流量增长。硬件必须预先进行分配，以最大程度减小延迟以及对整体系统可能造成的负面影响。

>[!IMPORTANT]
>
>Adobe 无法满足“占位”流量更改请求。除非另有指示，否则尽可能地遵循建议的前置时间，这包括不要过早地发送警报。

使用以下准则来确定您必须提前多久提交流量警报：

## 硬件分配前置时间


<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 流量更改类型 </th>
   <th colname="col2" class="entry"> 所需的前置时间 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 新帐户设置 </td>
   <td colname="col2"> <ul><li>3 个工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 与过去 30 天相比，平均每日流量的流量尖峰或突发的永久性流量增加高达 25%</td>
   <td colname="col2"> <ul><li>每日点击量不到 1 亿次的报告包：无需通知</li><li>每日点击量超过 1 亿次的报告包：5 个工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 与过去 30 天相比，平均每日流量的流量尖峰或突发的永久性流量增加超过 25%</td>
   <td colname="col2"> <ul><li>5 个工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 10 月至 12 月期间的假日活动 </td>
   <td colname="col2"> <ul><li>一个日历月</li></ul> </td>
  </tr>
 </tbody>
</table>

其他考虑事项：

* 如果您的多个报告包一开始具有或逐渐增加到上面所列数量，则可应用前置时间，以作为每个报告包的预计流量总和。
* 获取以下信息以提交流量更改：

   * 报告包 ID
   * 预计的每日点击量
   * 起始日期

* 当流量减少或报告包被弃用时，也需要客户端警报。

## 由于未实现的流量导致的硬件取消分配

如果客户端警报中的预计流量没有在“起始日期”后的 4 周内实现，则对应新帐户、流量尖峰和流量增长的硬件将被取消分配。如果流量仍然预计会实现，则在流量增长时必须生成一个新的客户端警报。
