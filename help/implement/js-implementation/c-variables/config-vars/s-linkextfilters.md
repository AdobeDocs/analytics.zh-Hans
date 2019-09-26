---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkExternalFilters

如果您的网站包含许多指向外部网站的链接，并且您不希望跟踪所有退出链接，则可使用 报告退出链接的特定子集。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | “路径”&gt;“登录和退出”&gt;“退出链接” | "" |

The 变 *`linkExternalFilters`* 量是与一起使用的可选变量，用 *`linkInternalFilters`* 于确定链接是否为退出链接。 退出链接定义为将访客带离您网站的任何链接。无论退出链接的目标窗口是弹出窗口还是现有窗口，都不会影响该链接在退出链接报表中的显示。仅在 *`trackExternalLinks`* is set to 'true.' The filters in  and  are case insensitive.*`linkExternalFilters`**`linkInternalFilters`*

>[!NOTE]
>
>If you don't want to use *`linkExternalFilters`*, delete it or set it to "".

过滤器列在中， *`linkExternalFilters`* 并默 *`linkInternalFilters`* 认情况下应用于任何链接的域和路径。 If  is set to 'true,' the filters apply to the entire URL (domain, path, and query string). *`linkLeaveQueryString`*&#x200B;这些过滤器始终应用于 URL 的绝对路径，即使将相对路径用作 href 值也不例外。

大部分公司发现通过 *`linkInternalFilters`* 足可控制退出链接，他们不需要 *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

以下示例说明此变量的使用方法。In this example, the URL of the page is `https://www.mysite.com/index.html`.

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

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. 不允许有空格。

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

URL 的任何部分均可包含于 *`linkExternalFilters`*, separated by commas.

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

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. 请勿使用此变量来强制 *`linkInternalFilters`* 内部链接成为退出链接。

* 如 *`linkExternalFilters`* 果应将其应用于链接的查询字符串，请确 *`linkLeaveQueryString`* 保设置为“true”。 See [linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.
