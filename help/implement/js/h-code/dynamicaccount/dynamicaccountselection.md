---
title: dynamicAccountSelection
description: dynamicAccountSelection 变量可启用或禁用动态帐户选择。
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
TQID: https://experienceleague.adobe.com/tne4K1ppeYbWGckTmuJy0f8Bjdw9WvGbjrOSKs4RXlk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 86
ht-degree: 82%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>仅当使用旧版 JavaScript 实施（H 代码）时，才支持动态帐户。 当前的AppMeasurement库或Adobe Experience Platform数据收集不支持这些变量。

`dynamicAccountSelection` 变量是一个布尔值，可确定是否使用动态帐户选择。

如果将此变量设置为 `true`，则 JavaScript 文件将会检查 `dynamicAccountMatch` 和 `dynamicAccountList`。

如果将此变量设置为 `false` 或未定义此变量，则将忽略 `dynamicAccountMatch` 和 `dynamicAccountList` 变量。

如果未定义此变量，则其默认值为 `false`。

## 语法

```js
s.dynamicAccountSelection = [boolean];
```

## 示例

```js
s.dynamicAccountSelection = true;
```
