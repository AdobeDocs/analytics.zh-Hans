---
title: 比较实施方法
description: 了解每种用于将数据发送到 Adobe Analytics 的方法的优点。
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
source-git-commit: d64f6687dd6e6f688d332926e6d90fa699cac968
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 59%

---

# 比较实施方法

了解每种实施 Adobe Analytics 的方法的比较情况。您可以使用这些表来帮助您的组织确定将数据发送到Adobe的最理想方式。 单击每一列以了解更多具体信息。

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Adobe Analytics 扩展](/help/implement/launch/overview.md) | [Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Web SDK 扩展](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| 实施要求 | 在每个页面上参考 `AppMeasurement.js`，定义变量，使用 `s.t()` 发送数据 至Adobe Analytics | 在每个页面上加载引用标记，使用数据收集UI定义变量并将数据发送到Adobe Analytics | 引用 `Alloy.js` 在每个页面上，使用 `alloy("sendEvent",{})` 合成XDM对象并使用Edge Network将所需数据发送到Adobe Analytics | 引用标记加载器在每个页面上，使用数据收集UI构建XDM对象，并使用Edge Network将所需数据发送到Adobe Analytics |
| 数据目标 | 直接发送到 Adobe Analytics | 直接发送到 Adobe Analytics | 发送到 Adobe Experience Platform Edge，后者会将数据转发到 Adobe Analytics | 发送到 Adobe Experience Platform Edge，后者会将数据转发到 Adobe Analytics |
| 难以进行实施调整 | 每次实施更改都需要访问网站代码 | 更改网站代码一次以安装加载器标记；可在数据收集 UI 中进行所有进一步的实施更新 | 每次实施更改都需要访问网站代码 | 更改网站代码一次以安装加载器标记；可在数据收集 UI 中进行所有进一步的实施更新 |
| 如何处理 A4T | A4T 调用包含在已发送到 Adobe 的点击中 | A4T 调用包含在已发送到 Adobe 的点击中 | A4T 调用作为单独的点击发送 | A4T 调用作为单独的点击发送 |
| 上下文数据 | 使用 `s.contextData`。 | 在自定义代码块中使用 `s.contextData` | 作为 `a.x.*` 上下文数据变量自动发送所有未映射的字段。 | 作为 `a.x.*` 上下文数据变量自动发送所有未映射的字段。 |

{style="table-layout:auto"}

## 移动设备及其他

>[!CAUTION]
>
>对版本 4 Mobile SDK 的支持于 2021 年 8 月 31 日终止。 请参阅 [AdobeMobile Services生命周期终止常见问题解答](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html) 以了解更多信息。


| | [Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md) | [服务器API](/help/implement/aep-edge/server-api/overview.md) |
| --- | --- | --- |
| 实施要求 | 在应用程序中引用标记加载器，然后使用数据收集UI中的直接API调用或规则来构建XDM对象，并使用Edge Network将所需数据发送到Adobe Analytics | 使用Edge Network服务器API构建XDM对象，并使用Edge Network将所需数据发送到Adobe Analytics |
| 数据目标 | 发送到 Adobe Experience Platform Edge，后者会将数据转发到 Adobe Analytics | 发送到 Adobe Experience Platform Edge，后者会将数据转发到 Adobe Analytics |
| 难以进行实施调整 | 更改从中进行直接API调用的应用程序代码，或更改数据收集UI | 每次实施更改都需要访问应用程序代码 |
| 如何处理 A4T | A4T 调用作为单独的点击发送 | A4T 调用作为单独的点击发送 |
| 上下文数据 | 作为 `a.x.*` 上下文数据变量自动发送所有未映射的字段。 | 所有未映射的字段都会自动发送为 `a.x.*` 上下文数据变量 |

{style="table-layout:auto"}
