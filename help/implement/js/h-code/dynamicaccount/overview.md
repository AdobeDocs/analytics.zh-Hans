---
title: 动态帐户概述
description: 了解关于如何使用 H 代码动态选择报表包的工作流。
feature: Implementation Basics
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 100%

---

# 动态帐户概述

>[!IMPORTANT]
>
>仅当使用旧版 JavaScript 实施（H 代码）时，才支持动态帐户。当前的 AppMeasurement 库或 Adobe Experience Platform 中的标记不支持这些变量。

动态帐户是一项实施功能，允许您根据自己定义的条件确定要使用的报表包。如果贵组织需要多个报表包，但希望在各网站之间使用相同的实施，则动态帐户是一个很好的解决方案。

>[!TIP]
>
>Adobe 建议先将数据发送到单个报表包，然后根据需要使用虚拟报表包来分离数据。有关更多信息，请参阅[全局报表包注意事项](../../../prepare/global-rs.md)。

可使用 3 个变量来动态选择报表包。

* [`dynamicAccountSelection`](dynamicaccountselection.md)：启用或禁用动态帐户选择。
* [`dynamicAccountMatch`](dynamicaccountmatch.md)：确定要观察的值。例如，URL 或查询字符串。
* [`dynamicAccountList`](dynamicaccountlist.md)：将值与 `dynamicAccountMatch` 进行比较，如果找到匹配项，则填充 `account` 变量。

如果 `dynamicAccountSelection = true`，则会将 `dynamicAccountMatch` 中的值与 `dynamicAccountList` 进行比较。如果与 `dynamicAccountList` 中的值匹配，则报表包 ID 包含在 `account` 变量中。

## 默认报表包

`account` 变量可最先设置，并在找不到任何指定字符串的情况下充当默认值。例如：

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

如果 `location.hostname` 既不是 `dev.example.com` 也不是 `example.com`，则会将点击发送到 `examplersiddefault`。

## 多包标记

多包标记可以与动态帐户选择一起使用。例如：

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

如果 `location.hostname` 包含 `example.com`，则会将点击同时发送到 `examplersid1` 和 `examplersid2`。
