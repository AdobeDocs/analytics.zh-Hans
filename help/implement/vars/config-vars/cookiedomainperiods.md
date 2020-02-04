---
title: cookieDomainPeriods
description: 帮助AppMeasurement了解如果您的域在其后缀中有句点，应存储cookie的域。
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# cookieDomainPeriods

AppMeasurement通过查看域和域后缀确定其Cookie位置。 对于像这样的 `example.com`域，AppMeasurement将cookies设置在正确的位置。 但是，对于其他域(如 `example.co.uk`AppMeasurement),AppMeasurement可能会错误地在上设置cookies `co.uk`。 大多数浏览器拒绝在此无效域上设置的Cookie，导致访客识别问题。

该变 `cookieDomainPeriods` 量通过调用域后缀中有额外的句点，帮助AppMeasurement确定Analytics cookies的设置位置。 此变量允许AppMeasurement适应域后缀中的额外句点，并在正确的位置设置cookie。

* 对于或 `example.com` 等 `www.example.com`域，无需设置此变量。 如果需要，可将此变量设置为 `"2"`。
* 对于或等 `example.co.uk` 域， `www.example.co.jp`将此变量设置为 `"3"`。

> [!IMPORTANT] 请勿将子域考虑在内。 例如，不要在示 `cookieDomainPeriods` 例URL上设置 `store.toys.example.com`。 AppMeasurement默认识别Cookie应存储在上 `example.com`，即使在具有许多子域的URL上也是如此。

## Adobe Experience Platform Launch中的域句点

域句点是配置Adobe Analytics扩展时 [!UICONTROL Cookies] accordion下的字段。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开 [!UICONTROL Cookies折叠] ，该面板显示“ [!UICONTROL 域句点] ”字段。

将此字段设 `3` 置为仅在后缀中包含句点的域上。 否则，此字段可留空。

## AppMeasurement和启动自定义代码编辑器中的s.cookieDomainPeriods

变 `cookieDomainPeriods` 量是一个字符串，通常设置为 `"3"`，仅在后缀中包含句点的域上。 其默认值是， `"2"`它适合大多数域。

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
