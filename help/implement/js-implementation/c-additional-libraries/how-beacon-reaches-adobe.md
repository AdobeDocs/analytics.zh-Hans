---
description: 当移动设备请求 Web 服务器中的网页时，将通过网关发送该请求，网关会将移动设备请求（通常按 WAP 或 I-Mode 协议）转换为 HTTP 请求再发送到 Web 服务器。
keywords: Analytics实施；网关；wap；i-mode；wbmp
seo-description: 当移动设备请求 Web 服务器中的网页时，将通过网关发送该请求，网关会将移动设备请求（通常按 WAP 或 I-Mode 协议）转换为 HTTP 请求再发送到 Web 服务器。
seo-title: 移动协议网络网关
solution: Analytics
title: 移动协议网络网关
topic: 开发人员和实施
uuid: a2c92ce2-53a9-4b5b-be1 a-89d9 f1 bf776 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 移动协议网络网关

当移动设备请求 Web 服务器中的网页时，将通过网关发送该请求，网关会将移动设备请求（通常按 WAP 或 I-Mode 协议）转换为 HTTP 请求再发送到 Web 服务器。

当移动设备请求 Web 服务器中的网页时，将通过网关发送该请求，网关会将移动设备请求（通常按 WAP 或 I-Mode 协议）转换为 HTTP 请求再发送到 Web 服务器。Web 服务器会对网关作出响应，进而将请求转发至手机。此网关的运行方式极其类似于标准代理服务器。但不同的是，网关可将移动设备的用户代理字符串传递到 Web 服务器。这样，Web 服务器会作出响应并发送一个专为发出请求的设备创建的网页。

因为 WAP 移动设备的屏幕大小有限，所以移动页面通常较为简洁，一般只包含文本和一张缓存图像。在向多个网页添加图像标记时，Adobe 服务器会在每个页面上发送图像请求。若返回的是 WBMP 图像，Adobe 服务器会指示浏览器不缓存该图像。因此，会在后续网页上再次请求该图像。应当使用上述随机数字来阻止未遵守 Adobe 不缓存指令的浏览器。
