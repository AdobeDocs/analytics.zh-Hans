---
title: dynamicAccountSelection
description: dynamicAccountSelection变量启用或禁用动态帐户选择。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountSelection

> [!IMPORTANT] 动态帐户仅支持使用传统JavaScript实现（H代码）。 当前AppMeasurement库或Adobe Experience Platform Launch不支持这些变量。

变量 `dynamicAccountSelection` 是一个布尔值，它确定是否使用动态帐户选择。

如果设置为 `true`，则JavaScript文件将查看和 `dynamicAccountMatch` 文件 `dynamicAccountList`。

如果设置为 `false`或未定义此变量，则忽略 `dynamicAccountMatch` 和 `dynamicAccountList` 变量。

如果未定义此变量，则默认值为 `false`。

## 语法

```js
s.dynamicAccountSelection = [boolean];
```

## 示例

```js
s.dynamicAccountSelection = true;
```
