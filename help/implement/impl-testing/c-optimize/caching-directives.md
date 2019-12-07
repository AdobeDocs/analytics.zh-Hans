---
description: JavaScript 库文件将在用户首次加载页面之后，被放入用户浏览器的缓存中。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 缓存指令
topic: Developer and implementation
uuid: 6bd2c26d-93ee-4039-8beb-6a6b16218a07
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 缓存指令

JavaScript 库文件将在用户首次加载页面之后，被放入用户浏览器的缓存中。

Adobe 客户应确保其 Web 服务器设置妥当，以便充分利用此项功能。例如，应确保 NO-CACHE 设置为 false。此外，还应确保过期日期离当前时间足够远。并确保所有代理缓存均已进行正确配置。请参阅客户的 Web 服务器文档，以了解更多详细信息。
