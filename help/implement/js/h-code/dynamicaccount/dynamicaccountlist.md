---
title: dynamicAccountList
description: 构建有关实施如何确定其报表包的逻辑。
feature: Implementation Basics
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 94%

---

# s.dynamicAccountList

>[!IMPORTANT]
>
>仅当使用旧版 JavaScript 实施（H 代码）时，才支持动态帐户。当前的AppMeasurement库或Adobe Experience Platform数据收集不支持这些变量。

`s.dynamicAccountList` 变量可动态确定 `s_account` 的值。如果将 `dynamicAccountSelection` 设置为 `true`，则会将 `dynamicAccountMatch` 变量与 `dynamicAccountList` 进行比较。如果找到匹配项，则使用匹配的报表包 ID。

## 语法

此变量是一个字符串，将由 JavaScript 文件自动解析。

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

有效输入是以分号分隔的 rsid 和值对列表。每个列表都包含以下项目：

* 一个或多个报表包 ID（以逗号分隔）
* 一个等号
* 要匹配的一个或多个字符串（以逗号分隔）

该字符串中只能使用标准的 ASCII 字符。不允许包含空格。

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
