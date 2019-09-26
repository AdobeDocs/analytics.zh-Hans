---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieDomain

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

通常， `s.cookieDomainPeriods` 用于从生成 `s.cookieDomain` 内容 `window.location.hostname`。 您可以显 `s.cookieDomainPeriods`式设置要在实 `s.cookieDomain` 施中使用的内容，而不是使用。 例如，您可以使用以下代码在完全限定的页面名称处设置 Cookie：

`s.cookieDomain = window.location.hostname;`
