---
title: 动态变量
description: 在不增加图像请求长度的情况下复制变量。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 94%

---


# 动态变量

动态变量允许您在不增加图像请求长度的情况下将值从一个变量复制到另一个变量。在多个变量中获取相同的数据时，这些功能非常有用。

在 Analytics 的早期版本中，图像请求长度对于防止数据被截断很重要。AppMeasurement 经过改进后，使用更长的图像请求查询字符串，因此通常不需要动态变量。

动态变量在图像请求中支持查询字符串参数或 HTTP 标头。有关可引用的可用参数的完整列表，请参阅[数据收集查询参数](../../validate/query-parameters.md)。有关可引用的可用 HTTP 请求字段的完整列表，请参阅维基百科上的[标准请求字段](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields)。

当 Adobe 识别动态变量前缀时，它会自动复制报表包中的查询字符串或 HTTP 标头值。此操作在任何其他处理（包括处理规则和 VISTA 规则）之前执行。

>[!TIP]
>
>在复制变量时需要注意最大字符限制。例如，如果将 `eVar1` 复制到 `prop1`，`prop1` 的值可能会被截断，因为它的长度限制为 100 字节（而 `eVar1` 的长度限制为 255 字节）。

## Adobe Experience Platform Launch 中的动态变量

您可以在接受字符串的任何维度字段中使用动态变量。Dimension项通常在配置Analytics扩展（全局变量）或在规则下进行设置。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到所需的维度项。

将动态变量前缀置于文本字段中，然后放置要引用的查询字符串参数或 HTTP 标头。默认情况下，动态变量前缀为 `D=`。

## AppMeasurement 和 Launch 自定义代码编辑器中的动态变量

动态变量是分配给其他变量的文本字符串。默认的动态变量前缀为 `D=`。动态变量区分大小写。

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

>[!NOTE]
>
>在调试实施时，动态变量会显示为字符串。值由 Adobe 数据收集服务器在服务器端复制。
