---
description: Adobe Mobile Services UI 将Adobe Analytics 报表包中的数据与发送推送通知和生成应用程序内消息的功能结合了起来。
title: Mobile Services 中的 VRS 支持
uuid: 1b11279e-d0d8-48c5-a5b5-8020d5ed39da
translation-type: tm+mt
source-git-commit: 9193a520b13a0717a3383a32b39936f278c49d49

---


# Mobile Services 中的 VRS 支持

Adobe Mobile Services UI 将Adobe Analytics 报表包中的数据与发送推送通知和生成应用程序内消息的功能结合了起来。

## Mobile Services 中的 VRS 支持 {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

Adobe Mobile Services UI 将Adobe Analytics 报表包中的数据与发送推送通知和生成应用程序内消息的功能结合了起来。

Adobe Mobile Services 支持虚拟报表包。但是，如果您计划创建包含多个应用程序数据的虚拟报表包，且计划执行消息传送活动，您必须将各个的应用程序 ID 分别指定为相应参数。如果您创建的是推送消息，则应用程序 ID 需要是您所使用区段的其中一个参数。如果您创建的是应用程序内消息，则应用程序 ID 需要是您为该消息所设定的特质的其中一个参数。如果没有将应用程序 ID 指定为相应的参数，则会对所有应用程序中满足该区段标准的所有用户发送/触发消息。

有关更多详细信息，请参阅 Adobe Mobile Services 文档中的[虚拟报表包](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/c-mob-vrs.html)。
