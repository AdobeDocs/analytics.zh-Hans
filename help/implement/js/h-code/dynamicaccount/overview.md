---
title: 动态帐户概述
description: 了解如何使用H代码动态选择报表包的工作流。
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# 动态帐户概述

> [!IMPORTANT] 动态帐户仅支持使用传统JavaScript实现（H代码）。 当前AppMeasurement库或Adobe Experience Platform Launch不支持这些变量。

动态帐户是一项实施功能，它允许您根据您定义的条件确定要使用的报表包。 如果您的组织需要多个报表包，但希望在您的站点之间使用相同的实施，则动态帐户是一个不错的解决方案。

> [!TIP] Adobe建议将数据发送到单个报表包，然后根据需要使用虚拟报表包来分离数据。 有关更 [多信息，请参阅全局报表包注意事项](../../../prepare/global-rs.md) 。

3个变量用于动态选择报表包。

* [`dynamicAccountSelection`](dynamicaccountselection.md):启用或禁用动态帐户选择。
* [`dynamicAccountMatch`](dynamicaccountmatch.md):确定要观察的值。 例如，URL或查询字符串。
* [`dynamicAccountList`](dynamicaccountlist.md):将值与进行比 `dynamicAccountMatch`较，如果找到匹配项，则填充该 `account` 变量。

如 `dynamicAccountSelection = true`果，则比较 `dynamicAccountMatch` 其中的值 `dynamicAccountList`。 如果值匹配， `dynamicAccountList` 则报表包ID将包含在变量 `account` 中。

## 默认报告套件

`account` 变量可最先设置，并在找不到任何指定字符串的情况下充当默认值。例如：

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

如果 `location.hostname` 不是 `dev.example.com` 或 `example.com`者，则攻击将发送到 `examplersiddefault`。

## 多包标记

多套件标记可以与动态帐户选择一起使用。 例如：

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

如果 `location.hostname` 包 `example.com`含，则点击将同时发送到 `examplersid1` 和 `examplersid2`。
