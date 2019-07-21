---
description: 示例中包含常见客户交互中发送的服务器调用范例。
keywords: Analytics 实施
seo-description: 示例中包含常见客户交互中发送的服务器调用范例。
seo-title: 示例访问
solution: Analytics
subtopic: 访客
title: 示例访问
topic: 开发人员和实施
uuid: bc5f8f56-52e3-42d8-af1 a-7f5 c7 b9496 c0
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 示例访问

>[!IMPORTANT]
>
>不再建议跨设备识别访客的方法。Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

示例中包含常见客户交互中发送的服务器调用范例。

| 服务器调用 | 操作 | 访客 ID Cookie | 访客 ID 变量 | 有效访客 ID | 访问页数 | 访问量 |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | 访客点击营销电子邮件中的链接，并从家庭计算机中访问您的网站。此访客过去还曾 7 次访问您的网站。 | 1 | - | 1 | 1 | 8 |
| 2-8 | 在您的网站上访问了另外的 7 个页面。 | 1 | - | 1 | 2-8 | 8 |
| 9 | 在家庭计算机上验证。 | 1 | CID1 | CID1 | 9 <br>This is CID1's first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.</br> | 8 |
| 10 | 访问另外一个页面。 | 1 | CID1 | CID1 | 10 | 8 |
| 11 | 使用办公室的笔记本电脑打开网站。此访客之前没有用这台设备访问过您的网站。 | 2 | - | 2 | 1 | 1 |
| 12 | 在笔记本电脑上验证。 | 2 | CID1 | CID1 | 1 | 9 |
| 13 | 查看另外一个页面。 | 2 | CID1 | CID1 | 2 | 9 |