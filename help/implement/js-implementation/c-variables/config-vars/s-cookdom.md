---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieDomain

该变量确定设置了 [!DNL Analytics] Cookie（`s_cc` 和 `s_sq`）的域。

通常情况下，`s.cookieDomainPeriods` 用于从 `window.location.hostname` 中生成 `s.cookieDomain`。您可以明确地将 `s.cookieDomain` 设置为要在实施中使用的变量，而不是使用 `s.cookieDomainPeriods`。例如，您可以使用以下代码在完全限定的页面名称处设置 Cookie：

`s.cookieDomain = window.location.hostname;`
