---
title: getPageName
description: 从当前网站路径创建一个简单易读的 pageName。
exl-id: a3aaeb5d-65cd-45c1-88bb-f3c0efaff110
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '736'
ht-degree: 100%

---

# Adobe 插件：getPageName

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getPageName` 插件可为当前 URL 创建一个简单易读且格式友好的版本。如果您希望在报告中使用易于设置且便于理解的 [`pageName`](../page-vars/pagename.md) 值，Adobe 建议您使用此插件。如果已经有 `pageName` 变量的命名结构（如通过数据层命名），则无需使用此插件。当没有其他解决方案可用来设置 `pageName` 变量时，最好使用此插件。

## 使用 Adobe Experience Platform Launch 扩展安装此插件

Adobe 提供了一个扩展，通过该扩展，您可以使用一些最常用的插件。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL 目录]按钮
1. 安装并发布[!UICONTROL 常用 Analytics 插件]扩展
1. 如果还没有任何扩展，请使用以下配置创建一个标签为“初始化插件”的规则：
   * 条件：无
   * 事件：核心 - 已加载的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常用 Analytics 插件
   * 操作类型：初始化 getPageName
1. 保存并发布对上述规则所做的更改。

## 使用 Launch 自定义代码编辑器安装此插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的[!UICONTROL 配置]按钮。
1. 展开[!UICONTROL 使用自定义代码配置跟踪]折叠面板，这会显示[!UICONTROL 打开编辑器]按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

## 使用 AppMeasurement 安装此插件

在实例化（使用 [`s_gi`](../functions/s-gi.md)）Analytics 跟踪对象后，将以下代码复制并粘贴到 AppMeasurement 文件中的任意位置。在您的实施中保留代码的注释和版本号可帮助 Adobe 对任何潜在问题进行疑难解答。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.2 */
var getPageName=function(si,qv,hv,de){var a=si,b=qv,f=hv,e=de;if("-v"===a)return{plugin:"getPageName",version:"4.2"};a:{if("undefined"!==typeof window.s_c_il){var d=0;for(var g;d<window.s_c_il.length;d++)if(g=window.s_c_il[d],g._c&&"s_c"===g._c){d=g;break a}}d=void 0}"undefined"!==typeof d&&(d.contextData.getPageName="4.2");var c=location.hostname,h=location.pathname.substring(1).split("/"),l=h.length,k=location.search.substring(1).split("&"),m=k.length;d=location.hash.substring(1).split("&");g=d.length;e=e?e:"|";a=a?a:c;b=b?b:"";f=f?f:"";if(1===l&&""===h[0])a=a+e+"home";else for(c=0;c<l;c++)a=a+e+decodeURIComponent(h[c]);if(b&&(1!==m||""!==k[0]))for(h=b.split(","),l=h.length,c=0;c<l;c++)for(b=0;b<m;b++)if(h[c]===k[b].split("=")[0]){a=a+e+decodeURIComponent(k[b]);break}if(f&&(1!==g||""!==d[0]))for(f=f.split(","),k=f.length,c=0;c<k;c++)for(b=0;b<g;b++)if(f[c]===d[b].split("=")[0]){a=a+e+decodeURIComponent(d[b]);break}return a.substring(a.length-e.length)===e?a.substring(0,a.length-e.length):a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getPageName` 方法使用以下参数：

* **`si`**（可选，字符串）：插入到字符串开头的 ID，表示网站的 ID。此值可以是数字 ID 或友好名称。如果未设置此值，则将默认使用当前域。
* **`qv`**（可选，字符串）：以逗号分隔的查询字符串参数列表，其中包含在 URL 中找到的已添加到字符串的参数（如果可找到）
* **`hv`**（可选，字符串）：以逗号分隔的参数列表，其中包含在 URL 散列中找到的已添加到字符串的参数（如果可找到）
* **`de`**（可选，字符串）：用于拆分字符串各个部分的分隔符。默认使用管道分隔符 (`|`)。

此方法将返回一个包含当前 URL 的友好格式版本的字符串。此字符串通常会被分配给 `pageName` 变量，但也可以用于其他变量。

## 示例调用

### 示例 1

如果当前 URL 为...

```js
https://mail.google.com/mail/u/0/#inbox
```

...并运行以下代码...

```js
s.pageName = getPageName()
```

...s.pageName 的最终值将为：

```js
s.pageName = "mail.google.com|mail|u|0";
```

### 示例 2

如果当前 URL 为...

```js
https://mail.google.com/mail/u/0/#inbox
```

...并运行以下代码...

```js
s.pageName = getPageName("gmail")
```

...s.pageName 的最终值将为：

```js
s.pageName = "gmail|mail|u|0";
```

### 示例 3

如果当前 URL 为...

```js
https://www.google.com/
```

...并运行以下代码...

```js
s.pageName = getPageName()
```

...s.pageName 的最终值将为：

```js
s.pageName = "www.google.com|home"
```

**注意**：当代码在不包含路径的 URL 上运行时，代码会始终在返回值的末尾处添加“home”值

### 示例 4

如果当前 URL 为...

```js
https://www.google.com/
```

...并运行以下代码...

```js
s.pageName = getPageName("google","","","|")
```

...s.pageName 的最终值将为：

```js
s.pageName = "google|home"
```

### 示例 5

如果当前 URL 为...

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...并运行以下代码...

```js
s.pageName = getPageName()
```

...s.pageName 的最终值将为：

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

但是，如果运行以下代码...

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...s.pageName 的最终值将为：

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## 从先前的版本升级

不论是否存在 Adobe Analytics 的 AppMeasurement 对象（即“s”对象），4.0 及更高版本的 getPageName 插件都可以正常运行。如果选择升级到此版本，请务必从调用中删除所有“s”对象的实例，以更改用于调用此插件的代码。
例如，将以下代码：

```js
s.pageName = s.getPageName();
```

...更改为下列代码：

```js
s.pageName = getPageName();
```

## 版本历史记录

### 4.2（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 4.1（2019 年 9 月 17 日）

* 将默认分隔符值从“冒号 + 空格”更改为管道字符。

### 4.0（2018 年 5 月 22 日）

* 对插件进行了彻底的再分析/重写
