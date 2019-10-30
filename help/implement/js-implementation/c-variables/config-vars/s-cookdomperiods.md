---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.cookieDomainPeriods

该变量通过确定页面 URL 的域名中的句点数来确定设置 [!DNL Analytics] Cookie（`s_cc` 和 `s_sq`）的域。某些插件还会使用此变量来确定要设置插件 Cookie 的正确域。

*`cookieDomainPeriods`* 的默认值为“2”。如果忽略 *`cookieDomainPeriods`*，则使用此值。例如，使用域 `www.mysite.com` 时，*`cookieDomainPeriods`* 应为“2”。对于 `www.mysite.co.jp`，*`cookieDomainPeriods`* 应为“3”。

如果 *`cookieDomainPeriods`* 被设置为“2”，而域包含三个句点，则 JavaScript 文件会尝试在域后缀上设置 Cookie。

例如，如果在域 `www.mysite.co.jp` 上将 *`cookieDomainPeriods`* 设置为“2”，则会在域 `co.jp` 上创建 `s_cc` 和 `s_sq` Cookie。由于 `co.jp` 是无效的域，所有浏览器都会拒绝这些 Cookie。因而，访客点击图数据会丢失，并且[!UICONTROL “访客资料”]&gt;[!UICONTROL “技术”]&gt;[!UICONTROL “Cookie”]报表指示几乎所有访客都拒绝这些 Cookie。

如果&#x200B;*`cookieDomainPeriods`*&#x200B;被设置为 "3"，而域仅包含两个句点，则 JavaScript 文件会尝试在网站的子域上设置 Cookie。例如，如果在域 `www2.mysite.com` 上将 *`cookieDomainPeriods`* 设置为“3”，则会在域 `www2.mysite.com` 上创建 `s_cc` 和 `s_sq` Cookie。在访客转到网站的子域（如 `www4.mysite.com`）时，对 `www2.mysite.com` 设置的所有 Cookie 都将无法读取。

> [!NOTE] 不要将其他子域作为的一部分包含 *`cookieDomainPeriods`*。 例如，`store.toys.mysite.com` 仍会将 *`cookieDomainPeriods`* 设置为“2”。此变量定义可以在根域 [!DNL mysite.com] 上正确设置 Cookie。将 *`cookieDomainPeriods`* 设置为“3”会在域 [!DNL toys.mysite.com] 上设置 Cookie，其结果与上一个示例相同。

另请参见 [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | CDP | 影响多个报表，因为它控制访客 ID 的存储和处理方式。 | "2" |

> [!NOTE]有些云计算服务被视为顶级域，不允许写入 Cookie。（例如，`compute.amazonaws.com`、`*.herokuapp.com`、`*.googlecode.com` 等等。）如果您在这些服务上进行实施，则可能会受到 Analytics 隐私设置的影响，因为如果您还没有设置自己的域（例如，如果您正在测试您的实施），那么该设置会删除已阻止所有 Cookie 的用户。在这种情况下，如果系统已确定其 Cookie 已禁用，则不可用或不可访问的点击会被禁止，因此会从报表中排除。

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

* 如果您发现访客点击图数据缺失，或[!UICONTROL 流量] &gt; [!UICONTROL 技术] &gt; [!UICONTROL Cookie] 报表显示有相当大比例的访客拒绝 Cookie，请检查 *`cookieDomainPeriods`* 的值是否正确。

* 如果 *`cookieDomainPeriods`* 大于该域的节数，则将在全域设置 Cookie。在访客切换子域时，这可能会导致数据丢失。
* The *`cookieDomainPeriods`* 变量在已停用实施的 *`trackingServer`* 之前使用，以设置访客 ID Cookie。尽管该变量仅出现在过时的代码中，但在这种情况下，如果未能正确定义 *`cookieDomainPeriods`*，仍会导致您的实施丢失数据。