---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics Implementation
solution: null
title: 动态变量
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountList

> [!NOTE] [当前的 AppMeasurement 库](../../c-appmeasurement-js/appmeasure-mjs.md)不支持 `s.dynamicAccountList` 变量。该变量只能在旧版 AppMeasurement（如 H 代码）中使用。

`s.dynamicAccountList` 变量用于帮助动态确定要将数据发送到的报表包。它将与 `dynamicAccountSelection` 和 `dynamicAccountMatch` 变量结合使用。如果将 `dynamicAccountSelection` 设置为 `true`，则将应用 `dynamicAccountList` 中的规则，并且这些规则将应用于 `dynamicAccountMatch` 中指定的 URL 部分。

## 语法和可能值

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

有效输入为一组分号分隔的规则列表，每条规则表示为一个名称=值对。每个列表都包含以下项目：

* 一个或多个报表包 ID（以逗号分隔）
* 一个等号
* 一个或多个 URL 过滤器（以逗号分隔）

该字符串中只能使用标准的 ASCII 字符（不允许有空格）。

## 示例

对于以下所有示例，页面 URL 是 `https://example.com/path2/?prod_id=12345`，`dynamicAccountSelection` 变量设置为 `true`，`s_account` 变量设置为 `examplersid`。

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## 缺陷、问题和提示

* 此变量中列出的规则按从左到右的顺序应用。如果 `dynamicAccountMatch` 变量与多个规则匹配，则使用最左侧的规则确定报表包。因此，请将较通用的规则移动到列表的右侧。
* 如果没有匹配的规则，则使用 `s_account` 中的默认报表包。
* 如果页面被保存到某个人的硬盘，或通过基于 Web 的翻译引擎（如 Google 的翻译页面）进行了翻译，则动态帐户选择可能无效。
* `dynamicAccountSelection` 规则仅适用于 `dynamicAccountMatch` 中指定的 URL 部分。
* 使用 [!DNL Adobe Experience Cloud Debugger] 来测试目标报表包。
