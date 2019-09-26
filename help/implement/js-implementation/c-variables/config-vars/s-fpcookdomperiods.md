---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.fpCookieDomainPeriods

 变量适用于由 JavaScript 设置的内置第一方 Cookie（s_sq、s_cc、插件），即使您的实施使用的是第三方 2o7.net 或 omtrdc.net 域。

The *`fpCookieDomainPeriods`* variable should never be dynamically set . If you use , it is good practice to specify a value for  as well. *`cookieDomainPeriods`**`fpCookieDomainPeriods`**`fpCookieDomainPeriods`* 继承该 *`cookieDomainPeriods`* 值。 Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

名称“ *`fpCookieDomainPeriods`*”指句点数(“”)“www”开头的域中句点 (.) 的数量。For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

The [!DNL AppMeasurement] for JavaScript file uses the *`fpCookieDomainPeriods`* variable to determine the domain with which to set first-party cookies other than the [!UICONTROL visitor ID] (s_vi) cookie. There are at least two cookies affected by this variable, including `s_sq` and `s_cc` (used for visitor click map and cookie checking respectively). [!UICONTROL getValOnce] 等插件使用的 Cookie 也会受到影响。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | cookieDomainPeriods |

## 设置 Cookie 域变量的示例代码

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

## 语法和可能值

The *`cookieDomainPeriods`*&#x200B;变量应为字符串，如下所示。

```js
s.fpCookieDomainPeriods="3"
```

## 示例

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

## 配置设置

无