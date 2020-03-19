---
title: cookieDomainPeriods
description: 帮助AppMeasurement了解如果您的域在其后缀中有句点，应存储cookie的域。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# fpCookieDomainPeriods

该变 `fpCookieDomainPeriods` 量通过调用域后缀中有额外的句点，帮助AppMeasurement确定Analytics cookies的设置位置。 此变量允许AppMeasurement适应域后缀中的额外句点，并在正确的位置设置cookie。 它继承了的 [`cookieDomainPeriods`](cookiedomainperiods.md)值，但如果您使用第一方Cookie实施，它仍然是设置的最佳实践。

* 对于或 `example.com` 等 `www.example.com`域，无需设置此变量。 如果需要，可将此变量设置为 `"2"`。
* 对于或等 `example.co.uk` 域， `www.example.co.jp`将此变量设置为 `"3"`。

> [!IMPORTANT] 请勿将子域考虑在内。 例如，不要在示 `fpCookieDomainPeriods` 例URL上设置 `store.toys.example.com`。 AppMeasurement默认识别Cookie应存储在上，即使 `example.com`在具有许多子域的URL上也是如此。

## Adobe Experience Platform Launch中的第一方域句点

第一方域句点是配置Adobe Analytics扩展时 [!UICONTROL Cookies] accordion下的字段。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到选项卡， [!UICONTROL Extensions] 然后单击“Adobe Analytics” [!UICONTROL Configure] 下的按钮。
4. 展开可 [!UICONTROL Cookies] 折叠面板，以显示 [!UICONTROL First-party Domain Periods] 字段。

将此字段设 `3` 置为仅在后缀中包含句点的域上。 否则，此字段可留空。

## s.fpCookieDomainPeriods in AppMeasurement and Launch自定义代码编辑器

变 `fpCookieDomainPeriods` 量是一个字符串，通常设置为 `"3"`，仅在后缀中包含句点的域上。 其默认值是， `"2"`它适合大多数域。

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
