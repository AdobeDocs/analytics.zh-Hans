---
description: Analytics 部署包括三个主要步骤。
keywords: Analytics 实施
seo-description: Analytics 部署包括三个主要步骤。
seo-title: 优化概述
solution: Analytics
subtopic: 故障诊断
title: 优化概述
topic: 开发人员和实施
uuid: 8e8cex5b-d4 b1-4d13-8525-39e4924 df247
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 优化概述

Analytics 部署包括三个主要步骤。

1. 首先是将 HTML 代码段复制到网站的每个页面（或页面模板）上。此 HTML 代码段非常小（400 至 1,000 字节），并包含 JavaScript 变量及其他用于数据收集过程的标识符。
1. 此代码段将调用 JavaScript 库文件，其中包括在量度收集过程中使用的 Analytics 特定 JavaScript 函数。如果正确地实施 Analytics￼ 代码，则浏览器执行 JavaScript 库文件所需的时间通常可以忽略不计。

1. 库文件向 Adobe 数据收集服务器发出图像请求。该服务器可收集正在提交的数据，并向访客的浏览器返回一个 1x1 的透明图像。第三步是向整个页面下载时间小幅添加增量。

>[!NOTE]
>
>客户可以采取其他步骤，最大限度地减少Analytics开销。

