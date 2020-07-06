---
title: manageVars
description: 一次更改多个 Analytics 变量的值。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 100%

---


# Adobe 插件：manageVars

>[!IMPORTANT]
>
> 此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`manageVars` 插件允许您同时处理多个 Analytics 变量的值。您还可以将值设置为小写，或一次性从多个变量值中删除不必要的字符。如果要一次清除多个变量的值，Adobe 建议您使用此插件。

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
   * 操作类型：初始化 manageVar
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
/* Adobe Consulting Plugin: manageVars v2.1 (Requires pt plug-in and other necessary callback plug-ins) */
s.manageVars=function(cb,l,il){var s=this;if(!s[cb])return!1;l=l||"";il=il||!0;var a,d="pageName,purchaseID,channel,server, pageType,campaign,state,zip,events,products,transactionID";for(a=1;76>a;a++)d+=",prop"+a;for(a=1;251>a;a++)d+=",eVar"+a;for(a=1;6>a;a++)d+=",hier"+a;for(a=1;4>a;a++)d+=",list"+a;for(a in s.contextData)d+=",contextData."+a;if(l){if(1==il)d=l.replace("['", ".").replace("']","");else if(0==il){l=l.split(",");il=d.split(",");d="";for(x in l)for(y in-1<l[x].indexOf("contextData")&& (l[x]="contextData."+l[x].split("'")[1]),il)l[x]===il[y]&&(il[y]="");for(y in il)d+=il[y]?","+il[y]:""}s.pt(d,",",cb,0);return!0} return""===l&&il?(s.pt(d,",",cb,0),!0):!1};

/* Adobe Consulting Plugin: lowerCaseVars for manageVars (Requires manageVars plug-in) */
s.lowerCaseVars=function(v){var s=this;s[v]&&("events"!==v&&-1===v.indexOf("contextData")?(s[v]=s[v].toString(),0!== s[v].indexOf("D=")&&(s[v]=s[v].toLowerCase())):-1<v.indexOf("contextData")&&(v=v.substring(v.indexOf(".")+1),s.contextData[v]&& (s.contextData[v]=s.contextData[v].toString().toLowerCase())))};

/* Adobe Consulting Plugin: cleanStr for manageVars (Requires manageVars and cleanStr plug-ins) */
s.cleanStr=function(v){var s=this;s[v]&&"function"!==typeof cleanStr&&(0>v.indexOf("contextData")?s[v]=cleanStr(s[v]): (v=v.substring(v.indexOf(".")+1),s.contextData[v]&&(s.contextData[v]=cleanStr(s.contextData[v].toString()))))};

/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g, "'").replace(/\t+/g,"").replace(/[\n\r]/g," ");for(;-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};

/* Adobe Consulting Plugin: pt v2.01 */
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`manageVars` 方法使用以下参数：

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

调用此方法将不会返回任何内容。相反，此方法会根据所需的回调函数更改 Analytics 变量的值。

## 示例调用

### 示例 1

以下代码...

```js
s.manageVars("lowerCaseVars");
```

...会将上述所有变量的值更改为小写版本。但唯有 events 变量例外，因为某些 events 变量（如 scAdd、scCheckout 等）要区分大小写，因此不应将其更改为小写

### 示例 2

以下代码...

```js
s.manageVars("lowerCaseVars", "events", false);
```

...产生的结果与第一个示例基本相同，因为 events 变量默认不用小写。

### 示例 3

以下代码...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...将仅更改（例如更改为小写）eVar1、eVar2、eVar3 和 list2 的值

### 示例 4

以下代码...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...将更改（例如更改为小写）除 eVar1、eVar2、eVar3 和 list2 之外上述所有其他变量的值

### 示例 5

以下代码...

```js
s.manageVars("cleanStr");
```

...将更改上述所有变量的值，包括 events 变量。具体而言，cleanStr 回调函数将对每个变量的值进行如下处理：

* 删除 HTML 编码
* 删除值开始和结尾处的空格
* 将左/右单引号（如 ’）替换为直单引号 (&#39;)
* 将制表符、换行符和回车符替换为空格
* 将双倍（或三倍及以上）行距均替换为单倍行距

## 版本历史记录

### 2.1（2019 年 1 月 14 日）

* 修复了 Internet Explorer 11 浏览器的错误。
* 对 `s.cleanStr` 进行了更改，现要使用常规 `cleanStr` 函数。

### 2.0（2018 年 5 月 7 日）

* 修正版本（包括对插件的彻底再分析/重写）
* 添加了 `cleanStr` 回调函数
