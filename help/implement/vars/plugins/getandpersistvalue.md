---
title: getAndPersistValue
description: 存储稍后可随时检索的值。
translation-type: ht
source-git-commit: a2970e05abf0d1f963175db6e3554aa0e3034a70
workflow-type: ht
source-wordcount: '934'
ht-degree: 100%

---


# Adobe 插件：getAndPersistValue

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getAndPersistValue` 插件允许您在 Cookie 中存储稍后可在访问期间进行检索的值。其作用与 Adobe Experience Platform Launch 中的[!UICONTROL 存储持续时间]功能类似。如果要在设置变量后的后续点击中自动将 Analytics 变量保留为相同的值，Adobe 建议使用此插件。如果 Launch 的[!UICONTROL 存储持续时间]功能足以满足需求，或者您不需要在后续点击中设置变量并将其保留为相同值，则无需使用此插件。eVar 的内置持久性不需要使用此插件，因为这些变量会由 Adobe 保留在服务器端。

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
   * 操作类型：初始化 getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getAndPersist` 方法使用以下参数：

* **`vtp`**（必需）：要在页面之间保留的值
* **`cn`**（可选）：用于存储值的 Cookie 的名称。如果未设置此参数，则将 Cookie 命名为 `"s_gapv"`
* **`ex`**（可选）：Cookie 过期前的天数。如果此参数为 `0` 或未设置，则 Cookie 将在访问结束时过期（处于不活动状态 30 分钟）。

如果已设置 `vtp` 参数中的变量，则插件会设置 Cookie，然后返回 Cookie 值。如果未设置 `vtp` 参数中的变量，则插件只会返回 Cookie 值。

## 示例

### 示例 1

以下代码将 eVar21 的值设置为等于“hello”。然后，该代码将 ev21gapv Cookie（28 天后过期）设置为等于 eVar21 的值（即“hello”）。然后，代码将 eVar21（重新）设置为等于 ev21gapv Cookie 的值。

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 示例 2

假设尚未在当前页面上设置 eVar21，但在过去 28 天内在上一页将其值设置为等于“hello”。以下代码会仅将 eVar21 设置为等于 ev21gapv Cookie 的值（即“hello”）。它不会重置 ev21gapv Cookie，因为在调用函数之前未在当前页面上设置 eVar21。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 示例 3

假设尚未在当前页面上设置 eVar21，但在过去 28 天内在上一页将其值设置为等于“hello”。以下代码仅会将 prop35 设置为等于 ev21gapv Cookie 的值（即“hello”）。它不会设置 eVar21。

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 示例 4

以下代码将 eVar21 的值设置为等于“howdy”。然后，该代码将 ev21gapv Cookie（28 天后过期）设置（或重置）为等于 eVar21 的值（即“howdy”）。该代码会将 prop35 的值设置为等于 ev21gapv Cookie 的值（即“howdy”）。

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 示例 5

假定在过去 28 天内，尚未在任何页面上设置 s.eVar21。以下代码将 s.eVar21 设置为无，因为 ev21gapv Cookie 将在上次设置后的 28 天后过期。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 示例 6

以下代码将 eVar30 的值设置为等于“shopping”。然后，它将 s_gapv Cookie（将在浏览器会话结束时过期）设置为等于 s.eVar30 的值（即，“shopping”）。然后，它将 s.eVar30 设置为等于 s_gapv Cookie 的值（即 getAndPersistValue 调用返回 s_gapv Cookie 的值，在本例中为“shopping”）。

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

如果未将 s.eVar30 设置为会话期间看到的任何其他页面上的显式值，但通过以下代码进行设置（在 doPlugins 中）...

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...将 s.eVar30 设置为等于“shopping”（即 s_gapv Cookie 持续得到的值）

## 版本历史记录

### 3.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 2.0（2018 年 4 月 16 日）

* 修正版本（代码更小）
* 现在，将 0 传递到 `ex` 参数将强制执行 30 分钟处于不活动状态后过期，而不是在浏览器会话结束时过期。

### 1.0（2016 年 1 月 18 日）

* 第一版。
