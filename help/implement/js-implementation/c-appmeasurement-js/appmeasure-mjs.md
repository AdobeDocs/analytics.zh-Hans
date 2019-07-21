---
description: AppMeasurement for JavaScript 是一个新库，所提供的核心功能与 s_code.js 相同，但其设计更轻便，速度更快，非常适合在移动和桌面网站上使用。
keywords: appasurement；Analytics实施；javascript；javascript的appasurement；初始化；检索appMeasurement实例；清晰的变量；clearvar；appasurement utilities；appasurement instance；appasurement优势
seo-description: AppMeasurement for JavaScript 是一个新库，所提供的核心功能与 s_code.js 相同，但其设计更轻便，速度更快，非常适合在移动和桌面网站上使用。
seo-title: 关于 AppMeasurement for JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: 关于 AppMeasurement for JavaScript
topic: 开发人员和实施
uuid: dc71ad7a-92bd-40cd-8fab-707f6f8472e2
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 关于 AppMeasurement for JavaScript

[!DNL AppMeasurement] for JavaScript 是一个新库，所提供的核心功能与 s_code.js 相同，但其设计更轻便，速度更快，非常适合在移动和桌面网站上使用。

## 迁移前的注意事项 {#section_B8E7B39E8469468883BA0B41234F21C4}

The following list contains changes you need to understand before switching to this new [!DNL AppMeasurement] version:

* 不再支持某些插件。See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).
* The library does not support dynamic account selection ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md), and [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)).

* The library and page code can be deployed inside the `<head>` tag.
* The Media and Integrate modules are supported using updated module code that is in the JavaScript [!DNL AppMeasurement] download package. 但不支持调查模块。
* 现有页面代码与新版本兼容。
* 该库提供了一些本地实用工具，用来获取查询参数、读取和写入 Cookie，以及执行高级链接跟踪。

## 常见问题解答 {#section_9BD41B08F7B54197B230937714B9357A}

See the [FAQ](../../../implement/faq.md#concept_9BBC230E01114318BE9C08724F2040D3) for information about performance, video tracking, mobile, and more.

## 初始化过程 {#section_F6D5680F6D134B6AB1F01C6235860635}

Call `s_gi()`, passing the report suite ID to initialize an [!DNL AppMeasurement] instance:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

When `s_gi` is called, if an [!DNL AppMeasurement] instance does not exist for the specified `s_account`, a new instance is created. 否则，会返回现有的实例。这有助于避免为同一帐户创建重复的对象。

## 检索 AppMeasurement 实例 {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

Throughout your code, call the global [s_gi() function](../../../implement/js-implementation/function-s-gi.md#concept_50EE6629F61A478BB67781408FBA04BD) to retrieve an existing [!DNL AppMeasurement] instance.

## 实用工具 {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] provides the following built-in utilities:

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

