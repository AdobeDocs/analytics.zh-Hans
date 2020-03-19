---
title: Util.getQueryParam
description: 返回查询字符串参数的值。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.getQueryParam

浏览器URL中的查询字符串参数经常包含Analytics的重要数据。 使用该 `Util.getQueryParam()` 方法从查询字符串检索数据。

## 在Adobe Experience Platform Launch中获取查询字符串参数数据

可以通过在数据元素中设置值来获取查询字符串参数数据。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到选项卡， [!UICONTROL Data Elements] 然后单击所需的数据元素（或创建数据元素）。
4. 将下拉 [!UICONTROL Extension] 列表设 [!UICONTROL Core]置为，将 [!UICONTROL Data Element Type] 其设置为 [!UICONTROL Query String Parameter]。
5. 在文本字段中输入查询字符串参数。

查询字符串参数值存储在数据元素中。 然后，您可以引用规则中的数据元素来分配Analytics变量。

## AppMeasurement和Launch自定义代码编辑器中的s.Util.getQueryParam()

调用该 `s.Util.getQueryParam()` 方法可从浏览器URL检索查询字符串值。 包含查询字符串参数的字符串参数是必需的。 此方法返回一个字符串，您可以将其分配给Analytics变量：

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

第二个可选参数允许您指定要检查查询字符串参数的字符串。 默认情况下，该实用程序会查看浏览器URL。

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

第三个可选参数允许您自定义查询字符串分隔符。 Its default value is `&`. 如果查询字符串使用不同的分隔符，则可以更改此值。

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

> [!TIP] 还有一个名为的类似 [`s.getQueryParam`](../plugins/getqueryparam.md) 插件。 此插件包含更高级的功能，但也更复杂，默认情况下不包含在AppMeasurement中。
