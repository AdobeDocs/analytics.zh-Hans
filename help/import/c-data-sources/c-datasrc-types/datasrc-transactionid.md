---
title: 交易 ID 数据源
description: 了解使用交易 ID 数据源的一般工作流程。
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 100%

---

# 交易 ID 数据源

通过交易 ID 数据源，您不仅可以并排查看在线和离线数据，还可以将数据绑定在一起。它需要在您的 Analytics 实施中使用 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 变量。

当您发送包含 `transactionID` 值的在线点击时，Adobe 会为当时设置或保留的所有变量生成“快照”。如果发现通过数据源上传了匹配的交易 ID，则离线数据和在线数据即建立关联。

要使用交易，必须已传入并处理具有某个交易 ID 的在线点击，然后再传入任何具有该交易 ID 的交易数据源数据。在线点击包含变量（eVar 等），而不包含在线点击上与交易 ID 信息一起保存的事件。

当传入了交易数据源点击时，数据源交易点击上的交易 ID 即查找与具有该交易 ID 的原始在线点击关联的变量等（而非事件）。如果在数据源交易点击上未传入变量的值，则它在数据源交易点击上使用这些变量。

## 示例

如果传入了交易 ID 为 1256 的在线点击，并在它上面设置了 `evar1=blue`、`evar2=water` 和 `event1`，则与 `evar1=blue`、`evar2=water` 一起保存交易 ID 1256 的交易数据。没有事件值保存为交易信息的一部分。

现在，假设随后通过系统传递一个交易 ID 为 1256 并设置了 `evar1=yellow`、`evar3=mountain` 和 `event2` 的数据源交易点击。系统查找已保存的交易数据，并在该数据源交易点击中设置 `evar2=water`（因为这是在原始点击上设置的内容）。由于已在数据源交易点击上设置了 `evar1` 的值（黄色），因此不设置 `evar1=blue`（因为它曾在原始点击上）。于是，该数据源交易点击的结果是具有 `evar1=yellow`、`evar2=water`（来自原始在线点击）和 `evar3=mountain`。这 3 个 eVar 值设置了 `event2` — 来自该数据源交易点击的事件。

当处理该数据源交易点击时，没有来自该数据源交易点击的值设置了 `event1`。

## 交易 ID 数据源的整个工作流程

通过以下通用工作流程来开始使用交易 ID 数据源：

1. 创建数据源（“通用”类别和“通用数据源（交易 ID）”类型）。
1. 按数据源设置向导获取一个 FTP 位置以上传数据和下载数据源模板文件。
1. 更新您的实施以包含该 `transactionID` 变量。
1. 将数据源文件上传到包含 `.fin` 文件的 FTP 站点。

## 上传文件和实现代码示例

如果您上传了以下数据源文件，并在您的站点上实现了下列代码，您会在报表中看到链接的数据。数据源文件使用 eVar1 和 event1，而联机实现使用 eVar2 和 event2。由于交易 ID 匹配，因此您可以看到 eVar1 的 event2 数据和 eVar2 的 event1 数据。

### 示例文件

下载模板、更新值，然后将其上传到数据源 FTP 位置：

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
