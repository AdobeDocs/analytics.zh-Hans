---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.linkExternalFilters

如果您的网站包含许多指向外部网站的链接，并且您不希望跟踪所有退出链接，则可使用 报告退出链接的特定子集。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | “路径”&gt;“登录和退出”&gt;“退出链接” | "" |

The *`linkExternalFilters`* variable is an optional variable used in conjunction with *`linkInternalFilters`* to determine whether a link is an exit link. 退出链接定义为将访客带离您网站的任何链接。无论退出链接的目标窗口是弹出窗口还是现有窗口，都不会影响该链接在退出链接报表中的显示。仅在 *`trackExternalLinks`* 设置为“True”时，才会跟踪退出链接。*`linkExternalFilters`* 和 *`linkInternalFilters`* 中的过滤器不区分大小写。

> [!NOTE]如果您不想使用 *`linkExternalFilters`*，请删除它或将其设置为 ""。

默认情况下，*`linkExternalFilters`* 和 *`linkInternalFilters`* 中的过滤器列表适用于任何链接的域和路径。如果 *`linkLeaveQueryString`* 设置为“true”，则这些过滤器应用于整个 URL（域名、路径和查询字符串）。这些过滤器始终应用于 URL 的绝对路径，即使将相对路径用作 href 值也不例外。

大部分公司发现通过 *`linkInternalFilters`* 足可控制退出链接，他们不需要 *`linkExternalFilters`*. 使用 *`linkExternalFilters`* 只会减少将退出链接视为外部链接的可能性。如果 *`linkExternalFilters`* 具有一个值，则仅当链接与 *`linkInternalFilters`* 不匹配，与 *`linkExternalFilters`* 匹配时，才会将其视为外部链接。

以下示例说明此变量的使用方法。在此示例中，页面的 URL 是 `https://www.mysite.com/index.html`。

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
...
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

## 语法和可能值

*`linkExternalFilters`* 变量是以逗号隔开的 ASCII 字符列表。不允许有空格。

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

URL 的任何部分均可包含于 *`linkExternalFilters`* 中，并以逗号分隔。

## 示例

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

## 配置设置

无

## 缺陷、问题和提示

* 使用 *`linkExternalFilters`* 可减少网站上视为外部链接的链接。不要使用此变量代替 *`linkInternalFilters`* 将内部链接强制变成退出链接。

* 如果将 *`linkExternalFilters`* 应用于链接的查询字符串，请确保将 *`linkLeaveQueryString`* 设置为“true”。请参阅 [linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)，然后将其设置为 `"true"`。

* 要禁用退出链接跟踪，请将 *`trackExternalLinks`* 设置为 `"false"`。
