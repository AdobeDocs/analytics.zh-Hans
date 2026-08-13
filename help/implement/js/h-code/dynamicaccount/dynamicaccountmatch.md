---
title: dynamicAccountMatch
description: dynamicAccountMatch 变量确定在动态帐户中要查看的值。
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
role: Developer
TQID: https://experienceleague.adobe.com/Ag4YQOjHPMRsktGSbzpErM55lVCydDHXfNiS4HJofIU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 129
ht-degree: 100%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>仅当使用旧版 JavaScript 实施（H 代码）时，才支持动态帐户。 当前的 AppMeasurement 库或 Adobe Experience Platform 中的标记不支持这些变量。

`dynamicAccountMatch` 变量值由 `dynamicAccountList` 进行检查和与其值进行比较。 如果 `dynamicAccountSelection` 未设置为 `true`，则忽略此变量。

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

* 保存到硬盘的页面不会定义任何 `location` 变量（例如，`location.host` 为空）。 确保 `s_account` 包含默认的报表包。
* 在页面通过基于 Web 的翻译引擎（如 Google）进行了翻译时，动态帐户选择无法按预期使用。 如需更精确的跟踪，请通过服务器端填充 `s_account` 变量。
