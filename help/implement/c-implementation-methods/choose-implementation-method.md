---
description: 可通过多种方法来实施 Adobe Analytics。
keywords: Analytics实施；实施方法；动态标签管理；dm；javascript
seo-description: 可通过多种方法来实施 Adobe Analytics。
seo-title: 选择实施方法
solution: Analytics
title: 选择实施方法
topic: 开发人员和实施
uuid: 20d3317f-7c63-4421-93e0-fff60 dbd9 f87
translation-type: tm+mt
source-git-commit: b1e69abd65f171b804e7f56031e594890bbd27bb

---


# 选择实施方法

可通过多种方法来实施 Adobe Analytics。

* [!UICONTROL Adobe Experience Platform Launch(] 推荐)
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Adobe Experience Platform Launch]{#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Experience Platform Launch] 是Adobe新一代网站标签和移动SDK管理功能。[!UICONTROL Experience Platform Launch] 可让您轻松部署和管理所有必要的分析、营销和广告集成，以支持相关客户体验。

[!UICONTROL Experience Platform Launch] 使任何人能够构建和维护自己的集成( [!DNL Experience Platform Launch]称为扩展)。These extensions are available to web and mobile [!UICONTROL Experience Platform Launch] customers in an app-store experience, so customers can quickly install, configure, and deploy their integrations.

For more information, see [Getting Started with Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL Dynamic Tag Management] 可自动完成实施 [!DNL Analytics]所需的大量细节工作。Enter the required information in a form-based interface, and [!DNL Dynamic Tag Management] generates the code you need to add to your pages.
熟悉JavaScript非常有用，并了解基本Analytics术语，如

* [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) 是什么以及它的工作原理是什么
* 何时需使用 [自定义事件](../../implement/analytics-terminology-basics/c-props-evars/event-custom.md#concept_CDA3C98C85B24A71B4B5C71F24BF918F)

有关如何访问及如何启动和运行动态标签管理的信息，请参阅“动态标签产品文档”中的[快速入门](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html)。

有关更多信息，请参阅[利用动态标签管理实现分析](../../implement/c-implement-with-dtm/dtm-implementation-overview.md)。

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

JavaScript 实施方法要求您在页面上手动配置 JavaScript 代码。如果您使用Experience Platform Launch或Dynamic Tag Management实施方法，可以简化大部分这种工作。不过，有些客户可能仍然需要使用 JavaScript 方法。

JavaScript 实施具有以下要求：

* 良好的 JavaScript 技能
* 对 Analytics 概念和术语的扎实理解

有关更多信息，请参阅[使用JavaScript实施分析](../../implement/js-implementation/javascript-implementation-overview.md)。
