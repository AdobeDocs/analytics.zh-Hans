---
title: 交易 ID 数据源
description: 了解使用交易 ID 数据源的一般工作流程。
translation-type: ht
source-git-commit: c6f84f470dcf97f49ce7dc9d2c5dd8c65cc6cf67
workflow-type: ht
source-wordcount: '270'
ht-degree: 100%

---


# 交易 ID 数据源

通过交易 ID 数据源，您不仅可以并排查看在线和离线数据，还可以将数据绑定在一起。它需要在您的 Analytics 实施中使用 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 变量。

当您发送包含 `transactionID` 值的在线点击时，Adobe 会为当时设置或保留的所有变量生成“快照”。如果找到通过数据源上载的匹配交易 ID，则会将在线和离线数据绑定在一起。先看到哪个数据源并不重要。

## 交易 ID 数据源的整个工作流程

通过以下通用工作流程来开始使用交易 ID 数据源：

1. 创建数据源（“通用”类别和“通用数据源（交易 ID）”类型）。
1. 按照数据源设置向导获取 FTP 位置，从而上载数据并下载数据源模板文件。
1. 更新您的实施以包含该 `transactionID` 变量。
1. 将数据源文件上载到包含 `.fin` 文件的 FTP 站点。

## 上载文件和实现代码示例

如果您上载了以下数据源文件，并在您的站点上实现了下列代码，您会在报表中看到链接的数据。数据源文件使用 eVar1 和 event1，而联机实现使用 eVar2 和 event2。由于交易 ID 匹配，因此您可以看到 eVar1 的 event2 数据和 eVar2 的 event1 数据。

### 示例文件

下载模板、更新值，然后将其上载到数据源 FTP 位置：

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### 实施代码示例

有关交易 ID 的更多详细说明，请参阅实施用户指南中的 [`transactionID`](/help/implement/vars/page-vars/transactionid.md)。

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
