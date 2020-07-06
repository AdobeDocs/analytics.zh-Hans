---
title: 使用硬编码图像请求实施
description: 使用 HTML 图像标记（硬编码图像请求）实施 Adobe Analytics。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 100%

---


# 使用硬编码图像请求实施

Adobe 提供的 AppMeasurement 库可编译页面上存在的变量，然后将其作为图像请求发送到 Adobe。您完全可以绕过 AppMeasurement 库，手动向 Adobe 发送图像请求。此方法要求您手动构建图像请求和查询字符串。

这种实施方法可在显示外部图像的任意平台上使用。此方法根本不依赖 JavaScript。

>[!NOTE]
>
> 虽然硬编码图像请求很容易设置，但却很难在较大的项目中调试、维护和扩展。在继续操作之前，请确保硬编码图像请求是最符合您需求的选择。

## 图像请求语法

以下是使用 HTML 的示例硬编码图像请求：

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` 指定协议。将图像请求中使用的协议与网站其他部分使用的协议进行匹配。
* `example.sc.omtrdc.net` 是 `trackingServer` 变量中包含的值。
* `/b/ss/` 包含在所有图像请求中。它是 Adobe 数据收集服务器上所存储图像的文件结构的一部分。
* `examplersid` 是要将数据发送到的报表包 ID。
* `/1/` 是点击源。请参阅导出用户指南中[数据列引用](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)下的 `hit_source`。控制 Cookie 和其他方法在识别访客时所采用的顺序。
* 查询字符串分隔符 (`?`) 之后的所有内容都是要包含到报表中的数据。有关可包含到图像请求中的完整参数列表，请参阅[数据收集查询参数](../validate/query-parameters.md)。

## 常见问题解答

了解使用硬编码图像请求时遇到的常见问题。

**查询字符串参数是否区分大小写？**

是的。请确保查询字符串参数完全匹配，否则将不会记录这些参数。例如，`pagename` 不是有效的查询字符串参数，而 `pageName` 才是有效的查询字符串参数。

**查询字符串中是否可以包含空格？**

每个查询字符串参数的值都经过 URL 编码。URL 编码会将 URL 中常见的非法字符转换为合法字符。例如，空格字符会被转换为 `%20`。请确保对任何非字母数字的字符进行 URL 编码。当图像请求到达数据收集服务器时，Adobe 会自动对值进行 URL 解码。

有关 URL 编码工作原理的更多信息，请参阅 W3Schools 上的 [HTML URL 编码参考](https://www.w3schools.com/tags/ref_urlencode.asp)。

**一个值最多可包含多少个字符？**

每个变量的最大长度各不相同。大多数流量变量最多可容纳 100 个字节，而大多数转化变量最多可容纳 255 个字节。当图像请求到达数据收集服务器时，Adobe 会自动将值截断为最大长度。
