---
title: 交易ID数据源
description: 了解使用交易ID数据源的一般工作流程。
translation-type: tm+mt
source-git-commit: a5c3d9b2cd02dc7e89abb469e2e0e44985a17638

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
