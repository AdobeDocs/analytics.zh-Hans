---
title: cookieDomain
description: （已停用）帮助确定要在其中设置Cookie的域。
feature: Appmeasurement Implementation
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 77%

---

# cookieDomain

>[!IMPORTANT]
>此变量已停用。请改用 [`trackingServer`](trackingserver.md)。

`cookieDomain` 变量可确定 AppMeasurement 将在哪个域中设置 Cookie。您可以使用此变量而不是 [`cookieDomainPeriods`](cookiedomainperiods.md) 变量来明确设置 Cookie 域。

仅当&#x200B;**同时**&#x200B;满足以下两个条件时，才需要使用此变量：

* 您的实施使用第一方 Cookie。对于使用含有 `sc.adobedc.net` 的 [`trackingServer`](trackingserver.md) 值的实施，不需要使用此变量。
* 域的后缀中有句点。例如，`example.co.uk` 可以使用 `cookieDomain` 变量明确声明 Cookie 域是 `example.co.uk` 而不是 `co.uk`。

只有少量实施需要使用 `cookieDomain` 变量，虽然如此，可以改用替代变量，如 [`cookieDomainPeriods`](cookiedomainperiods.md)。

## 使用Web SDK的Cookie域

如果没有此变量，Web SDK可以确定正确的Cookie存储域。

## 使用Adobe Analytics扩展的Cookie域

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.cookieDomain

`cookieDomain` 变量是一个字符串，设置为要用于存储 Cookie 的域。

```js
s.cookieDomain = "stats.example.com";
```
