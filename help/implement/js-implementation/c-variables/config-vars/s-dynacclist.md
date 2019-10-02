---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# s.dynamicAccountList

> [!NOTE] 当前 `s.dynamicAccountList` AppMeasurement库中不 [支持该变量](../../c-appmeasurement-js/appmeasure-mjs.md)。 它仅用于传统AppMeasurement，如H代码。

The `s.dynamicAccountList` variable is used to help dynamically determine a report suite to send data to. 它与和变量一 `dynamicAccountSelection` 起使 `dynamicAccountMatch` 用。 The rules in `dynamicAccountList` are applied if `dynamicAccountSelection` is set to `true`, and they apply to the section of the URL specified in `dynamicAccountMatch`.

## 语法和可能值

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

有效输入是以分号分隔的name=value对（规则）列表。 每个列表都包含以下项目：

* 一个或多个报表包ID（以逗号分隔）
* 等号
* 一个或多个URL过滤器（以逗号分隔）

该字符串中只能使用标准的 ASCII 字符（不允许有空格）。

## 示例

对于以下所有示例，页面URL `https://example.com/path2/?prod_id=12345`都是， `dynamicAccountSelection` 变量设置为 `true`，变 `s_account` 量设置为 `examplersid`。

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

* The rules listed in this variable are applied in a left-to-right order. If the `dynamicAccountMatch` variable matches more than one rule, the left-most rule is used to determine the report suite. As a result, place more generic rules to the right of the list.
* If no rules match, the default report suite in `s_account` is used.
* 如果将您的页面保存到某人的硬盘中或通过基于Web的翻译引擎（如Google的翻译页面）进行翻译，则动态帐户选择可能无效。
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.
* 使用 [!DNL Adobe Experience Cloud Debugger] 测试目标报表包。
