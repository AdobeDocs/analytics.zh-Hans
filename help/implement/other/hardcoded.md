---
title: 使用硬编码图像请求实施
description: 使用 HTML 图像标记（硬编码图像请求）实施 Adobe Analytics。
feature: Implementation Basics
exl-id: 84247daf-c94b-456c-9824-6d4a0b3e6065
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 100%

---

# 使用硬编码图像请求实施

Adobe 提供的 AppMeasurement 库可编译页面上存在的变量，然后将其作为图像请求发送到 Adobe。您完全可以绕过 AppMeasurement 库，手动向 Adobe 发送图像请求。此方法要求您手动构建图像请求和查询字符串。

这种实施方法可在显示外部图像的任意平台上使用。此方法根本不依赖 JavaScript。

>[!NOTE]
>
>虽然硬编码图像请求很容易设置，但却很难在较大的项目中调试、维护和扩展。在继续操作之前，请确保硬编码图像请求是最符合您需求的选择。

## 图像请求语法

以下是使用 HTML 的示例硬编码图像请求：

```html
<img src="https://example.data.adobedc.net/b/ss/examplersid/1/s234234238479?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` 指定协议。将图像请求中使用的协议与网站其他部分使用的协议进行匹配。
* `example.data.adobedc.net` 是 [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) 变量中包含的值。
* `/b/ss/` 包含在所有图像请求中。它是 Adobe 数据收集服务器上所存储图像的文件结构的一部分。
* `examplersid` 是要将数据发送到的报表包 ID。对于多个报表包，请使用逗号分隔 ID，并且不要使用空格（例如 `examplersid1,examplersid2` 等）。
* `/1/` 是点击源。请参阅导出用户指南中[数据列引用](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)下的 `hit_source`。控制 Cookie 和其他方法在识别访客时所采用的顺序。
* `/s234234238479`（`"s"` + 随机数）可阻止浏览器缓存图像请求。
* 查询字符串分隔符 (`?`) 之后的所有内容都是要包含到报表中的数据。有关可包含到图像请求中的完整参数列表，请参阅[数据收集查询参数](../validate/query-parameters.md)。

## Microsoft Outlook 中的硬编码图像请求

由于大多数电子邮件都是基于 HTML，因此可以跟踪打开的电子邮件并将相关数据发送到 Adobe Analytics。如果贵组织选择使用此方法，请注意以下事项：

* 每个电子邮件渲染器都可能会递增一次可计费服务器调用。
* 只会跟踪支持 HTML 并允许使用图像的电子邮件客户端。默认情况下，某些电子邮件客户端（例如 Microsoft Outlook）会阻止外部图像。在收件人选择下载外部图像后，才会跟踪这些电子邮件。

要撰写包含图像请求的 Outlook 电子邮件，请执行以下操作：

1. 打开 HTML 编辑器。如果 HTML 编辑器不可用，也可以使用纯文本编辑器。
2. 在新建的 HTML 文件中，插入一个硬编码图像请求 `<img>` 标记，该标记包裹在 `<body>` 标记中。
3. 保存 HTML 文件。
4. 打开 Microsoft Outlook 并撰写电子邮件。
5. 转到“插入”选项卡，然后单击&#x200B;**附加文件**。选择图像请求 HTML 文件。
6. 单击“插入”旁边的弹出菜单，然后选择&#x200B;**插入为文本**。如果单击不带弹出菜单的“插入”按钮，则 HTML 文件将变为一个不起任何作用的附件。

您的电子邮件似乎没有变化，因为图像请求是 1x1 透明像素。如果出于测试目的要查看图像请求，请修改 HTML 文件，使其包含边框、附加文本或其他内容。

## 常见问题解答

了解使用硬编码图像请求时遇到的常见问题。

### 查询字符串参数是否区分大小写？

是的。请确保查询字符串参数完全匹配，否则将不会记录这些参数。例如，`pagename` 不是有效的查询字符串参数，而 `pageName` 才是有效的查询字符串参数。

### 查询字符串中是否可以包含空格？

每个查询字符串参数的值都经过 URL 编码。URL 编码会将 URL 中常见的非法字符转换为合法字符。例如，空格字符会被转换为 `%20`。请确保对任何非字母数字的字符进行 URL 编码。当图像请求到达数据收集服务器时，Adobe 会自动对值进行 URL 解码。

有关 URL 编码工作原理的更多信息，请参阅 W3Schools 上的 [HTML URL 编码参考](https://www.w3schools.com/tags/ref_urlencode.asp)。

### 一个值最多可包含多少个字符？

每个变量的最大长度各不相同。大多数流量变量最多可容纳 100 个字节，而大多数转化变量最多可容纳 255 个字节。当图像请求到达数据收集服务器时，Adobe 会自动将值截断为最大长度。
