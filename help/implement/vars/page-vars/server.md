---
title: server
description: 填充“服务器”维度。
translation-type: ht
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9
workflow-type: ht
source-wordcount: '159'
ht-degree: 100%

---


# server

`server` 变量通常存储网站的主机名。它通常在包含来自多个域的数据的报表包中使用。它的功能与 prop 相同。

## Adobe Experience Platform Launch 中的服务器

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置服务器。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 服务器]部分。

可以将服务器设置为任何字符串值或数据元素。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.server

`s.server` 变量是一个字符串，通常包含网站的主机名。其值的最大长度为 100 字节；超出此长度的值会被截断。

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
