---
title: server
description: 填充“服务器”维。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# server

该变 `server` 量通常存储站点的主机名。 它通常用于包含多个域的数据的报表包。 它的功能与prop相同。

## Adobe Experience Platform Launch中的服务器

您可以在配置Analytics扩展时（全局变量）或根据规则设置服务器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到“服 [!UICONTROL 务器] ”部分。

可以将服务器设置为任何字符串值或数据元素。

## AppMeasurement中的s.server和启动自定义代码编辑器

该 `s.server` 变量是一个字符串，通常包含站点的主机名。 最大值为100字节；长值被截断。

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
