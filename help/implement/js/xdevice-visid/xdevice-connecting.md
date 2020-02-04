---
description: 跨设备访客识别可帮助您连接跨多个设备的访客。跨设备访客识别使用访客 ID 变量 s.visitorID 来关联跨设备的用户。
keywords: Analytics Implementation
subtopic: Visitors
title: 跨设备连接用户
topic: Developer and implementation
uuid: 6243957b-5cc1-49ef-aa94-5b5ec4eac313
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# 跨设备连接用户

> [!IMPORTANT]不再建议使用这种方法来识别跨设备访客。请参 [阅组件用户指南中](/help/components/cda/cda-home.md) 的跨设备分析。

跨设备访客识别可帮助您连接跨多个设备的访客。Cross-device visitor identification uses the `visitorID` variable to associate a user across devices. 在识 `visitorID` 别唯一访客时，该变量将优先级设置为最高。

当您使用自定义访客ID发送点击时，Adobe会检查是否有任何具有匹配访客ID的访客资料。 如果存在访客资料，则从该点开始使用系统中已有的访客资料，而不再使用以前的访客资料。

Setting the `visitorID` variable is typically set after authentication, or after a visitor performs some other action that allows you to uniquely identify them independently of the device that is used. 有效标识符包括其用户名、电子邮件地址的哈希值或不包含任何个人识别信息的内部ID。

客户从每台设备登录后，他们都会绑定到同一个用户配置文件。 如果访客稍后在设备上注销，则他们继续属于同一访客配置文件，因为Adobe会识别每台设备上的浏览器cookie属于同一访客配置文件。 Adobe建议在删 `visitorID` 除浏览器Cookie时尽可能使用变量。

## 限制

使用您自己的自定义访客ID，您可以更好地控制访客的识别方式，但这有其局限性。

* **访客重复数据消除不具有追溯性**:如果访客首次访问您的网站，则进行身份验证后，将计为两个唯一访客。 一个唯一访客计数是自动生成的通用Analytics ID，另一个唯一访客计数是自定义访客ID在他们登录时的计数。 每次访客使用新设备或清除其cookie时，都会出现这种独特访客复制。
* **与Experience Cloud ID服务不兼容**:自从引入跨设备访客识别功能后，Adobe发布了更强大、更可靠的跨设备跟踪访客的方法。 这些新的识别方法与自定义访客ID覆盖不兼容。 如果您计划使用ID服务、跨设备分析(CDA)或设备合作，Adobe强烈建议不要使用该变 `visitorID` 量。
