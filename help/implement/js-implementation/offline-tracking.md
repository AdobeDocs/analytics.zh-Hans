---
description: 您可以使用下面的变量和函数在应用程序离线时存储测量调用。
keywords: Analytics 实施
seo-description: 您可以使用下面的变量和函数在应用程序离线时存储测量调用。
seo-title: 离线跟踪
solution: Analytics
title: 离线跟踪
topic: 开发人员和实施
uuid: f7c55aef-28a4-4f2f-8f47-792a05f9525b
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 离线跟踪

您可以使用下面的变量和函数在应用程序离线时存储测量调用。

>[!NOTE]
>
>要启用脱机跟踪，您的报表包必须启用时间戳。如果报表包已启用时间戳，那么您的 `trackOffline` 配置属性&#x200B;*必须*&#x200B;为 true。如果您的报表包未启用时间戳，则 `trackOffline` 配置属性&#x200B;*必须*&#x200B;为 false。如果配置不正确，数据将会丢失。如果您不确定报表包是否已启用时间戳，[联系客户关怀人员](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics)

启用后，离线 AppMeasurement 按照下面的方式运行：

* 应用程序发送服务器调用，但是数据传输失败。
* AppMeasurement 生成当前点击时间戳。
* AppMeasurement 缓冲点击数据，并将缓冲的点击数据备份为永久存储以避免数据丢失。

AppMeasurement 在每次后续点击时或经过 `offlineThrottleDelay` 定义的间隔后，尝试发送缓冲的点击数据，并保持原始点击顺序。如果数据传输失败，它会继续缓冲点击数据（这在设备离线时仍继续）。

<table id="table_E8FD8C89025C4E819FE2FEBC7A78984D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 属性或方法 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>trackOffline </p> </td> 
   <td colname="col2"> <p>默认值：false </p> <p>启用或禁用对测量库的离线跟踪。 </p> <p> <b>示例：</b> </p> 
    <code class="syntax c">s. trackOffline= true； </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineLimit </p> </td> 
   <td colname="col2"> <p>默认值：无限制 </p> <p>队列中存储的离线点击的最大数量。 </p> <p> <b>示例：</b> </p> 
    <code class="syntax c">s. offlineHitLimit=100； </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineThrottleDelay </p> </td> 
   <td colname="col2"> <p>默认值：0 </p> <p>以毫秒为单位指定一个停顿（或延迟），用于在 AppMeasurement 检测到活动网络连接时发送缓冲的点击数据。执行此操作可降低发送多个应用程序点击对性能造成的影响。 </p> <p>例如，如果 offlineThrottleDelay=1000，则发送点击数据需要 300 毫秒，AppMeasurement 将等待 700 毫秒再发送下一个缓冲点击。 </p> 
    <code class="syntax c">s. offlineThrottleDelay=1000； </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forceOnline </p> <p>forceOffline </p> </td> 
   <td colname="col2"> <p> 手动设置测量对象的在线或离线状态。库会自动检测设备离线或在线，因此仅在希望强制离线测量时才需要使用这两种方法。<code>forceOnline</code> 仅用于在手动离线后恢复到在线状态。 </p> <p>离线测量时： </p> 
    <ul id="ul_5A9CFD2968F64F938652C1D779EB7589"> 
     <li id="li_AF074C55DFED4DC8BD8CF3D25805040C"> 如果 <code>trackOffline</code> 为 true：会存储点击量，直到测量在线。 </li> 
     <li id="li_6A623377462548DB97C31654EADCFAF3"> 如果 <code>trackOffline</code> 为 false：会丢弃点击量。 </li> 
    </ul> <p> <b>示例：</b> </p> 
    <code class="syntax c">s. forceOffline()；

s.forceOnline();
</code> </td>
</tr> 
 </tbody> 
</table>
