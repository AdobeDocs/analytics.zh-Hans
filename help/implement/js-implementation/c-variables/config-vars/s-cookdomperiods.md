---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.cookieDomainPeriods

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. 某些插件还会使用此变量来确定要设置插件 Cookie 的正确域。

The default value for *`cookieDomainPeriods`* is "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. For example, using the domain ,  should be "2". `www.mysite.com`*`cookieDomainPeriods`* For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting *`cookieDomainPeriods`* to "2" on the domain `www.mysite.co.jp`, the `s_cc` and `s_sq` cookies are created on the domain `co.jp`. 由于 `co.jp` 是无效的域，所有浏览器都会拒绝这些 Cookie。因而，访客点击图数据会丢失，并且[!UICONTROL “访客资料”]&gt;[!UICONTROL “技术”]&gt;[!UICONTROL “Cookie”]报表指示几乎所有访客都拒绝这些 Cookie。

如果&#x200B;*`cookieDomainPeriods`*&#x200B;被设置为 "3"，而域仅包含两个句点，则 JavaScript 文件会尝试在网站的子域上设置 Cookie。例如，如果在域 *`cookieDomainPeriods`* 上设置为“3”，则 `www2.mysite.com`会在域 `s_cc` 上创建和 `s_sq` cookies `www2.mysite.com`。 When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example, `store.toys.mysite.com` would still have *`cookieDomainPeriods`* set to "2". 此变量定义可以在根域 [!DNL mysite.com] 上正确设置 Cookie。Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

另请参 [阅s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | CDP | 影响多个报表，因为它控制访客 ID 的存储和处理方式。 | "2" |

>[!NOTE]
>
>某些云计算服务被视为顶级域，不允许写入Cookie。 (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) 如果您在这些服务上进行实施，则可能会受到 Analytics 隐私设置的影响，因为如果您还没有设置自己的域（例如，如果您正在测试您的实施），那么该设置会删除已阻止所有 Cookie 的用户。在这种情况下，如果系统已确定其 Cookie 已禁用，则不可用或不可访问的点击会被禁止，因此会从报表中排除。

## 示例

手动设置变量：

```js
s.cookieDomainPeriods = "3";
```

在核心 JavaScript 文件同时包含以下两种情况时，动态设置变量的若干示例：

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

## 缺陷、问题和提示

* 如果您发现访客点击图数据缺失，或[!UICONTROL “流量”]&gt;[!UICONTROL “技术”]&gt;[!UICONTROL “Cookie”]报表显示有相当大比例的访客拒绝 Cookie，请检查&#x200B;*`cookieDomainPeriods`*&#x200B;的值是否正确设置。

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. 在访客切换子域时，这可能会导致数据丢失。
* The 变量 *`cookieDomainPeriods`* 在设置访客ID cookie之前已弃 *`trackingServer`* 用的实施中使用。 虽然代码过时，但在这种情况下未正确定 *`cookieDomainPeriods`* 义，使您的实施面临数据丢失的风险。