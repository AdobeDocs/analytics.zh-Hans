---
description: 可通过多种方法来实施 Adobe Analytics。
keywords: Analytics 实施;实施方法;dynamic tag management;dtm;javascript
seo-description: 可通过多种方法来实施 Adobe Analytics。
seo-title: 选择实施方法
solution: Analytics
title: 选择实施方法
topic: 开发人员和实施
uuid: 20d3317f-7c63-4421-93e0-fff60dbd9f87
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# 选择实施方法

可通过多种方法来实施 Adobe Analytics。

* [!UICONTROL Adobe Experience Platform Launch]（推荐）
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Adobe Experience Platform Launch] {#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Experience Platform Launch] 是 Adobe 推出的新一代网站标记和移动 SDK 管理功能。[!UICONTROL Experience Platform Launch] 为您提供了一种简单的方式来部署和管理所有用来改善相关客户体验的分析、营销和广告集成。

[!UICONTROL Experience Platform Launch] 可让任何人构建与维护他们自身与 [!DNL Experience Platform Launch] 的集成，这也称为扩展。[!UICONTROL Experience Platform Launch] 客户（Web 客户或移动设备客户）可在应用商店中获取这些扩展，从而可以快速安装、配置和部署自己的集成。

For more information, see [Getting Started with Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL Dynamic Tag Management] 可自动完成实施 [!DNL Analytics] 所需完成的大多数具体工作。在基于表单的界面中输入所需信息，[!DNL Dynamic Tag Management] 即会生成您需要添加到页面的代码。熟悉 JavaScript 并了解以下基本的 Analytics 术语是非常有用的

* [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) 是什么以及它的工作原理是什么
* 何时使用[自定义事件](/help/implement/analytics-terminology-basics/c-props-evars/event-custom.md)）

有关如何访问及如何启动和运行动态标签管理的信息，请参阅“动态标签产品文档”中的[快速入门](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html)。

有关更多信息，请参阅[使用 Dynamic Tag Management 实施 Analytics](/help/implement/c-implement-with-dtm/dtm-implementation-overview.md)。

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

JavaScript 实施方法要求您在页面上手动配置 JavaScript 代码。如果您使用 Experience Platform Launch 或 Dynamic Tag Management 实施方法，则可以简化很多工作。不过，有些客户可能仍然需要使用 JavaScript 方法。

JavaScript 实施具有以下要求：

* 良好的 JavaScript 技能
* 对 Analytics 概念和术语的扎实理解

有关更多信息，请参阅[使用 JavaScript 实施 Analytics](/help/implement/js-implementation/javascript-implementation-overview.md)。
