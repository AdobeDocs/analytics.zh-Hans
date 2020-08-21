---
title: pageUrl
description: 覆盖网站上自动收集的页面 URL。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '299'
ht-degree: 100%

---


# pageUrl

AppMeasurement 会在每次点击时自动收集页面 URL。如果要覆盖由 AppMeasurement 自动收集的页面 URL，可使用此变量。在大多数情况下，您无需设置此变量。

>[!NOTE]
>
>此变量不是 Analysis Workspace 中的可用维度。它只能在 Data Warehouse 和数据馈送中使用。如果要在 Analysis Workspace 中将页面 URL 用作维度，请考虑在每次点击时将 `pageURL` 变量传递到 eVar 中。

有时 URL 的长度会大于 255 字节。AppMeasurement 对图像请求中 URL 的前 255 字节使用 `g` 查询字符串参数。如果 URL 的长度大于 255 字节，则 URL 的其余部分会存储在 `-g` 查询字符串参数中。URL 中的协议和查询字符串均包含在此变量中。

## Adobe Experience Platform Launch 中的页面 URL

Launch 会自动填充页面 URL。但是，您可以在配置 Analytics 扩展时（全局变量）或根据规则设置页面 URL 覆盖。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 页面 URL] 部分。

可以将页面 URL 设置为任何字符串值。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.pageURL

`s.pageURL` 变量是一个包含页面 URL 的字符串。AppMeasurement 会自动收集此变量，但您可以根据需要覆盖其值。

```js
s.pageURL = "https://example.com";
```

如果要在报表中将页面 URL 用作维度，请考虑在实施中使用以下内容：

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```
