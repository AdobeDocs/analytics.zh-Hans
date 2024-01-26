---
title: dynamicAccountSelection
description: dynamicAccountSelection 变量可启用或禁用动态帐户选择。
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 82%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>仅当使用旧版 JavaScript 实施（H 代码）时，才支持动态帐户。当前的AppMeasurement库或Adobe Experience Platform数据收集不支持这些变量。

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
