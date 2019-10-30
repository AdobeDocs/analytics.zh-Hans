---
description: 返回指定查询字符串参数的值（如果在当前页面 URL 中或在提供的字符串中找到）。
keywords: Analytics 实施
seo-description: 返回指定查询字符串参数的值（如果在当前页面 URL 中或在提供的字符串中找到）。
seo-title: Util.getQueryParam
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.getQueryParam
topic: 开发人员和实施
uuid: 1fecd148-3e52-46f2-a73f-003563f7a62c
translation-type: ht
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Util.getQueryParam

返回指定查询字符串参数的值（如果在当前页面 URL 中或在提供的字符串中找到）。

由于重要数据（例如促销活动跟踪代码、内部搜索关键词等）可在页面上的查询字符串中找到，getQueryParam 可帮助将这些数据捕获到 Analytics 变量中。

此实用工具可替换[getQueryParam](../../implement/js-implementation/plugins/getqueryparam.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) 插件。

**语法：**

```
s.Util.getQueryParam(key, [url], [delim])
```

>[!NOTE]
>
>此实用工具的语法不同于插件的语法。

**参数：**

| 参数 | 描述 |
|---|---|
| key | （必需）您要获取的查询字符串参数的名称。该参数区分大小写。 |
| url | （可选）默认 URL 为 `s.pageURL` 或 `window.location`。指定此参数的值会使用指定的 URL 覆盖检索查询参数时所在的 URL。 |
| delim | （可选）URL 中的参数分隔符。默认分隔符为“&amp;”。它允许您指定备用的查询字符串分隔符，如“;”。 |

**返回结果：**

如果未提供密钥，或者 URL 选项不存在，抑或者是在 URL 中找不到密钥，则函数将返回空字符串“”。如果在 URL 中找到片段分隔符 #，则不会考虑片段分隔符之后的所有内容。如果密钥存在并且被分配给某个值，则会对该值进行 URL 解码并将其返回。

**示例：**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

