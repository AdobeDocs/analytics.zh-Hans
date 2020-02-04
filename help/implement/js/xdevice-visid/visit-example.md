---
description: 示例中包含常见客户交互中发送的服务器调用范例。
keywords: Analytics Implementation
subtopic: Visitors
title: 跨设备访客识别示例
topic: Developer and implementation
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: tm+mt
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# 跨设备访客识别示例

> [!IMPORTANT]不再建议使用这种方法来识别跨设备访客。请参 [阅组件用户指南中](/help/components/cda/cda-home.md) 的跨设备分析。

以下示例说明了跨设备访客识别如何使用在常见客户交互中发送的服务器调用示例工作。

| 服务器调用 | 操作 | 访客 ID Cookie | 访客 ID 变量 | 有效访客 ID | 访问页数 | 访问量 |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | 访客点击营销电子邮件中的链接，并从家庭计算机中访问您的网站。此访客过去还曾 7 次访问您的网站。 | 1 | - | 1 | 1 | 8 |
| 2-8 | 在您的网站上访问了另外的 7 个页面。 | 1 | - | 1 | 2-8 | 8 |
| 9 | 在家庭计算机上验证。 | 1 | CID1 | CID1 | 9 <br>(This is CID1&#39;s first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.) | 8 |
| 10 | 访问另外一个页面。 | 1 | CID1 | CID1 | 10 | 8 |
| 11 | 使用办公室的笔记本电脑打开网站。此访客之前没有用这台设备访问过您的网站。 | 2 | - | 2 | 1 | 1 |
| 12 | 在笔记本电脑上验证。 | 2 | CID1 | CID1 | 1 | 9 |
| 13 | 查看另外一个页面。 | 2 | CID1 | CID1 | 2 | 9 |

## 访问计数

Analytics在每次看到访问页码等于1的点击时对访问进行计数。

使用上表，新访问被计数4次：第1、9、11和12次点击。

## 访客计数

Analytics 将每个有效的独特访客 ID 算作一个独特访客。

使用上表，新访客被计数3次：在1,9和10中。

当您使用跨设备访客识别时，您看到的唯一访客数可能会增加。 同一次访问中可以对访客计数两次：对用户进行首次访问和验证用户身份后再次进行访问。

![](assets/visitors.png)

初始关联后，访问计数将恢复正常，因为访客通过其浏览器cookie关联。 如果访客稍后查看您的网站，接着进行验证，访客计数不会虚增，因为有效的访客 ID 在验证后不会发生更改。

![](assets/visitors_2.png)

确保在识别独特访客时尽可能保持一致。 例如，在用户通过身份验 `visitorID` 证后始终使用变量。
