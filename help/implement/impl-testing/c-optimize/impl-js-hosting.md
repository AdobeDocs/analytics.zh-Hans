---
description: 将指向 JavaScript 库文件的调用置于页面顶部，可确保图像成为最先下载的元素之一。
keywords: Analytics 实施
seo-description: 将指向 JavaScript 库文件的调用置于页面顶部，可确保图像成为最先下载的元素之一。
seo-title: JavaScript文件位置和并发
solution: Analytics
subtopic: 故障诊断
title: JavaScript文件位置和并发
topic: 开发人员和实施
uuid: ed5118a8-b142-4fab-8aa1-92d931 cc1439
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# JavaScript文件位置和并发

将指向 JavaScript 库文件的调用置于页面顶部，可确保图像成为最先下载的元素之一。

大部分 Web 浏览器可同时下载多个图像。通常，可在同一时间下载三至四个图像。

由于大部分的 Web 浏览器可同时下载多个元素，因此很多常用浏览器（包括 Internet Explorer）的“状态栏”都不会准确显示浏览器正在尝试加载哪个元素。例如，“状态栏”可能会报告您的浏览器正在等待下载图像 1。但网络数据包测试结果却表明浏览器已收到图像 1 并正在等待下载图像 2。

>[!NOTE]
>
>由于第三方Internet性能审计提供商(如Keynote Systems)按顺序(而非同时)下载页面图像元素，因此它们不模拟典型的用户体验。

