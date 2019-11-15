---
description: s_gi() 函数用于按报表包 ID 创建或查找 AppMeasurement 实例。AppMeasurement 会在内部保持跟踪每个创建的实例，s_gi() 会为报表包返回现有实例（如果存在）。如果实例不存在，则会创建一个新实例并返回。
keywords: Analytics Implementation
solution: Analytics
title: s_gi() 函数
topic: Developer and implementation
uuid: a77de90e-c60e-4946-90cf-deaf8aa3d755
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s_gi() 函数

s_gi() 函数用于按报表包 ID 创建或查找 AppMeasurement 实例。AppMeasurement 会在内部保持跟踪每个创建的实例，s_gi() 会为报表包返回现有实例（如果存在）。如果实例不存在，则会创建一个新实例并返回。

我们建议调用 `s_gi()` 后再设置变量并通过页面代码进行跟踪调用。这能确保在 s 变量被无意中被覆盖后也能使用正确的对象跟踪调用。

## 使用多报表包 {#section_F2F3B76E7AFD4B4B91CDC8BBEB34BBC5}

返回的对象会因传递的报表包 ID 而有所不同。例如，如果您对 `s_gi()` () 进行如下的初始调用：

```
var s=s_gi('rsid1,rsid2')
```

下表概述了后续调用所返回的对象：

| **后续调用 s_gi** | **返回对象的描述** |
|---|---|
| `s=s_gi('rsid1,rsid2')` | 早些时候引用的同一对象。 |
| `s=s_gi('rsid1')` | 早期创建的对象的副本，但并非原始对象。 |
| `s=s_gi('rsid1,rsid3')` | 早期创建的对象的副本，但并非原始对象。 |
| `s=s_gi('rsid3')` | 新的空对象，未设置任何配置变量（如 linkTrackVars 和 linkDownloadFileTypes 为空）。 |
