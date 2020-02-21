---
title: writeSecureCookies
description: 允许AppMeasurement使用“安全”属性设置Cookie。
translation-type: tm+mt
source-git-commit: 7644f70dfec5380fc75be14605f1c4f74ee4a8c3

---


# writeSecureCookies

该变 `writeSecureCookies` 量允许AppMeasurement设置 [Analytics的Secure cookie](https://en.wikipedia.org/wiki/Secure_cookie) 。 此设置适用于由AppMeasurement设置的访客ID Cookie和您使用该方法设置的 `Util.CookieWrite` Cookie。 它需要AppMeasurement 2.18.0或更高版本。

> [!IMPORTANT] 如果启用该变 `writeSecureCookies` 量，请确保站点上的所有内容都通过HTTPS安全地提供。 如果启用了此变量，并且您的页面上有不安全的内容，则AppMeasurement将不起作用。

## 在Adobe Experience Platform Launch中编写安全Cookie

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement中的s.writeSecureCookies和启动自定义代码编辑器

该变 `s.writeSecureCookies` 量是一个布尔值，它确定AppMeasurement在创建Cookie时是否设置Secure属性。 Its default value is `false`. 将此变量设置为 `true` 站点上的所有内容都是安全的，并且您希望AppMeasurement设置的cookie具有“安全”属性。

```js
s.writeSecureCookies = true;
```
