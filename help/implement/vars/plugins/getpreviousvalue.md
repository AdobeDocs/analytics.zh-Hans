---
title: getPreviousValue
description: 获取传递到变量的上一个值。
feature: Variables
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 77%

---

# Adobe 插件：getPreviousValue

{{plug-in}}

`getPreviousValue` 插件允许您将一个变量设置为在上一次点击时设置的值。如果您的实施包含当前点击的所有所需值，则无需使用此插件。

## 使用Web SDK扩展安装此插件

Adobe提供了一个扩展，通过该扩展，您可以将最常用的插件与Web SDK结合使用。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击 **[!UICONTROL 标记]** 单击左侧的，然后单击所需的标记属性。
1. 单击 **[!UICONTROL 扩展]** ，然后单击 **[!UICONTROL 目录]** 选项卡
1. 找到并安装 **[!UICONTROL 常用Web SDK插件]** 扩展。
1. 单击 **[!UICONTROL 数据元素]** 单击左侧的，然后单击所需的数据元素。
1. 使用以下配置设置所需的数据元素名称：
   * 扩展：常用Web SDK插件
   * 数据元素： `getPreviousValue`
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
   * 操作类型：初始化 getPreviousValue
1. 保存并发布对上述规则所做的更改。

## 使用自定义代码编辑器安装此插件

如果您不想使用“常用Analytics插件”插件扩展，则可以使用自定义代码编辑器。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 展开[!UICONTROL 使用自定义代码配置跟踪]折叠面板，这会显示[!UICONTROL 打开编辑器]按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

## 使用 AppMeasurement 安装此插件

在实例化（使用 [`s_gi`](../functions/s-gi.md)）Analytics 跟踪对象后，将以下代码复制并粘贴到 AppMeasurement 文件中的任意位置。在您的实施中保留代码的注释和版本号可帮助 Adobe 对任何潜在问题进行疑难解答。

```js
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getPreviousValue` 函数使用以下参数：

* **`v`**（字符串，必需）：具有要传递给下一个图像请求的值的变量。用于检索上一页值的常用变量为 `s.pageName`。
* **`c`**（字符串，可选）：用于存储值的 Cookie 的名称。如果未设置此参数，则将默认使用 `"s_gpv"`。

调用此函数时，将返回 Cookie 中包含的字符串值。然后，此插件会重置 Cookie 过期时间，并为其分配 `v` 参数中的变量值。该 Cookie 将在处于非活动状态 30 分钟后过期。

## 示例

```js
// 1. Sets prop7 to the cookie value contained in gpv_Page
// 2. Resets the gpv_Page cookie value to the page variable
// 3. If the page variable is not set, reset the gpv_Page cookie expiration
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if event1 is in the events variable.
if(inList(s.events,"event1")) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if the page variable is currently set on the page
if(s.pageName) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets eVar10 equal to the cookie value contained in s_gpv, then sets the s_gpv cookie to the current value of eVar1.
s.eVar10 = getPreviousValue(s.eVar1);
```

## 罕见情况

如果将与 `v` 参数关联的变量设为新值且运行 `getPreviousValue` 插件，但未同时发送 Analytics 服务器调用，则在下次运行插件时，仍会将 `v` 参数的新值视为“上一个值”。
例如，假定以下代码在访问的第一个页面上运行：

```js
s.pageName = "Home";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

此代码会生成一个服务器调用，其中 `pageName` 为“Home”，并且未设置 prop7。不过，对 `getPreviousValue` 的调用会将 `pageName` 的值存储在 `gpv_Page` Cookie 中。假定以下代码紧接着在同一页面上运行：

```js
s.pageName = "New value";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
```

由于此代码块中未运行 `t()` 函数，因此不会发送其他图像请求。然而，如果此时运行 `getPreviousValue` 函数代码，则 `prop7` 将设置为 `pageName` 的上一个值（“Home”），然后将 `pageName` 的新值（“New value”）存储在 `gpv_Page` Cookie 中。接下来，假定访客导航到其他页面，并且以下代码在该页面上运行：

```js
s.pageName = "Page 2";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

当 `t()` 函数运行时，会创建一个图像请求，其中 `pageName` 为“Page 2”且 `prop7` 为“New value”，它是上次调用 `getPreviousValue` 时 `pageName` 的值。虽然 `prop7` 的值 `"Home"` 是传递到 `pageName` 的第一个值，但“Home”从未包含在任何实际图像请求中。

## 版本历史记录

### 3.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### v2.0（2019 年 10 月 7 日）

* 修正版本（对逻辑进行了彻底重写）。
