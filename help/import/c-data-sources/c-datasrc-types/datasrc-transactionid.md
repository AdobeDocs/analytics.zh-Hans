---
title: 交易 ID 数据源
description: 了解使用交易 ID 数据源的一般工作流程。
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 45%

---

# 交易 ID 数据源

通过交易 ID 数据源，您不仅可以并排查看在线和离线数据，还可以将数据绑定在一起。它需要在您的 Analytics 实施中使用 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 变量。

当您发送包含 `transactionID` 值的在线点击时，Adobe 会为当时设置或保留的所有变量生成“快照”。如果找到通过数据源上载的匹配交易 ID，则会将在线和离线数据绑定在一起。

对于使用交易，必须先发送并处理具有交易ID的在线点击，然后再发送具有该交易ID的任何交易数据源数据。 在线点击包含随交易ID信息保存的在线点击中的变量（eVar等），但不包含事件。

在发送交易数据源点击时，数据源交易点击的交易ID会查找var等。 与原始在线点击与该交易ID关联的（非事件）。 如果数据源交易点击中传递的变量没有值，则它会在数据源交易点击中使用这些变量。

## 示例

如果在其上传递了交易ID为1256的在线点击 `evar1=blue`, `evar2=water` 和 `event1` 设置，则交易ID 1256的交易数据保存为 `evar1=blue`, `evar2=water`. 事务信息中不保存任何事件值。

现在，假设数据源交易点击随后通过交易ID为1256和 `evar1=yellow`, `evar3=mountain` 和 `event2` 设置。 系统在数据源事务点击集中查找保存的事务数据和 `evar2=water` （因为这是在原始点击中设置的内容）。 未设置 `evar1=blue` （与在原始点击时一样），因为 `evar1` （黄色）已在数据源交易点击中设置。  因此，数据源交易点击会导致 `evar1=yellow`, `evar2=water` （来自原始在线点击）和 `evar3=mountain`. 这3个eVar值具有 `event2` set — 数据源交易点击中的事件。

没有来自数据源交易点击的值 `event1` 在处理数据源交易点击时设置。

## 交易 ID 数据源的整个工作流程

通过以下通用工作流程来开始使用交易 ID 数据源：

1. 创建数据源（“通用”类别和“通用数据源（交易 ID）”类型）。
1. 按照数据源设置向导获取FTP位置，以上载数据并下载数据源模板文件。
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
