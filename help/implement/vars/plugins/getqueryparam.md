---
title: getQueryParam
description: 提取 URL 查询字符串参数的值。
translation-type: ht
source-git-commit: 03c3a954c40d17f11f4f80ee3a378fd43948cc5c
workflow-type: ht
source-wordcount: '896'
ht-degree: 100%

---


# Adobe 插件：getQueryParam

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getQueryParam` 插件允许您提取 URL 中包含的任意查询字符串参数的值。在从登录页面 URL 中提取内部和外部促销活动代码时，此插件非常有用。在提取搜索词或其他查询字符串参数时，此插件也非常有价值。

此插件在解析复杂 URL（包括散列和包含多个查询字符串参数的 URL）方面提供了强大的功能。如果您只需要处理简单的查询字符串参数，Adobe 建议您使用 Launch 中的 URL 参数功能或 AppMeasurement 中包含的 [`Util.getQueryParam()`](../functions/util-getqueryparam.md) 方法。

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
   * 操作类型：初始化 getQueryParam
1. 保存并发布对上述规则所做的更改。

## 使用 Launch 自定义代码编辑器安装此插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的[!UICONTROL 配置]按钮。
1. 展开[!UICONTROL 使用自定义代码配置跟踪]折叠面板，这会显示[!UICONTROL 打开编辑器]按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0 */
function getQueryParam(b,c,d){function h(b,a){a=a.split("?").join("&");a=a.split("#").join("&");var c=a.indexOf("&");if(b&&(-1<c||a.indexOf("=")>c)){c=a.substring(c+1);c=c.split("&");for(var d=0,k=c.length;d<k;d++){var f=c[d].split("="),e=f[1];if(f[0].toLowerCase()===b.toLowerCase())return decodeURIComponent(e||!0)}}}if("-v"===b)return{plugin:"getQueryParam",version:"4.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getQueryParam="4.0");if(b){c=c||"";d=(d||"undefined"!==typeof a&&a.pageURL||location.href)+"";(4<c.length||-1<c.indexOf("="))&&d&&4>d.length&&(a=c,c=d,d=a);a="";for(var g=b.split(","),l=g.length,e=0;e<l;e++)b=h(g[e],d),"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,a+=a?c+b:b):a=""===a?b:a+(c+b);return a}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getQueryParam` 方法使用以下参数：

* **`qsp`**（必需）：包含要在 URL 中查找的查询字符串参数列表，以逗号分隔。此列表不区分大小写。
* **`de`**（可选）：当有多个匹配的查询字符串参数时使用的分隔符。默认使用空字符串。
* **`url`**（可选）：要从中提取查询字符串参数值的自定义 URL、字符串或变量。默认值为 `window.location`。

调用此方法时，会根据上述参数和 URL 返回一个值：

* 如果找不到匹配的查询字符串参数，此方法将返回空字符串。
* 如果找到一个匹配的查询字符串参数，此方法将返回该查询字符串参数值。
* 如果找到一个匹配的查询字符串参数，但其值为空，此方法将返回 `true`。
* 如果找到多个匹配的查询字符串参数，此方法将返回一个字符串，其中每个参数值均由 `de` 参数中的字符串分隔。

## 示例调用

### 示例 1

如果当前 URL 为：

```js
http://www.abc123.com/?cid=trackingcode1
```

以下代码会将 s.campaign 设置为等于“trackingcode1”：

```js
s.campaign=s.getQueryParam('cid');
```

### 示例 2

如果当前 URL 为：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

以下代码会将 s.campaign 设置为等于“trackingcode1:123456”：

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### 示例 3

如果当前 URL 为：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

以下代码会将 s.campaign 设置为等于“trackingcode1123456”：

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### 示例 4

如果当前 URL 为：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

以下代码会将 s.campaign 设置为等于“123456”：

```js
s.campaign=s.getQueryParam('ecid');
```

### 示例 5

如果当前 URL 为：

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

以下代码会将 s.campaign 设置为等于“123456”

```js
s.campaign=s.getQueryParam('ecid');
```

**注意**：如果用于检查的 URL 中没有问号，此插件会将 URL 中的井号替换为问号。如果在用于检查的 URL 中井号前面有一个问号，此插件会将 URL 中的井号替换为与号；

### 示例 6

如果当前 URL 为...

```js
http://www.abc123.com/
```

...且如果按如下所示设置变量 s.testURL：

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

以下代码根本不会设置 s.campaign：

```js
s.campaign=s.getQueryParam('cid');
```

但是，以下代码会将 s.campaign 设置为等于“trackingcode1”：

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**注意**：第三个参数可以是代码将用于在其中查找查询字符串参数的任意字符串/变量

以下代码会将 s.eVar2 设置为等于“123456|trackingcode1|true|300”：

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* 值“123456”来自 s.testURL 变量中的 ecid 参数
* 值“trackingcode1”来自 s.testURL 变量中的 cid 参数
* 值“true”来自 s.testURL 变量中的井号后存在的位置参数（而不是参数的值）

值“300”来自 s.testURL 变量中 pos 参数的值

## 版本历史记录

### 4.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。
* 删除了 `pt` 插件的依赖项。

### 3.3（2019 年 9 月 24 日）

* 绕过了不必要的逻辑，因而减小了代码大小

### 3.2（2018 年 5 月 15 日）

* 将 `findParameterValue` 和 `getParameterValue` 函数移到了 `getQueryParam` 函数

### 3.1（2018 年 5 月 10 日）

* 修复了捕获到查询字符串参数但值为空的问题

### 3.0（2018 年 4 月 16 日）

* 修正版本（重新编译，代码更小）。
* 出于可读性目的，将帮助程序函数重命名 `findParameterValue` 和 `getParameterValue`。
* 消除了添加参数来查找 URL 散列中所包含参数的需要

### 2.5（2016 年 1 月 8 日）

* 与 H 代码和 AppMeasurement 都兼容（需要同时使用 `s.pt` 和 AppMeasurement）。

### 2.4

* 添加了 `h` 参数，允许代码查找在井号 (`#`) 后找到的查询字符串参数

### 2.3

* 修复了插件仅在跟踪代码后存在井号的情况下才能正常运行的回归问题

### 2.2

* 现已从返回值中删除井号（以及之后的所有内容）

### 2.1

* 与 H.10 代码兼容
