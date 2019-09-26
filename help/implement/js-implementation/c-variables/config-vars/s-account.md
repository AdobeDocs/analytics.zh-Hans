---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.account

 变量可确定存储和报告数据的报表包。

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. 报表包 ID 由 Adobe 来确定。

## 参数

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 40 字节 | 在 URL 路径中 | 不适用 | 不适用 |

Each report suite ID must match the value created in the [!DNL Admin Console]. 每个报表包 ID 不得大于 40 字节，但所有报表包（整个逗号分隔的列表）的总大小没有任何限制。

在报表中，报表包是区段的最基础级别。您可以设置任意数量的报表包，只要不超过合同允许的最大数量即可。每个报表包都指向 Adobe 收集服务器中填充的一套专用表格。报表包由 JavaScript 代码中的`s_account`变量标识。

在 [!DNL Analytics] 网站中，位于报表左上方的下拉框显示当前的报表包。每个报表包都有一个称为报表包 ID 的唯一标识符。此`s_account`变量包含一或多个接收数据的报表包 ID。[!DNL Analytics] 用户无法查看报表包 ID 的值，且必须由 Adobe 提供或批准后才能使用。Every report suite ID has an associated "friendly name" that can be changed in the report suites section of the [!DNL Admin Console].

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). You can declare the  variable on the HTML page, which is a common practice when the value of  may change from page to page. `s_account``s_account`Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. In some cases, the value of  also appears in the domain, before 112.2o7.net. `s_account`路径中的值是唯一确定目标报表包的值。下面的粗体文本显示接收发送数据的报表包，它也会在调试程序中显示。请参阅 [DigitalPulse Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## 语法和可能值

报表包 ID 是 ASCII 字符的字母数字字符串，长度不超过 40 个字节。唯一允许使用的非字母数字字符是连字符。不得使用空格、点号、逗号和其他标点符号。此`s_account`变量可能包含多个报表包，所有报表包都从该页面接收数据。

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

All values of  must be provided or approved by Adobe.`s_account`

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

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. 使用 [!DNL DigitalPulse Debugger] 确定目标报表包。

* 在有些情况下，可以使用 [!DNL VISTA] 更改目标报表包。在使用第一方 Cookie 或您的网站有超过 20 个活动报表包时，建议使用 [!DNL VISTA] 把数据重新路由或复制到另一报表包。

* Always declare `s_account` inside the JS file or just before it is included.
