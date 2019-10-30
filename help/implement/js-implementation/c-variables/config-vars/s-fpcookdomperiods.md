---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.fpCookieDomainPeriods

 变量适用于由 JavaScript 设置的内置第一方 Cookie（s_sq、s_cc、插件），即使您的实施使用的是第三方 2o7.net 或 omtrdc.net 域。

*`fpCookieDomainPeriods`* 变量绝不应进行动态设置。如果您使用 *`cookieDomainPeriods`*，则最好也为 *`fpCookieDomainPeriods`* 指定一个值。*`fpCookieDomainPeriods`* 会继承 *`cookieDomainPeriods`* 值。请注意，*`fpCookieDomainPeriods`* 不会影响设置有访客 ID Cookie 的域，即使您的实施将此视为第一方 Cookie。

名称“*`fpCookieDomainPeriods`*”是指句点（“.”）的数量。“www”开头的域中句点 (.) 的数量。例如，`www.mysite.com` 包含两个句点，而 `www.mysite.co.jp` 包含三个句点。描述此变量的另一种方式是网站主域的节数（`mysite.com` 为两节，而 `mysite.co.jp` 为三节）。

[!DNL AppMeasurement] for JavaScript 文件使用变量 *`fpCookieDomainPeriods`* 确定用来设置除[!UICONTROL 访客 ID] (s_vi) Cookie 以外的第一方 Cookie 的域。There are at least two cookies affected by this variable, including `s_sq` and `s_cc` (used for visitor click map and cookie checking respectively). [!UICONTROL getValOnce] 等插件使用的 Cookie 也会受到影响。

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

*`cookieDomainPeriods`* 变量应为字符串，如下所示。

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