---
title: getQueryParam
description: 提取 URL 查询字符串参数的值。
feature: Variables
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 74%

---

# Adobe 插件：getQueryParam

{{plug-in}}

`getQueryParam` 插件允许您提取 URL 中包含的任意查询字符串参数的值。在从登录页面 URL 中提取内部和外部促销活动代码时，此插件非常有用。在提取搜索词或其他查询字符串参数时，此插件也非常有价值。

此插件在解析复杂 URL（包括散列和包含多个查询字符串参数的 URL）方面提供了强大的功能。如果您只需要处理简单的查询字符串参数，Adobe建议使用URL参数功能，例如，使用Web SDK、Adobe Analytics扩展或者 [`Util.getQueryParam()`](../functions/util-getqueryparam.md) AppMeasurement中包含的方法。

## 使用Web SDK扩展安装此插件

Adobe提供了一个扩展，通过该扩展，您可以将最常用的插件与Web SDK结合使用。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击 **[!UICONTROL 标记]** 单击左侧的，然后单击所需的标记属性。
1. 单击 **[!UICONTROL 扩展]** ，然后单击 **[!UICONTROL 目录]** 选项卡
1. 找到并安装 **[!UICONTROL 常用Web SDK插件]** 扩展。
1. 单击 **[!UICONTROL 数据元素]** 单击左侧的，然后单击所需的数据元素。
1. 使用以下配置设置所需的数据元素名称：
   * 扩展：常用Web SDK插件
   * 数据元素： `getQueryParam`
1. 在右侧设置所需的参数。
1. 保存并发布对数据元素所做的更改。

## 安装插件以手动实施Web SDK

尚不支持在手动实施Web SDK时使用此插件。

## 使用Adobe Analytics扩展安装此插件

Adobe提供了一个扩展，通过该扩展，您可以将最常用的插件与Adobe Analytics结合使用。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL 目录]按钮
1. 安装并发布[!UICONTROL 常用 Analytics 插件]扩展
1. 如果还没有任何扩展，请使用以下配置创建一个标签为“初始化插件”的规则：
   * 条件：无
   * 事件：核心 - 已加载的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常用 Analytics 插件
   * 操作类型：初始化 getQueryParam
1. 保存并发布对上述规则所做的更改。

## 使用自定义代码编辑器安装此插件

如果您不想使用“常用Analytics插件”插件扩展，则可以使用自定义代码编辑器。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 展开[!UICONTROL 使用自定义代码配置跟踪]折叠面板，这会显示[!UICONTROL 打开编辑器]按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getQueryParam` 函数使用以下参数：

* **`qsp`**（必需）：包含要在 URL 中查找的查询字符串参数列表，以逗号分隔。此列表不区分大小写。
* **`de`**（可选）：当有多个匹配的查询字符串参数时使用的分隔符。默认使用空字符串。
* **`url`**（可选）：要从中提取查询字符串参数值的自定义 URL、字符串或变量。默认值为 `window.location`。

调用此函数时，会根据上述参数和 URL 返回一个值：

* 如果找不到匹配的查询字符串参数，此函数将返回空字符串。
* 如果找到一个匹配的查询字符串参数，此函数将返回该查询字符串参数值。
* 如果找到一个匹配的查询字符串参数，但其值为空，此函数将返回 `true`。
* 如果找到多个匹配的查询字符串参数，此函数将返回一个字符串，其中每个参数值均由 `de` 参数中的字符串分隔。

## 示例

```js
// Given the URL https://example.com/?cid=trackingcode
// Sets the campaign variable to "trackingcode"
s.campaign = getQueryParam('cid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode:123"
s.campaign = getQueryParam('cid,ecid',':');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode123"
s.campaign = getQueryParam('cid,ecid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123#location
// Sets the campaign variable to "123"
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com/#location&cid=trackingcode&ecid=123
// Sets the campaign variable to "123"
// The plug-in replaces the URL's hash character with a question mark if a question mark doesn't exist.
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com
// Does not set the campaign variable to a value.
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid');

// Given the URL https://example.com
// Sets the campaign variable to "trackingcode"
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid','',s.pageURL);

// Given the URL https://example.com
// Sets eVar2 to "123|trackingcode|true|300"
s.eVar1 = "https://example.com/?cid=trackingcode&ecid=123#location&pos=300";
s.eVar2 = getQueryParam('ecid,cid,location,pos','|',s.eVar1);
```

## 版本历史记录

### 4.0.1（2021 年 3 月 26 日）

* 更新了查询字符串中不存在查询参数时返回“未定义”而非 &quot;&quot; 的问题。

### 4.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。
* 删除了 pt 插件的依赖项。

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
