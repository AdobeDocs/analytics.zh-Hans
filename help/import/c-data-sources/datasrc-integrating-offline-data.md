---
description: 数据源提供其他两种方式，用于将离线发生的事件集成到您的在线数据。
subtopic: Data sources
title: 交易和客户集成
topic-fix: Developer and implementation
uuid: 71f73a47-3436-4314-a182-36de4bd935ba
exl-id: d4e4388b-6449-4fef-a94d-01b3a52c2190
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 79%

---

# 交易和客户集成

数据源提供其他两种方式，用于将离线发生的事件集成到您的在线数据。

* [启用交易 ID 记录](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C)
* [交易集成](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_B3F281CEFF9B47E9A07F9851D61D415D)
* [客户集成](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_9F4AAD710D2543BDA834090A98115FBF)

这些集成将离线数据与特定的在线交易或在线访客关联。

## 启用交易 ID 记录 {#section_30D6D47AEC0F4A36B87EBFE4C858F20C}

交易 ID 可以从 UI 启用/禁用，而无需 ClientCare 的参与：

转到&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > 选择报表包 > **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 一般帐户设置]**。

<!-- 

<p>When contacting Customer Care, be prepared to provide the following information: </p> 
<ul id="ul_C425C7A074484650AFCCF0425E8E3F47"> 
 <li id="li_7640C0C4DF0C49749A3C37E5461DC22F">Report Suite ID of the data source for which you need transaction ID recording enabled. <p>In Data Sources, the report suite ID is the first part of the login appended by a random number that identifies the specific data source that was set up. For example, <code> RSID-drmossdev5 Login-drmossdev5_0001343430</code>. </p> </li> 
 <li id="li_4FB0E3EC7BE94A2DBEE9063365A71C9C">The Transaction ID expiration window (described in <a href="/help/import/c-data-sources/datasrc-tid-visitor-profile.md"  > Transaction ID and Visitor Profiles</a>). By default this is 90 days, but it can be extended to up to 2 years. </li> 
</ul>

 -->

要查看是否启用了“事务ID记录”，请导航至&#x200B;**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 数据源]**。

![](assets/transaction-ID-recording-active.png)

[!UICONTROL “管理”]选项卡将显示“交易 ID 记录”的状态。

## 客户集成 {#section_9F4AAD710D2543BDA834090A98115FBF}

客户 ID 用于指定客户的离线活动，并将其与在线活动关联。它们应当在以下情况下使用：

* 在 *`visitorID`* 变量中）。
* 客户活动转为离线（例如商机提供或购买）没有指定的时间点。

若要配置此类型的数据源，请参阅[访客 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)

## 交易集成 {#section_B3F281CEFF9B47E9A07F9851D61D415D}

交易 ID 用于记录某一时间点的访客状态。使用它们的时间点通常应在客户体验从在线转为离线时，例如：

* 为销售人员提供一个联系客户的商机。
* 进行在线购买，并且以后可以在商店退货。
* 购买以后可能会寻求支持的产品。

客户从在线转为离线时通常是匿名的。

“访问参与”量度中不包括交易ID事件（这些量度显示在市场营销报告中）。 这是因为交易ID数据与访问无关联(因为脱机事件通常不是联机事件的一部分)，而是与访客关联。

请参阅[事务ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)。
