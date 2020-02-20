---
title: 交易ID数据源
description: 了解使用交易ID数据源的一般工作流程。
translation-type: tm+mt
source-git-commit: c6f84f470dcf97f49ce7dc9d2c5dd8c65cc6cf67

---


# 交易ID数据源

交易ID数据源不仅允许您并排查看线上和线下数据，还可以将数据绑定在一起。 它需要在Analytics实施 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 中使用变量。

当您发送包含值的在线点击时， `transactionID` Adobe会对当时设置或保留的所有变量进行“快照”。 如果找到通过数据源上传的匹配事务ID，则脱机和联机数据会绑定在一起。 首先看到哪个数据源并不重要。

## 交易ID数据源的整个工作流

使用以下通用工作流可开始使用事务ID数据源：

1. 创建数据源(“通用”类别和“通用数据源（事务ID）”类型)。
1. 按照数据源设置向导进行操作，以获取一个FTP位置以上传数据并下载数据源模板文件。
1. 更新您的实施以包含该 `transactionID` 变量。
1. 将数据源文件与文件一起上传到FTP站 `.fin` 点。

## 上传文件和实施代码示例

如果您上传了以下数据源文件，并在您的站点上实施了以下代码，您会在报告中看到链接的数据。 数据源文件使用eVar1和event1，而联机实现使用eVar2和event2。 由于事务ID匹配，因此您可以看到eVar1的event2数据和eVar2的event1数据。

### 示例文件

下载模板，更新值，然后将其上传到数据源FTP位置：

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### 示例实施代码

有关事务ID的更详细说明，请参阅 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 《实施用户指南》中的“。

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
