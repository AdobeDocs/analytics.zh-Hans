---
title: 使用硬编码图像请求实施
description: 使用HTML图像标记（硬编码图像请求）实施Adobe Analytics
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 使用硬编码图像请求实施

Adobe提供的AppMeasurement库编译页面上存在的变量，然后将其作为图像请求发送给Adobe。 您可以完全绕过AppMeasurement库，然后手动向Adobe发送图像请求。 此方法要求您手动制定图像请求和查询字符串。

此实现方法可用于显示来自外部源的图像的任何平台。 它根本不依赖JavaScript。

> [!NOTE] 虽然硬编码图像请求易于设置，但很难在较大的项目中调试、维护和缩放。 在继续操作之前，请确保硬编码图像请求是最佳选项。

## 图像请求语法

以下是使用HTML的硬编码图像请求示例：

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` 指定协议。 将图像请求中使用的协议与站点其他部分使用的协议相匹配。
* `example.sc.omtrdc.net` 是变量中包含的 `trackingServer` 值。
* `/b/ss/` 包含在所有图像请求中。 它是Adobe数据收集服务器上存储的图像的文件结构的一部分。
* `examplersid` 是要将数据发送到的报表包ID。
* `/1/` 是命中源。 请参 `hit_source` 阅导 [出用户指南中的数据列引用](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) 。 控制Cookie和其他方法识别访客的顺序。
* 查询字符串分隔符(`?`)之后的所有内容都是要包含在报表中的数据。 有关 [可包含在图像请求中的参数的完整列表](../validate/query-parameters.md) ，请参阅数据收集查询参数。

## 常见问题解答

了解使用硬编码图像请求的常见问题。

**查询字符串参数是否区分大小写？**

可以。确保查询字符串参数完全匹配，否则不记录这些参数。 例如， `pagename` is不是有效的查询字符串参数，而 `pageName` 是。

**我是否可以在查询字符串中包含空格？**

每个查询字符串参数的值都经过URL编码。 URL编码将URL中通常非法的字符转换为合法字符。 例如，空格字符会被转化为 `%20`. 确保任何非字母数字的字符都经过URL编码。 当图像请求到达数据收集服务器时，Adobe会自动对值进行解码。

有关 [URL编码工作方式的更多信息](https://www.w3schools.com/tags/ref_urlencode.asp) ，请参阅W3Schools上的HTML URL编码参考。

**单个值最多可包含多少个字符？**

每个变量的最大长度不同。 大多数流量变量最多可容纳100个字节，而大多数转换变量最多可容纳255个字节。 当图像请求到达数据收集服务器时，Adobe会自动将这些值截断到其最大长度。
