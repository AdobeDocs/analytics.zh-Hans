---
title: cleanStr
description: 从字符串中删除或替换所有不必要的字符。
translation-type: tm+mt
source-git-commit: e08f3e168a779f9678a109d7f533761629cd38f3

---


# Adobe插件：cleanStr

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics的使用中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `cleanStr` 件可删除或替换字符串中所有不必要的字符，包括HTML标记字符、额外的空格、制表符和换行／回车符。 它还替换左／右单引号(`‘` 和 `’`)直单引号(`'`)。 如果您希望从变量值中删除不必要的字符，并且Launch中的“清理文本”功能无法满足您的实施需求，则Adobe建议使用此插件。 如果收集的数据不包含不必要的字符，或者Launch中的“清理文本”功能足够，则无需此插件。

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
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `cleanStr` 法使用以下参数：

* **`str`**（必需，字符串）:要清理HTML编码、额外空白、制表符或其他不必要字符的值。

该方法返回参数的值，并删 `str` 除所有不必要的字符。

## 示例

### 示例#1

假设如下(其中点表示空格，箭头表示制表符字符

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

运行以下代码时……

```js
s.eVar1 = cleanStr(s.eVar1)
```

...eVar1将设置为等于“this is a messystring”（删除所有额外空格和所有制表符）

### 示例#2

如果...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...下面的代码运行……

```js
cleanStr(s.eVar1)
```

...s.eVar1的最终值仍将是：

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

单独运行插件（不将返回值分配给变量）实际上不会“重置”通过str参数传入的变量。

## 版本历史

### 1.0（2018年4月15日）

* 第一版。
