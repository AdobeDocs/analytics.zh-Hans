---
description: 跨设备访客识别可帮助您连接跨多个设备的访客。跨设备访客识别使用访客 ID 变量 s.visitorID 来关联跨设备的用户。
keywords: Analytics 实施
subtopic: Visitors
title: 跨设备连接用户
feature: Implementation Basics
exl-id: dfe278db-01de-4bba-b07a-66d52de1dbe2
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 95%

---

# 跨设备连接用户

>[!IMPORTANT]
>
>不再建议使用这种方法来识别跨设备访客。相关信息，请参阅组件用户指南中的[跨设备分析](/help/components/cda/overview.md)。

跨设备访客识别可帮助您连接跨多个设备的访客。跨设备访客识别使用 `visitorID` 变量来关联跨设备的用户。在识别独特访客时，`visitorID` 变量享有最高优先级别。

当您使用自定义访客 ID 发送点击时，Adobe 会检查是否存在任何具有匹配访客 ID 的访客资料。如果存在，则会从此时开始使用系统中已存在的该访客资料，并且不再使用之前的访客资料。

`visitorID` 变量通常在出现以下情况后进行设置：执行身份验证；或访客执行了某些其他操作，使您能够脱离他们所使用的设备进行唯一识别。有效标识符包含由用户名、电子邮件地址或内部 ID 构成且不含任何个人身份信息的哈希。

客户从每台设备登录后，所有这些设备都会绑定到同一个用户资料。如果访客稍后在设备上注销，则这些设备将继续属于同一访客资料，因为 Adobe 可识别出每台设备上的浏览器 Cookie 属于同一访客资料。Adobe 建议尽量使用 `visitorID` 变量以防浏览器 Cookie 被删除。

## 限制

通过使用您自己的自定义访客 ID，您可以更好地控制访客的识别方式，但这同时也存在限制。

* **无法实现访客计数去重**：如果一位访客在首次访问您的网站后进行身份验证，则会计为两个独特访客。其中，会将自动生成的 Analytics ID 计为一个独特访客，并将登录时使用的自定义访客 ID 计为另一个独特访客。每次访客使用新设备或清除其 Cookie 时，都会按这种方式重复计算独特访客数。
* **与 Experience Cloud ID 服务不兼容**：自从引入跨设备访客识别功能后，Adobe 推出了更强大、更可靠的跨设备访客跟踪方法。这些新的识别方法与自定义访客 ID 覆盖不兼容。如果您计划使用ID服务或Cross-Device Analytics (CDA)，Adobe强烈建议不要使用`visitorID`变量。
