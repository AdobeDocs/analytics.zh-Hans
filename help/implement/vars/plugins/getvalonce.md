---
title: getValOnce
description: 防止将一个 Analytics 变量连续两次设置为同一个值。
translation-type: tm+mt
source-git-commit: 5a81754ca6137d7bc1e790fe537acbb4bbdb8efb
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 99%

---


# Adobe 插件：getValOnce

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`getValOnce` 插件可防止将一个变量多次设置为等于同一个值。如果您希望在发生访客刷新页面或多次访问给定页面的情况下进行去重处理，Adobe 建议您使用此插件。如果您不担心 Analysis Workspace 中的“发生次数”量度，则无需使用此插件。

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
   * 操作类型：初始化 getValOnce
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
/* Adobe Consulting Plugin: getValOnce v3.0 (Requires AppMeasurement) */
function getValOnce(vtc,cn,et,ep){var e=vtc,k=cn,l=et,m=ep;if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.0"};var c=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,a;b<window.s_c_il.length;b++)if(a=window.s_c_il[b],a._c&&"s_c"===a._c)return a}();"undefined"!==typeof c&&(c.contextData.getValOnce="3.0");window.cookieWrite=window.cookieWrite||function(b,a,d){if("string"===typeof b){var h=window.location.hostname,c=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){c=2<c?
c:2;var f=h.lastIndexOf(".");if(0<=f){for(;0<=f&&1<c;)f=h.lastIndexOf(".",f-1),c--;f=0<f?h.substring(f):h}}g=f;a="undefined"!==typeof a?""+a:"";if(d||""===a)if(""===a&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return b&&(document.cookie=encodeURIComponent(b)+"="+encodeURIComponent(a)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(b)===a:!1}};window.cookieRead=window.cookieRead||function(b){if("string"===
typeof b)b=encodeURIComponent(b);else return"";var a=" "+document.cookie,d=a.indexOf(" "+b+"="),c=0>d?d:a.indexOf(";",d);return(b=0>d?"":decodeURIComponent(a.substring(d+2+b.length,0>c?a.length:c)))?b:""};return e&&(k=k||"s_gvo",l=l||0,m="m"===m?6E4:864E5,e!==this.c_r(k))?(c=new Date,c.setTime(c.getTime()+l*m),cookieWrite(k,e,0===l?0:m),e):""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getValOnce` 方法使用以下参数：

* **`vtc`**（必需，字符串）：要检查并确定之前是否已设置为相同值的变量
* **`cn`**（可选，字符串）：包含要检查的值的 Cookie 的名称。默认为 `"s_gvo"`
* **`et`**（可选，整数）：Cookie 的过期时间（以天或分钟为单位，具体取决于 `ep` 参数）。默认值为 `0`，该值表示将在浏览器会话结束时过期
* **`ep`**（可选，字符串）：仅当还同时设置了 `et` 参数时才会设置此参数。如果希望 `et` 的过期时间以分钟而不是以天为单位，请将此参数设置为 `"m"`。默认值为 `"d"`，该值会以天为单位设置 `et` 参数。

如果 `vtc` 参数与 Cookie 值相匹配，此方法将返回空字符串。如果 `vtc` 参数与 Cookie 值不匹配，此方法会将 `vtc` 参数作为字符串返回。

## 示例调用

### 示例 1

使用此调用可防止在接下来的 30 天内连续多次将同一个值传递到 s.campaign：

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

在上述调用中，插件会先比较 s_campaign Cookie 中已包含的值与来自当前 s.campaign 变量的值。如果这两个值不匹配，插件会将 s_campaign Cookie 设置为等于来自 s.campaign 的新值，然后返回该新值。这种比较将在接下来的 30 天内持续进行

### 示例 2

使用此调用可防止在整个会话期间设置相同的值：

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

此代码可防止在整个用户会话期间连续多次将同一个值传递到 s.eVar2。由于已将过期时间设置为等于 0，因此还会忽略 ep 参数中的“m”值（在调用结束时）。此代码还会将比较值存储到 s_ev2 Cookie 中。

## 版本历史记录

### 3.0（2021年3月19日）

* 已添加版本号作为上下文数据。

### 2.01

* 修复了编写 Cookie 时的问题。

### 2.0

* 修正版本（重新编译，代码更小）。

### 1.1

* 添加了通过 `t` 参数选择有效期（分钟或天数）的选项。
* 更正了 `k` 变量的使用范围，以将该变量设为仅供此插件使用。此更改可防止页面上的其他代码可能造成的干扰。
