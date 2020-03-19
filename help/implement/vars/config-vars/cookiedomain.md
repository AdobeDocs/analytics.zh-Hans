---
title: cookieDomain
description: cookieDomain变量可帮助确定要设置cookie的域。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# cookieDomain

> [!IMPORTANT] 此变量已停用。 请改 [`trackingServer`](trackingserver.md) 用。

该变 `cookieDomain` 量确定AppMeasurement设置cookie的域。 您可以使用此变量显式设置cookie域，而不是使用变 [`cookieDomainPeriods`](cookiedomainperiods.md) 量。

仅当满足以下两个条件时 **才需** 要使用此变量：

* 如果您的实施使用第一方Cookie。 在使用包含值的实现中不需要 [`trackingServer`](trackingserver.md) 此变量 `sc.omtrdc.net`。
* 如果域的后缀中有句点。 例如，可 `example.co.uk` 以使用变量 `cookieDomain` 显式声明cookie域是 `example.co.uk` 否是 `co.uk`。

只有少量实现可用于变量， `cookieDomain` 甚至可以改用替代变 [`cookieDomainPeriods`](cookiedomainperiods.md) 量（如）。

## Adobe Experience Platform Launch中的Cookie域

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement中的s.cookieDomain和启动自定义代码编辑器

该 `cookieDomain` 变量是一个字符串，并设置为要在其上存储cookie的域。

```js
s.cookieDomain = "stats.example.com";
```
