---
title: cookieDomainPeriods
description: 帮助 AppMeasurement 了解当您的域的后缀中有句点时，应使用哪个域来存储 Cookie。
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# cookieDomainPeriods

AppMeasurement 可通过检查域和域的后缀确定其 Cookie 位置。对于像 `example.com` 这样的域，AppMeasurement 会将 Cookie 设置到正确位置中。但是，对于其他域（如 `example.co.uk`），AppMeasurement 可能会错误地将 Cookie 设置到 `co.uk` 上。大多数浏览器会拒绝在此无效域上设置的 Cookie，而这会导致无法正确访客识别。

`cookieDomainPeriods` 变量会声明域后缀中含有额外的句点，从而可帮助 AppMeasurement 确定在何处设置 Analytics Cookie。此变量允许 AppMeasurement 处理域后缀中的额外句点，并在正确的位置设置 Cookie。

* 对于 `example.com` 或 `www.example.com` 等域，无需设置此变量。如果需要，可将此变量设置为 `"2"`。
* 对于 `example.co.uk` 或 `www.example.co.jp` 等域，将此变量设置为 `"3"`。

>[!IMPORTANT] 此变量不考虑子域。例如，不要在示例 URL `store.toys.example.com` 上设置 `cookieDomainPeriods`。默认情况下，AppMeasurement 允许将 Cookie 存储在 `example.com` 上，甚至存储在具有许多子域的 URL 上。

## Adobe Experience Platform Launch 中的“域名段”

“域名段”是在配置 Adobe Analytics 扩展时显示在 [!UICONTROL Cookie] 折叠面板中的一个字段。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]按钮。
4. 展开 [!UICONTROL Cookie] 折叠面板，这会显示[!UICONTROL 域名段]字段。

仅当域的后缀中包含句点时，才会将此字段设置为 `3`。否则，可将此字段留空。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.cookieDomainPeriods

`cookieDomainPeriods` 变量是一个字符串，一般而言，仅对于后缀中包含句点的域，才会将该变量设置为 `"3"`。其默认值是 `"2"`，该值适用于大多数域。

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
