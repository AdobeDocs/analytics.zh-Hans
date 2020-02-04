---
title: manageVars
description: 一次更改多个Analytics变量的值。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobe插件：manageVars

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics的使用中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该 `manageVars` 插件允许您同时操作多个Analytics变量的值。 您还可以将值设置为小写，或同时从多个变量值中删除不必要的字符。 如果要同时清除多个变量的值，Adobe建议使用此插件。

## 使用Adobe Experience Platform Launch扩展安装插件

Adobe提供了一个扩展，允许您使用最常用的插件。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击“目 [!UICONTROL 录] ”按钮
1. 安装和发布 [!UICONTROL Common Analytics插件扩展]
1. 对于要使用插件的任何启动规则，请添加一个具有以下配置的操作：
   * 扩展：常见分析插件
   * 操作类型：初始化addProductEvar
1. 保存更改并发布到规则

## 使用Launch自定义代码编辑器安装插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics扩 [!UICONTROL 展下的] “配置”按钮。
1. 使用自定 [!UICONTROL 义代码accordion展开“配置跟踪] ”，该面板显示“打 [!UICONTROL 开编辑器] ”按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存更改并将其发布到Analytics扩展。

## 使用AppMeasurement安装插件

在实例化（使用）Analytics跟踪对象后，复制并粘贴AppMeasurement文件中的任意位置的以下代 `s_gi`码。 在您的实施中保留代码的注释和版本号可帮助Adobe解决任何潜在问题。

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

## 使用插件

该方 `manageVars` 法使用以下参数：

* **`cb`**（必需，字符串）:插件用来操作Analytics变量的回调函数的名称。 您可以使用Adobe函数（如）或`cleanStr`您自己的自定义函数。
* **`l`**（可选，字符串）:要处理的Analytics变量的逗号分隔列表。 未设置时默认为所有Adobe Analytics变量，包括：
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
   * 所有prop
   * 所有eVar
   * 所有层次结构变量
   * 所有列表变量
   * 所有上下文数据变量
* **`Il`**（可选，布尔）:如果要`false`排除参数中声&#x200B;*明的变量列表*，而不是包括`l`这些变量，则设置为。 默认为`true`。

调用此方法不会返回任何内容。 相反，它会根据所需的回调函数更改Analytics变量的值。

## 示例调用

### 示例#1

以下代码……

```js
s.manageVars("lowerCaseVars");
```

...将上述所有变量的值更改为小写版本。  这的唯一例外是events变量，因为某些事件（如scAdd、scCheckout等）区分大小写且不应小写

### 示例#2

以下代码……

```js
s.manageVars("lowerCaseVars", "events", false);
```

...由于events变量在默认情况下不小写，因此与第一个示例产生的结果基本相同。

### 示例#3

以下代码……

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...将仅更改（例如小写）eVar1、eVar2、eVar3和list2的值

### 示例#4

以下代码……

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...将更改（例如小写）上述所有变量的值，eVar1、eVar2、eVar3和list2除外

### 示例#5

以下代码……

```js
s.manageVars("cleanStr");
```

...更改上述所有变量的值，包括事件变量。  具体而言，cleanStr回调函数对每个变量的值执行以下操作：

* 删除HTML编码
* 删除值开始和结尾处的空格
* 替换左／右单引号(例如，“)”，单引号(&#39;)
* 将制表符、换行符和回车符替换为空格
* 替换所有双（或三等）单空格

## 版本历史

### 2.1（2019年1月14日）

* Internet Explorer 11浏览器的错误修复。
* 对的更 `s.cleanStr`改，现在使用常规 `cleanStr` 函数。

### 2.0（2018年5月7日）

* 点发行（包括插件的完全重新分析／重写）
* 添加了 `cleanStr` 回调函数
