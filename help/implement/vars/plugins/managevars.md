---
title: manageVars
description: 一次更改多个 Analytics 变量的值。
feature: Appmeasurement Implementation
exl-id: b80d1c43-7e79-443e-84fb-1f1edffca461
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 83%

---

# Adobe 插件：manageVars

{{plug-in}}

`manageVars` 插件允许您同时处理多个 Analytics 变量的值。您还可以将值设置为小写，或一次性从多个变量值中删除不必要的字符。如果要一次清除多个变量的值，Adobe 建议您使用此插件。

## 使用Web SDK或Web SDK扩展安装此插件

尚不支持使用此插件在Web SDK中使用。

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
   * 操作类型：初始化 manageVar
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
/* Adobe Consulting Plugin: manageVars v3.0 (Requires AppMeasurement) */
function manageVars(cb,l,il){var g=cb,c=l,d=il;if("-v"===g)return{plugin:"manageVars",version:"3.0"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof f){f.contextData.manageVars="3.0";f.blankVars=function(a){this[a]&&(0>a.indexOf("contextData")?this[a]="":(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]="")))};f.lowerCaseVars=function(a){this[a]&&("events"!==a&&-1===a.indexOf("contextData")?(this[a]=this[a].toString(),0!==this[a].indexOf("D=")&&(this[a]=this[a].toLowerCase())):-1<a.indexOf("contextData")&&(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=this.contextData[a].toString().toLowerCase())))};f.cleanStr=function(a){function b(a){if("string"===typeof a){for(a=a.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g,"'").replace(/\t+/g,"").replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}this[a]&&"function"===typeof b&&(0>a.indexOf("contextData")?this[a]=b(this[a]):(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=b(this.contextData[a].toString()))))};f.pt=function(a,b,c,d){if(a&&this[c]){a=a.split(b||",");b=a.length;for(var e,f=0;f<b;f++)if(e=this[c](a[f],d))return e}};if(!f[g])return!1;c=c||"";d=d||!0;var b,e="pageName,purchaseID,channel,server,pageType,campaign,state,zip,events,products,transactionID";for(b=1;76>b;b++)e+=",prop"+b;for(b=1;251>b;b++)e+=",eVar"+b;for(b=1;6>b;b++)e+=",hier"+b;for(b=1;4>b;b++)e+=",list"+b;for(b in f.contextData)e+=",contextData."+b;if(c){if(1==d)e=c.replace("['",".").replace("']","");else if(0==d){c=c.split(",");d=e.split(",");e="";for(x in c)for(y in-1<c[x].indexOf("contextData")&&(c[x]="contextData."+c[x].split("'")[1]),d)c[x]===d[y]&&(d[y]="");for(y in d)e+=d[y]?","+d[y]:""}f.pt(e,",",g,0);return!0}return""===c&&d?(f.pt(e,",",g,0),!0):!1}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`manageVars` 函数使用以下参数：

* **`cb`**（必需，字符串）：插件用来处理 Analytics 变量的回调函数的名称。您可以使用 Adobe 函数（如 `cleanStr`）或者您自己自定义的函数。
* **`l`**（可选，字符串）：包含要处理的 Analytics 变量的逗号分隔列表。如果未设置，则将默认包含所有 Adobe Analytics 变量，包括：
   * `pageName`
   * `purchaseID`
   * `channel`
   * `server`
   * `pageType`
   * `campaign`
   * `state`
   * `zip`
   * `events`
   * `products`
   * `transactionID`
   * 所有 prop
   * 所有 eVar
   * 所有层级结构变量
   * 所有列表变量
   * 所有上下文数据变量
* **`Il`**（可选，布尔）：如果要&#x200B;**“排除”`l` 参数中声明的变量列表，而不是要包含这些变量，则将此参数设置为 `false`。默认为 `true`。

调用此函数将不会返回任何内容。相反，此方法会根据所需的回调函数更改 Analytics 变量的值。

## 示例调用

### 示例 1

以下代码...

```js
manageVars("lowerCaseVars");
```

...会将上述所有变量的值更改为小写版本。唯一的例外是events变量，因为某些事件（如scAdd、scCheckout等）区分大小写，因此不应将其更改为小写

### 示例 2

以下代码...

```js
manageVars("lowerCaseVars", "events", false);
```

...产生的结果与第一个示例基本相同，因为 events 变量默认不用小写。

### 示例 3

以下代码...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...将仅更改（例如更改为小写）eVar1、eVar2、eVar3 和 list2 的值

### 示例 4

以下代码...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...将更改（例如更改为小写）除 eVar1、eVar2、eVar3 和 list2 之外上述所有其他变量的值

### 示例 5

以下代码...

```js
manageVars("cleanStr");
```

...将更改上述所有变量的值，包括 events 变量。具体而言，cleanStr 回调函数将对每个变量的值进行如下处理：

* 删除 HTML 编码
* 删除值开始和结尾处的空格
* 将左/右单引号替换为直单引号(`'`)
* 将制表符、换行符和回车符替换为空格
* 将所有双（或三等）空格替换为单空格

## 版本历史记录

### 3.0（2021 年 3 月 19 日）

* 以上下文数据形式添加了版本号。

### 2.1（2019 年 1 月 14 日）

* 修复了 Internet Explorer 11 浏览器的错误。
* 对 `s.cleanStr` 进行了更改，现要使用常规 `cleanStr` 函数。

### 2.0（2018 年 5 月 7 日）

* 修正版本（包括对插件的彻底再分析/重写）
* 添加了 `cleanStr` 回调函数
