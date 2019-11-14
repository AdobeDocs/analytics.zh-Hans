---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# server

 变量用于显示网页的域（显示访客访问的域）或提供页面的服务器（用于负载平衡快速引用）。

<!-- 

server.xml

 -->

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | server | 服务器 | "" |

如果您的网站有多个域提供相同的内容服务，则&#x200B;*`server`*&#x200B;变量可用于跟踪访客使用了这其中哪些域。以下 JavaScript 将页面的域填入服务器变量。

```js
s.server=window.location.hostname
```

如果您使用服务器变量为负载平衡提供快速指导，则可以将服务器名称或数量填入服务器变量。请参阅以下示例：

```js
s.server="server 14"
```

虽然[!UICONTROL 最受欢迎服务器]报表可用作负载平衡快速引用，但它并不能精确地测量服务器负载。例如，后退按钮流量并不会增加服务器负载，但会在报表中显示。该报表不会显示哪些服务器提供图像或大容量下载服务。

**语法和可能值** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

*`server`* 变量除标准变量限制以外，无其它限制。

**示例** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**配置设置** {#section_969DB379D5BD469FBEE8D505D3000E49}

无

**缺陷、问题和提示** {#section_42A28F9B01574F38891D9D54B411D8FE}

*`server`* 变量可用于显示哪些域最受欢迎或哪些服务器提供的网页最多。

