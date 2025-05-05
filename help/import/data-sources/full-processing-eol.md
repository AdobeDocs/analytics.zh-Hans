---
title: 完全处理数据源生命周期结束
description: 详细了解Full Processing Data Sources生命周期结束公告。
exl-id: 7dd6d518-156f-4bf5-86cb-04d0acc8ff0c
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 4%

---

# 完全处理数据源生命周期结束

过去，完全处理数据源使组织能够将点击级别的数据提交到Adobe Analytics。 这些数据的处理方式与通过AppMeasurement等传统数据收集手段收集的数据的处理方式相同。 2020年，Adobe发布了[批量数据插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)，它执行与完全处理数据源相同的功能，但具有附加功能。 本页详细介绍了Bulk Data Insertion API提供的其他功能，并概述了文件格式的差异。

2021年3月25日，Adobe阻止创建新的完全处理数据源连接。 2022年1月31日，所有完全处理数据服务被停用。

## 完全处理数据源与批量数据插入API之间的主要区别

* 批量数据插入允许您提交多个文件以进行并行处理。 访客组可确保访客连续性和eVar归因。
* Bulk Data Insertion具有数据验证和错误处理功能，消除了提交点击数据中的一些管理工作。
* 批量数据插入支持多种访客ID识别方法。
* 批量数据插入有一些额外的必填字段：访客标识列、`pageName`（或等效链接）、`reportSuiteID`、`timestamp`和`userAgent`。
* 为确保访客连续性和归因，批量数据插入要求文件中的行按时间排序。 如需了解跨多个文件对访客活动排序，请参阅[访客组](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/)。
* 批量数据插入要求文件以.gzip格式压缩。
* BDIA使用`timestamp`而不是`date`。

## BDIA和完全处理数据源之间的变量比较

批量数据插入引入了以下变量，这些变量以前在Full Processing Data Sources中不可用：

* **`aamlh`**： Adobe Audience Manager位置提示。
* **`contextData.key`**： [上下文数据变量](/help/implement/vars/page-vars/contextdata.md)。
* **`customerID`**： ID服务变量Experience Cloud。 包括 `id`、`authState` 和 `isMCSeed`。
* **`hints`**： [客户端提示](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=zh-Hans)变量。 包括`bitness`、`brands`、`mobile`、`model`、`platform`、`platformversion`和`wow64`。
* **`ipaddress`**：访客的IP地址。
* **`language`**： [语言](/help/components/dimensions/language.md)维度。
* **`list1`** - **`list3`**： [列表变量](/help/implement/vars/page-vars/list.md)。
* **`marketingCloudVisitorID`**：访客的Experience CloudID。
* **`tnta`**： [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=zh-Hans)集成中使用的Target数据有效负载。
* **`trackingServer`**： [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md)变量。
* **`transactionID`**： [`transactionID`](/help/implement/vars/page-vars/transactionid.md)变量。
* **`userAgent`**：设备的用户代理字符串。

批量数据插入不支持以下变量：

* **`charSet`**： [`charSet`](/help/implement/vars/config-vars/charset.md)变量。 批量数据插入仅支持UTF-8。
* **`timezone`**：访客的时区与GMT的时差（以小时为单位）。
* **`clickAction`**、**`clickActionType`**、**`clickContext`**、**`clickContextType`**、**`clickSourceID`**、**`clickTag`**：Activity Map数据收集中使用的变量。
