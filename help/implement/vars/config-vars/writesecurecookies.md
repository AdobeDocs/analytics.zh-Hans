---
title: writeSecureCookies
description: 允许 AppMeasurement 使用“安全”属性设置 Cookie。
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# writeSecureCookies

`writeSecureCookies` 变量允许 AppMeasurement 为 Analytics 设置[安全 Cookie](https://en.wikipedia.org/wiki/Secure_cookie)。此设置适用于由 AppMeasurement 设置的访客 ID Cookie，以及您使用 `Util.CookieWrite()` 方法设置的 Cookie。它需要 AppMeasurement 2.18.0 或更高版本。

>[!IMPORTANT] 如果启用 `writeSecureCookies` 变量，请确保网站上的所有内容都通过 HTTPS 协议来安全地提供。如果启用了此变量，并且您的页面上有不安全的内容，则 AppMeasurement 将不起作用。

## 在 Adobe Experience Platform Launch 中编写安全 Cookie

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.writeSecureCookies

`s.writeSecureCookies` 变量是一个布尔值，用于确定 AppMeasurement 在创建 Cookie 时是否为 Cookie 设置了安全属性。其默认值为 `false`。如果网站上的所有内容都安全，并且您希望 AppMeasurement 设置的 Cookie 具有“安全”属性，请将此变量设置为 `true`。

```js
s.writeSecureCookies = true;
```
