---
title: cleanStr
description: 删除或替换字符串中所有不必要的字符。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 100%

---


# Adobe 插件：cleanStr

>[!IMPORTANT]
>
> 此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

`cleanStr` 插件可删除或替换字符串中所有不必要的字符，包括 HTML 标记字符、额外的空格、制表符和换行符/回车符。它还会将左/右单引号（`‘` 和 `’`）替换为直单引号 (`'`)。如果您想要从变量值中删除不必要的字符，并且 Launch 中的“清理文本”功能无法满足您的实施需求，则 Adobe 建议您使用此插件。如果收集的数据不包含不必要的字符，或者 Launch 中的“清理文本”功能满足您的实施需求，则无需使用此插件。

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
   * 操作类型：初始化 cleanStr
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
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用此插件

`cleanStr` 方法使用以下参数：

* **`str`**（必需，字符串）：用于清理 HTML 编码、额外空格、制表符或其他不必要字符的值。

该方法会返回 `str` 参数的值，并删除所有不必要的字符。

## 示例

### 示例 1

假设以下字符串（其中点代表空格，而箭头代表制表符）

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

运行以下代码时...

```js
s.eVar1 = cleanStr(s.eVar1)
```

...eVar1 将被设置为等于“this is a messystring”（删除了所有额外空格和所有制表符）

### 示例 2

如果...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...并运行以下代码...

```js
cleanStr(s.eVar1)
```

...s.eVar1 的最终值仍将为：

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

单独运行此插件（不将返回值指定给变量）实际上不会“重置”通过 str 参数传入的变量。

## 版本历史记录

### 1.0（2018 年 4 月 15 日）

* 第一版。
