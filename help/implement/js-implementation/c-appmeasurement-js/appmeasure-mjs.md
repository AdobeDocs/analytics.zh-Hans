---
description: AppMeasurement for JavaScript 是一个新库，所提供的核心功能与 s_code.js 相同，但其设计更轻便，速度更快，非常适合在移动和桌面网站上使用。
keywords: appmeasurement;Analytics 实施;javascript;appmeasurement for javascript;初始化;检索 appmeasurement 实例;clear vars;clearvars;appmeasurement 实用程序;appmeasurement 实例;appmeasurement 好处
seo-description: AppMeasurement for JavaScript 是一个新库，所提供的核心功能与 s_code.js 相同，但其设计更轻便，速度更快，非常适合在移动和桌面网站上使用。
seo-title: 关于 AppMeasurement for JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: 关于 AppMeasurement for JavaScript
topic: 开发人员和实施
uuid: dc71ad7a-92bd-40cd-8fab-707f6f8472e2
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 关于 AppMeasurement for JavaScript

[!DNL AppMeasurement] for JavaScript 是一个新库，所提供的核心功能与 s_code.js 相同，但其设计更轻便，速度更快，非常适合在移动和桌面网站上使用。

## 迁移前的注意事项 {#section_B8E7B39E8469468883BA0B41234F21C4}

以下列表包含在切换到该新版 [!DNL AppMeasurement] 之前需要了解的更改：

* 不再支持某些插件。请参阅 [AppMeasurement 插件支持](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A)。
* 该库不支持动态帐户选择（[dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md)、[dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md) 和 [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)）。

* 库和页面代码可以部署在 `<head>` 标记中。
* JavaScript [!DNL AppMeasurement] 下载包中包含更新的模块代码，这些代码支持媒体和集成模块。但不支持调查模块。
* 现有页面代码与新版本兼容。
* 该库提供了一些本地实用工具，用来获取查询参数、读取和写入 Cookie，以及执行高级链接跟踪。

## 常见问题解答 {#section_9BD41B08F7B54197B230937714B9357A}

请参阅[常见问题解答](../../../implement/faq.md#concept_9BBC230E01114318BE9C08724F2040D3)，以了解有关性能、视频跟踪、移动设备等内容的信息。

## 初始化过程 {#section_F6D5680F6D134B6AB1F01C6235860635}

调用 `s_gi()`，从而传递报表包 ID 以初始化 [!DNL AppMeasurement] 实例：

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

在调用 `s_gi` 时，如果指定的 `s_account` 中不存在 [!DNL AppMeasurement] 实例，则会创建一个新实例。否则，会返回现有的实例。这有助于避免为同一帐户创建重复的对象。

## 检索 AppMeasurement 实例 {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

在整个代码中，调用全局 [s_gi() 函数](../../../implement/js-implementation/function-s-gi.md#concept_50EE6629F61A478BB67781408FBA04BD)以检索现有的 [!DNL AppMeasurement] 实例。

## 实用工具 {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] 提供了以下内置实用工具：

* [Util.cookieRead](../../../implement/js-implementation/util-cookieread.md#concept_33BD774A90504F2C8094DDC16D47440D)
* [Util.cookieWrite](../../../implement/js-implementation/util-cookiewrite.md#concept_9BE4F7D9CDAE4445B9AF3212BC7E61F2)
* [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)

## ClearVars {#section_597C411E7EDB42BC9A6A0508C9D57147}

可以使用新的 `clearVars` 方法从实例对象中清除以下值：

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

例如：

```js
s.clearVars()
```

## 优点 {#section_091E5A28E89E438E8A54A95F55165743}

* 比 H.25 代码快 3 至 7 倍。
* 未压缩时仅为 21k，压缩后为 8k（H.25 代码未压缩时为 33k，压缩后为 13k）。
* 本地支持多个常用插件 ()。
* 小巧、快速的特点非常适合用于移动网站，而强健的功能又适合在完整的桌面网站上使用，从而使您可以在所有 Web 环境中使用单个库。

