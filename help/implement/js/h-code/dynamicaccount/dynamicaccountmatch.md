---
title: dynamicAccountMatch
description: dynamicAccountMatch变量确定在动态帐户中要查看的值。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountMatch

> [!IMPORTANT] 动态帐户仅支持使用传统JavaScript实现（H代码）。 当前AppMeasurement库或Adobe Experience Platform Launch不支持这些变量。

变 `dynamicAccountMatch` 量是查看和比较 `dynamicAccountList` 其值的值。 如果 `dynamicAccountSelection` 未设置为， `true`则忽略此变量。

如果未定义此变量，则其默认值为 `window.location.host`。

## 语法

```js
s.dynamicAccountMatch=[DOM object]
```

## 示例

```js
// Look at the URL path to determine report suite
s.dynamicAccountMatch = location.pathname;

// Use a query string
s.dynamicAccountMatch = location.search;

// Use the full URL
s.dynamicAccountMatch = location.href;

// Use concatenated variables
s.dynamicAccountMatch =  location.hostname + location.pathname + location.search;
```

## 其他说明

* 保存到硬盘的页面没有定义 `location` 多个变量(例如， `location.host` 为空)。 确保包 `s_account` 含默认的报表包。
* 通过基于Web的翻译引擎（如Google）翻译页面时，动态帐户选择无法按设计方式工作。 For more precise tracking, populate the `s_account` variable server-side.
