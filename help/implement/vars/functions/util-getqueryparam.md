---
title: Util.getQueryParam
description: 返回查询字符串参数的值。
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Util.getQueryParam

浏览器URL中的查询字符串参数经常包含Analytics的重要数据。 使用该 `Util.getQueryParam` 方法从查询字符串检索数据。

## 在Adobe Experience Platform Launch中获取查询字符串参数数据

可以通过在数据元素中设置值来获取查询字符串参数数据。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“数 [!UICONTROL 据元素] ”选项卡，然后单击所需的数据元素（或创建数据元素）。
4. 将“扩 [!UICONTROL 展] ”下拉列表设 [!UICONTROL 置为Core]，将“ [!UICONTROL 数据元素类型] ”设置为 Query String参数。
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

> [!NOTE] AppMeasurement的先前版本有一个名为可用的插 `s.getQueryParam` 件。 此插件不再需要，因为默认情况下，它现在包含在AppMeasurement中。
