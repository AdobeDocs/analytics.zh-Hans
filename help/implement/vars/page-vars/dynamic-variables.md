---
title: 动态变量
description: 复制变量而不增加图像请求长度。
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# 动态变量

动态变量允许您将值从一个变量复制到另一个变量，而不会增加图像请求长度。 在多个变量中捕获相同的数据时，这些功能非常有用。

在Analytics的早期版本中，图像请求长度对于防止截断数据很重要。 AppMeasurement的改进允许更长的图像请求查询字符串，因此通常不需要动态变量。

动态变量支持图像请求中的查询字符串参数或HTTP头。 有关 [可参考的可用参数的完整列表](../../validate/query-parameters.md) ，请参阅数据收集查询参数。 请参 [阅维基百科上的标准请求字段](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) ，以获得可参考的HTTP请求字段的完整列表。

当Adobe识别动态变量前缀时，它会自动复制报表包中的查询字符串或HTTP头值。 此操作在任何其他处理（包括处理规则和VISTA规则）之前发生。

> [!TIP] 在复制变量时注意最大字符限制。 例如，如果复制 `eVar1` 到 `prop1`, `prop1` 则可能有截断值，因为它有100字节限制(而 `eVar1` 有255字节限制)。

## Adobe Experience Platform Launch中的动态变量

您可以在接受字符串的任何维字段中使用动态变量。 维值通常在配置Analytics扩展（全局变量）时或在规则下设置。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到所需的维值。

将动态变量前缀放在文本字段中，后跟要引用的查询字符串参数或HTTP头。 默认情况下，动态变量前缀为 `D=`。

## AppMeasurement和Launch自定义代码编辑器中的动态变量

动态变量是分配给其他变量的文本字符串。 默认的动态变量前缀为 `D=`。 动态变量区分大小写。

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

> [!NOTE] 在调试实施时，动态变量显示为字符串。 值由Adobe数据收集服务器在服务器端复制。
