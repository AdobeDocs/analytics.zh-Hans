---
title: 交易 ID 数据源
description: 了解使用交易 ID 数据源的一般工作流程。
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 7%

---

# 交易 ID 数据源

交易ID数据源是汇总数据源的变体，允许您将在线和离线数据绑定在一起。 它需要在您的 Analytics 实施中使用 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 变量。

* 如果数据源文件中的行包含与AppMeasurement已收集的交易ID匹配的交易ID，则维度和量度将附加到在线点击中。
* 如果数据源文件中的某行包含不含匹配项的交易ID，则该行的处理方式与汇总数据源类似。

>[!NOTE]
>
>在使用交易ID数据源之前，必须先在中启用它 [一般帐户设置](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) （对于所需的报表包）。

当您发送包含 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 值，Adobe会为当时设置或保留的所有变量生成“快照”。 如果找到通过数据源上传的匹配交易ID，则离线数据和在线数据即建立关联。

交易ID数据源具有以下属性：

* 首先要收集和处理在线数据。 如果在报表包处理与该交易ID匹配的点击之前上载了交易ID数据源，则不会链接该数据。
* 通过AppMeasurement收集的交易ID将在大约90天后过期。 如果您的组织需要更长的交易ID窗口，请联系Adobe客户关怀团队。
* 使用过期的交易ID上传的数据源的处理方式与没有交易ID上传的数据的处理方式类似。
* 如果在线点击和交易ID数据源中均包含相同变量，则使用交易ID数据源中的值。
* 如果某个变量包含在在线点击中，但不包含在匹配的交易ID数据源点击中，则将保留在线点击变量。
* 如果在多个在线点击中设置相同的交易ID，则只有第一次发生事件会使用来自匹配交易ID数据源的数据进行更改。
* 如果在同一维的多个数据源行上设置相同的交易ID，则会使用最新的维度项。

例如：

1. 从AppMeasurement发送页面查看，其中：
   * `eVar1` 等于 `blue`
   * `eVar2` 等于 `water`
   * `events` 等于 `event1`
   * `transactionID` 等于 `1256`
2. 收集并处理点击后，您可以上传交易ID数据源，其中：
   * `eVar1` 等于 `yellow`
   * `eVar3` 等于 `bird`
   * `events` 等于 `event2`
   * `transactionID` 等于 `1256`
3. 处理数据源点击后，即可在工作区中查看报表。 数据将显示以下内容：
   * `eVar1` 等于 `yellow`
   * `eVar2` 等于 `water`
   * `eVar3` 等于 `bird`
   * `events` 等于 `event2`

eVar1值 `blue` 和 `event1` 量度在报表中不存在，因为交易ID点击会覆盖这些相应的值。
