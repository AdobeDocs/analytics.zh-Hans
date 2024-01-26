---
title: getAndPersistValue
description: 存储稍后可随时检索的值。
feature: Variables
exl-id: b562f9ad-3844-4535-b729-bd3f63f6f0ae
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 70%

---

# Adobe 插件：getAndPersistValue

{{plug-in}}

`getAndPersistValue` 插件允许您在 Cookie 中存储稍后可在访问期间进行检索的值。其作用与 [!UICONTROL 存储持续时间] Adobe Experience Platform数据收集中的Adobe Analytics扩展中的功能。 如果要在设置变量后的后续点击中自动将 Analytics 变量保留为相同的值，Adobe 建议使用此插件。在以下情况下，无需使用此插件 [!UICONTROL 存储持续时间] Analytics扩展中的功能便已足够。 如果您不需要设置变量并在后续点击中将变量保留为相同的值，那么也没必要使用此插件。eVar 的内置持久性不需要使用此插件，因为 eVar 会由 Adobe 保留在服务器端。

## 使用Web SDK扩展安装此插件

Adobe提供了一个扩展，通过该扩展，您可以将最常用的插件与Web SDK结合使用。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击 **[!UICONTROL 标记]** 单击左侧的，然后单击所需的标记属性。
1. 单击 **[!UICONTROL 扩展]** ，然后单击 **[!UICONTROL 目录]** 选项卡
1. 找到并安装 **[!UICONTROL 常用Web SDK插件]** 扩展。
1. 单击 **[!UICONTROL 数据元素]** 单击左侧的，然后单击所需的数据元素。
1. 使用以下配置设置所需的数据元素名称：
   * 扩展：常用Web SDK插件
   * 数据元素： `getAndPersistValue`
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
   * 操作类型：初始化 getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`getAndPersist` 函数使用以下参数：

* **`vtp`**（必需）：要在页面之间保留的值
* **`cn`**（可选）：用于存储值的 Cookie 的名称。如果未设置此参数，则将 Cookie 命名为 `"s_gapv"`
* **`ex`**（可选）：Cookie 过期前的天数。如果此参数为 `0` 或未设置，则 Cookie 将在访问结束时过期（处于不活动状态 30 分钟）。

如果已设置 `vtp` 参数中的变量，则插件会设置 Cookie，然后返回 Cookie 值。如果未设置 `vtp` 参数中的变量，则插件只会返回 Cookie 值。

## 示例

```js
// Sets eVar21 to "raccoon", and sets the ev21gapv cookie to "raccoon" (which expires in 28 days).
s.eVar21 = "raccoon";
s.eVar21 = getAndPersistValue(s.eVar21,"ev21gapv",28);

// Checks the "ev21gapv" cookie for a value and assigns it to eVar21. It does not set a cookie value or reset an existing cookie's expiration since the value is not set on the page.
// If there is a cookie, assigns eVar21 to that value. Otherwise, eVar21 is blank.
s.eVar21 = getAndPersistValue(s.eVar21,"ev21gapv",28);

// Checks the "ev21gapv" cookie for a value and assigns it to prop35. It does not set a cookie value or reset an existing cookie's expiration since eVar21 is not set on the page.
s.prop35 = getAndPersistValue(s.eVar21,"ev21gapv",28);

// Sets eVar21 to "panda", and sets the ev21gapv cookie to "panda" (which expires in 14 days). It then sets prop35 to the value contained in the ev21gapv cookie.
// Ultimately both eVar21 and prop35 contain the value "panda".
s.eVar21 = "panda";
s.prop35 = getAndPersistValue(s.eVar21,"ev21gapv",14);

// Sets eVar30 to "shopping", and sets the s_gapv cookie to "shopping" (which expires at the end of the browser session).
s.eVar30 = "shopping";
s.eVar30 = getAndPersistValue(s.eVar30);
```

## 版本历史记录

### 3.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 2.0（2018 年 4 月 16 日）

* 修正版本（代码更小）
* 现在，将 0 传递到 `ex` 参数将强制执行 30 分钟处于不活动状态后过期，而不是在浏览器会话结束时过期。

### 1.0（2016 年 1 月 18 日）

* 第一版。
