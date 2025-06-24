---
title: Util.getQueryParam
description: 返回查询字符串参数的值。
feature: Appmeasurement Implementation
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 79%

---

# Util.getQueryParam

浏览器 URL 中的查询字符串参数经常包含用于 Analytics 的重要数据。使用 `Util.getQueryParam()` 方法可从查询字符串中检索数据。

## 使用Adobe Analytics扩展和Web SDK扩展获取查询字符串参数数据

可以通过在数据元素中设置值来获取查询字符串参数数据。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 数据元素]选项卡，然后单击所需的数据元素（或创建数据元素）。
4. 将[!UICONTROL 扩展]下拉列表设置为&#x200B;**[!UICONTROL 核心]**，将[!UICONTROL 数据元素类型]设置为&#x200B;**[!UICONTROL 查询字符串参数]**。
5. 在文本字段中输入查询字符串参数。

查询字符串参数值会存储在数据元素中。然后，您可以引用规则中的数据元素来分配所需的变量。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.Util.getQueryParam()

调用 `s.Util.getQueryParam()` 方法可从浏览器 URL 中检索查询字符串值。包含查询字符串参数的字符串参数是必需参数。此方法会返回一个字符串，您可以将其分配给 Analytics 变量：

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

第二个可选参数允许您指定要检查查询字符串参数的字符串。默认情况下，该实用程序会检查浏览器 URL。

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

第三个可选参数允许您自定义查询字符串分隔符。其默认值为 `&`。如果查询字符串使用不同的分隔符，则可以更改此值。

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP]
>
>可使用一个名为 [`s.getQueryParam`](../plugins/getqueryparam.md) 的类似插件。此插件包含更高级的功能，但同时也更复杂，而且默认情况下不包含在 AppMeasurement 中。
