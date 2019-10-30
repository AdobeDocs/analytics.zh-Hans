---
description: 指定禁用链接，并自定义链接的标注方式。访问您网站的访客可以通过访问数据收集域的退出页面，选择不在Adobe的分析产品中跟踪其活动。
keywords: Analytics 实施
seo-description: 指定禁用链接，并自定义链接的标注方式。访问您网站的访客可以通过访问数据收集域的退出页面，选择不在Adobe的分析产品中跟踪其活动。
seo-title: 添加选择退订链接
solution: Analytics
subtopic: 故障诊断
title: 添加选择退订链接
topic: 开发人员和实施
uuid: c12092be-3be7-4621-b838-d6b78d074f84
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 添加选择退订链接

指定禁用链接，并自定义链接的标注方式。访问您网站的访客可以通过访问数据收集域的退出页面，选择不在Adobe的分析产品中跟踪其活动。

如果用户选择不进行跟踪，并且已设置禁用 Cookie，您的 JavaScript 文件将继续向 Adobe 服务器发送数据，但不会处理或报告该数据。

URL 结构的 collection_domain 部分即为您的 JavaScript 文件中使用的 trackingServer。用于Adobe Analytics实施的集合域可在Adobe Analytics表第一行的DigitalPulse调试器中查看，该表标记为“第一方Cookie”或“第三方Cookie”，具体取决于您的实施。 您的网站的收集域可能包含 2o7.net、omtrdc.net 或您的网站域名，例如 metrics.example.com。

访客单击禁用页面上的链接即可完成禁用，从而在其浏览器内完成 Cookie 的设置。对适用的跟踪域设置 `omniture_optout` Cookie 以后，Adobe Analytics 将不会报告用户活动。您可以将自己的链接提供给禁用 Cookie，也可以根据以下步骤来设置禁用 Cookie。

Adobe 为所有实施类型均提供禁用选项。您需要对自己的隐私政策负责，并且应遵守签署的条款。请注意，禁用页面的链接会根据实施类型而发生变化，如此处所述。

如果您在 Adobe 所拥有的域名（即 207.net 或 omtrdc.net）上设置了 Cookie 的情况下实施 Adobe Analytics 产品和服务，那么可以将您的网站访客引导至 [Adobe 隐私中心](https://www.adobe.com/privacy/opt-out.html)提供的禁用机制，该机制适用于所有使用 Adobe Analytics 产品和服务的 Adobe Cookie 的站点。Adobe 选择退出机制的直接链接为 `https:// *collection_domain* /optout.html`。

More information about Adobe Analytics privacy practices can be found at [https://www.adobe.com/privacy/advertising-services.html](https://www.adobe.com/privacy/advertising-services.html).

* [禁用页面 URL 结构](../../../implement/js-implementation/data-collection/opt-out-link.md#section_E0462428D2E440E7863E24D2F6DBF748)
* [示例禁用 URL](../../../implement/js-implementation/data-collection/opt-out-link.md#section_258DE5226AA0483CA790D2C9C5318B2E)
* [标注您的禁用 URL](../../../implement/js-implementation/data-collection/opt-out-link.md#section_674AB62E810B414AB8F1615C0E3061F8)

## 禁用页面 URL 结构 {#section_E0462428D2E440E7863E24D2F6DBF748}

您的禁用页面的 URL 如下：

```
https://collection_domain/optout.html[?optional_parameters]
```

`optional_parameters` 包括：

`locale=[code]`：提供选择退出页面的翻译版本。支持以下区域设置：

* en_US（默认）
* de_DE
* es_ES
* fr_FR
* jp_JP
* ko_KR
* zh_CN
* zh_TW

`popup=1`:将页面视为弹出窗口，并提供“关闭窗口”按钮。

## 示例禁用 URL {#section_258DE5226AA0483CA790D2C9C5318B2E}

一个全屏英文网页，并在其中包含一个链接，单击这个链接可阻止在 metrics.example.com 上对访客进行跟踪：

```
https://metrics.example.com/optout.html
```

一个全屏法语网页，并在其中包含一个链接，单击这个链接可阻止在 example.d3.sc.omtrdc.net 上对访客进行跟踪：

```
https://example.d3.sc.omtrdc.net/optout.html?locale=fr_FR
```

一个全屏德语网页，并在其中包含一个链接，单击这个链接可阻止在 example.112.2o7.net 上对访客进行跟踪：

```
https://example.112.2o7.net/optout.html?popup=1&locale=de_DE
```

## 标注您的禁用 URL {#section_674AB62E810B414AB8F1615C0E3061F8}

您可以在您网站上的如下某个位置提供一个链接：

```
 <a href=" https://stats.adobe.com/optout.html?optout=1&confirm_change=1">
Click Here to Opt Out! </a>
```

其中，将 *`stats.adobe.com`* 替换为 *`s.trackingServer`* 变量所设置的内容。

此外，如果您想提供选择加入链接，请使用相同的 URL，但需将其中的 `?optout=1` 替换为 `?optin=1`，并保留 `confirm_change=1`。
