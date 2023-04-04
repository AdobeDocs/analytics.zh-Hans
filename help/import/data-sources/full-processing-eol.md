---
title: 完全处理数据源的生命周期终止
description: 进一步了解用于完全处理数据源的生命周期终止公告。
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 9%

---

# 完全处理数据源的生命周期终止

完全处理数据源过去允许组织向Adobe Analytics提交点击级别的数据。 此数据的处理方式与通过传统数据收集方法（如AppMeasurement）收集的数据相同。 2020年，Adobe发布了 [批量数据插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)，其功能与完全处理数据源相同，但具有其他功能。 本页提供了有关批量数据插入API提供的其他功能的详细信息，并概述了文件格式的差异。

2021年3月25日，Adobe阻止创建新的完全处理数据源连接。 2022年1月31日，所有完全处理数据服务都被停用。

## 完全处理数据源与批量数据插入API之间的主要区别

* 批量数据插入允许您提交多个文件以进行并行处理。 访客组可确保访客连续性和eVar归因。
* 批量数据插入具有数据验证和错误处理功能，从而消除了提交点击数据的一些管理工作。
* 批量数据插入支持多种访客ID识别方法。
* 批量数据插入包含一些其他必填字段：访客识别列， `pageName` （或等效链接）、 `reportSuiteID`, `timestamp`和 `userAgent`.
* 为确保访客连续性和归因，批量数据插入要求按时间顺序对文件中的行进行排序。 如需了解跨多个文件对访客活动排序，请参阅[访客组](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/)。
* 批量数据插入要求文件以.gzip格式进行.csv压缩。
* BDIA用法 `timestamp` 而不是 `date`.

## BDIA与完全处理数据源之间的变量比较

以下变量已引入批量数据插入，以前在完全处理数据源中不可用：

* **`aamlh`**:Adobe Audience Manager位置提示。
* **`contextData.key`**: [上下文数据变量](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**:Experience CloudID服务变量。 包括 `id`、`authState` 和 `isMCSeed`。
* **`hints`**: [客户端提示](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html) 变量。 包括 `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion`和 `wow64`.
* **`ipaddress`**:访客的IP地址。
* **`language`**:的 [语言](/help/components/dimensions/language.md) 维度。
* **`list1`** - **`list3`**: [列表变量](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**:访客的Experience CloudID。
* **`tnta`**:在中使用的Target数据有效负载 [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html) 集成。
* **`trackingServer`**:的 [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) 变量。
* **`transactionID`**:的 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 变量。
* **`userAgent`**:设备的用户代理字符串。

通过批量数据插入，不支持以下变量：

* **`charSet`**:的 [`charSet`](/help/implement/vars/config-vars/charset.md) 变量。 批量数据插入仅支持UTF-8。
* **`timezone`**:访客的时区与GMT的时区（以小时为单位）偏移。
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**:用于Activity Map数据收集的变量。
