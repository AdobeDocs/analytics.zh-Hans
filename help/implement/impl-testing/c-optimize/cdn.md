---
description: 内容传递服务或内容发布网络 (CDN)（如 Akamai 和 Speedera）可将网站内容置于网络的最前沿，即让经常请求的文档靠近其受访问的位置。
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: 内容传递服务/网络
topic: Developer and implementation
uuid: 6cb57c59-d0f9-4ca5-9f15-0e74e585a4a1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 内容传递服务/网络

内容传递服务或内容发布网络 (CDN)（如 Akamai 和 Speedera）可将网站内容置于网络的最前沿，即让经常请求的文档靠近其受访问的位置。

通常，这会减少访问延迟，降低带宽使用率和基础设施成本。

您的 JavaScript AppMeasurement 库文件可通过 CDN 传递至网站访客，以提升文件传递的性能。Adobe 客户需要确保他们已正确配置其 CDN 服务。CDN 是下载时间产生波动的常见原因，并且可能是造成下载时间发生变动最可能的原因。

标签管理器将所有 JavaScript 存储在 CDN 上。
