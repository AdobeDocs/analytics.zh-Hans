---
title: fpcookieDomainPeriods
description: 帮助 AppMeasurement 了解当您的域的后缀中有句点时，应使用哪个域来存储 Cookie。
feature: Variables
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 86%

---

# fpCookieDomainPeriods

`fpCookieDomainPeriods` 变量会声明域后缀中含有额外的句点，从而可帮助 AppMeasurement 确定在何处设置 Analytics Cookie。此变量允许 AppMeasurement 处理域后缀中的额外句点，并在正确的位置设置 Cookie。它会继承 [`cookieDomainPeriods`](cookiedomainperiods.md) 的值，如果您使用第一方 Cookie 实施，最佳做法便是将此变量设置为该值。

* 对于 `example.com` 或 `www.example.com` 等域，无需设置此变量。如果需要，可将此变量设置为 `"2"`。
* 对于 `example.co.uk` 或 `www.example.co.jp` 等域，将此变量设置为 `"3"`。

>[!IMPORTANT]
>
>此变量不考虑子域。例如，不要在示例 URL `store.toys.example.com` 上设置 `fpCookieDomainPeriods`。默认情况下，AppMeasurement 允许将 Cookie 存储在 `example.com` 上，甚至存储在具有许多子域的 URL 上。

## 使用Web SDK的第一方域名段

在没有此变量的情况下，Web SDK可以确定正确的Cookie存储域。

## 使用Adobe Analytics扩展的第一方域名段

“第一方域名段”是在配置 Adobe Analytics 扩展时位于 [!UICONTROL Cookie] 折叠面板下的一个字段。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;]**配置**[!UICONTROL &#x200B;按钮。
4. 展开 [!UICONTROL Cookie] 折叠面板，这会显示[!UICONTROL 第一方域名段]字段。

仅当域的后缀中包含句点时，才会将此字段设置为 `3`。否则，可将此字段留空。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.fpCookieDomainPeriods

`fpCookieDomainPeriods` 变量是一个字符串，一般而言，仅对于后缀中包含句点的域，才会将该变量设置为 `"3"`。其默认值是 `"2"`，该值适用于大多数域。

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
