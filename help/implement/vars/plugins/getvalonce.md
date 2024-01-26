---
title: getValOnce
description: 防止将一个 Analytics 变量连续两次设置为同一个值。
feature: Variables
exl-id: 23bc5750-43a2-4693-8fe4-d6b31bc34154
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 74%

---

# Adobe 插件：getValOnce

{{plug-in}}

`getValOnce` 插件可防止将一个变量多次设置为等于同一个值。如果您希望在发生访客刷新页面或多次访问给定页面的情况下进行去重处理，Adobe 建议您使用此插件。如果您不担心 Analysis Workspace 中的“发生次数”量度，则无需使用此插件。

## 使用Web SDK扩展安装此插件

Adobe提供了一个扩展，通过该扩展，您可以将最常用的插件与Web SDK结合使用。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击 **[!UICONTROL 标记]** 单击左侧的，然后单击所需的标记属性。
1. 单击 **[!UICONTROL 扩展]** ，然后单击 **[!UICONTROL 目录]** 选项卡
1. 找到并安装 **[!UICONTROL 常用Web SDK插件]** 扩展。
1. 单击 **[!UICONTROL 数据元素]** 单击左侧的，然后单击所需的数据元素。
1. 使用以下配置设置所需的数据元素名称：
   * 扩展：常用Web SDK插件
   * 数据元素： `getValOnce`
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
   * 操作类型：初始化 getValOnce
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
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getValOnce v3.1 */
function getValOnce(vtc,cn,et,ep){var e=vtc,i=cn,t=et,n=ep;  if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.1"};var o=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();if(void 0!==o&&(o.contextData.getValOnce="3.1"),window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){var n=window.location.hostname,o=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){o=2<o?o:2;var r=n.lastIndexOf(".");if(0<=r){for(;0<=r&&1<o;)r=n.lastIndexOf(".",r-1),o--;r=0<r?n.substring(r):n}}if(g=r,i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var f=new Date;f.setTime(f.getTime()+6e4*t)}else f=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!=typeof cookieRead)&&cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),n=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>n?i.length:n)))?e:""},e){var i=i||"s_gvo",t=t||0,n="m"===n?6e4:864e5;if(e!==cookieRead(i)){var r=new Date;return r.setTime(r.getTime()+t*n),cookieWrite(i,e,0===t?0:r),e}}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getValOnce` 函数使用以下参数：

* **`vtc`**（必需，字符串）：要检查并确定之前是否已设置为相同值的变量
* **`cn`**（可选，字符串）：包含要检查的值的 Cookie 的名称。默认为 `"s_gvo"`
* **`et`**（可选，整数）：Cookie 的过期时间（以天或分钟为单位，具体取决于 `ep` 参数）。默认值为 `0`，该值表示将在浏览器会话结束时过期
* **`ep`**（可选，字符串）：仅当还同时设置了 `et` 参数时才会设置此参数。如果希望 `et` 的过期时间以分钟而不是以天为单位，请将此参数设置为 `"m"`。默认值为 `"d"`，该值会以天为单位设置 `et` 参数。

如果 `vtc` 参数与 Cookie 值相匹配，此函数将返回空字符串。如果 `vtc` 参数与 Cookie 值不匹配，此函数会将 `vtc` 参数作为字符串返回。

## 示例

```js
// Prevent the same value from being passed in to the campaign variable more than once in a row for next 30 days
s.campaign = getValOnce(s.campaign,"s_campaign",30);

// Prevent the same value from being passed in to eVar2 more than once in a row for the browser session
s.eVar2 = getValOnce(s.eVar2,"s_ev2");

// Prevent the same value from being passed in to eVar8 more than once in a row for 10 minutes
s.eVar8 = getValOnce(s.eVar8,"s_ev8",10,"m");
```

## 版本历史记录

### 3.1（2022年9月22日）

* 修复了到期错误

### 3.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 2.01

* 修复了编写 Cookie 时的问题。

### 2.0

* 修正版本（重新编译，代码更小）。

### 1.1

* 添加了通过 `t` 参数选择有效期（分钟或天数）的选项。
* 更正了 `k` 变量的使用范围，以将该变量设为仅供此插件使用。此更改可防止页面上的其他代码可能造成的干扰。
