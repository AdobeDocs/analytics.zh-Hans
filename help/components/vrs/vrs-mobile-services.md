---
description: Adobe Mobile Services UI 将Adobe Analytics 报表包中的数据与发送推送通知和生成应用程序内消息的功能结合了起来。
seo-description: Adobe Mobile Services UI 将Adobe Analytics 报表包中的数据与发送推送通知和生成应用程序内消息的功能结合了起来。
seo-title: 移动服务中的VRS支持
title: 移动服务中的VRS支持
uuid: 1b11279e-d0 d8-48c5 b5-8020d5 ed39 da
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 移动服务中的VRS支持

Adobe Mobile Services UI 将Adobe Analytics 报表包中的数据与发送推送通知和生成应用程序内消息的功能结合了起来。

## VRS support in Mobile Services {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

Adobe Mobile Services UI 将Adobe Analytics 报表包中的数据与发送推送通知和生成应用程序内消息的功能结合了起来。

Adobe Mobile Services 支持虚拟报表包。但是，如果您计划创建包含多个应用程序数据的虚拟报表包，且计划执行消息传送活动，您必须将各个的应用程序 ID 分别指定为相应参数。如果您创建的是推送消息，则应用程序 ID 需要是您所使用区段的其中一个参数。如果您创建的是应用程序内消息，则应用程序 ID 需要是您为该消息所设定的特质的其中一个参数。如果没有将应用程序 ID 指定为相应的参数，则会对所有应用程序中满足该区段标准的所有用户发送/触发消息。

有关更多详细信息，请参阅 Adobe Mobile Services 文档中的[虚拟报表包](https://marketing.adobe.com/resources/help/en_US/mobile/c_mob_vrs.html)。
