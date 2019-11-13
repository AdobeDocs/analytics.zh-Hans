---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.useForcedLinkTracking


 变量可确定存储和报告数据的报表包。

如果发送到多个报表包（多报表包标记），则 `s.account` 可以是以逗号分隔的值列表。报表包 ID 由 Adobe 来确定。

## 参数

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 40 字节 | 在 URL 路径中 | 不适用 | 不适用 |

每个报表包 ID 必须匹配 [!DNL Admin Console] 中创建的值。每个报表包 ID 不得大于 40 字节，但所有报表包（整个逗号分隔的列表）的总大小没有任何限制。

在报表中，报表包是区段的最基础级别。您可以设置任意数量的报表包，只要不超过合同允许的最大数量即可。每个报表包都指向 Adobe 收集服务器中填充的一套专用表格。报表包由 JavaScript 代码中的`s_account`变量标识。

在 [!DNL Analytics] 网站中，位于报表左上方的下拉框显示当前的报表包。每个报表包都有一个称为报表包 ID 的唯一标识符。此`s_account`变量包含一或多个接收数据的报表包 ID。[!DNL Analytics] 用户无法查看报表包 ID 的值，且必须由 Adobe 提供或批准后才能使用。每个报表包 ID 都有一个关联的“友好名称”，该名称可在 [!DNL Admin Console] 的报表包部分进行更改。

`s_account` 变量通常在 JavaScript 文件 (s_code.js) 内声明。您可以在 HTML 页面上声明 `s_account` 变量，当 `s_account` 的值在页面之间可能会发生更改时，这是一种常见的做法。由于 `s_account` 变量具有全局范围，因此应紧接在包括 Adobe 的 JavaScript 文件之前声明该变量。如果 `s_account` 在加载 JavaScript 文件时没有值，则不会向 [!DNL Analytics] 发送数据。

Adobe 的 [!DNL DigitalPulse Debugger] 会在 URL 的路径中显示 `s_account` 值，即在单词“Image”的正下方，紧接 /b/ss/ 之后。在某些情况下，`s_account` 的值也会显示在该域中，112.2o7.net 之前。路径中的值是唯一确定目标报表包的值。下面的粗体文本显示接收发送数据的报表包，它也会在调试程序中显示。请参阅 [DigitalPulse Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## 语法和可能值

报表包 ID 是 ASCII 字符的字母数字字符串，长度不超过 40 个字节。唯一允许使用的非字母数字字符是连字符。不得使用空格、点号、逗号和其他标点符号。此`s_account`变量可能包含多个报表包，所有报表包都从该页面接收数据。

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

`s_account` 的所有值都必须由 Adobe 提供或批准。

## 示例

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

## 在 Analytics 中配置变量

Adobe [!DNL Customer Care] 可能会更改与各个报表包 ID 关联的易记名称。在 [!DNL Analytics] 网站屏幕左上方的下拉框中可看到易记名称。

## 缺陷、问题和提示

* 如果 `s_account` 为空、未声明或包含异常值，则不会收集任何数据。
* `s_account` 变量为以逗号分隔的列表（多报表包标记）时，不要在报表包 ID 间插入空格。
* 如果 [!UICONTROL s.dynamicAccountSelection] 被设置为 *True*，则使用 URL 确定目标报表包。使用 [!DNL DigitalPulse Debugger] 确定目标报表包。

* 在有些情况下，可以使用 [!DNL VISTA] 更改目标报表包。在使用第一方 Cookie 或您的网站有超过 20 个活动报表包时，建议使用 [!DNL VISTA] 把数据重新路由或复制到另一报表包。

* 始终在 JS 文件内或在被包含之前声明 `s_account`。
