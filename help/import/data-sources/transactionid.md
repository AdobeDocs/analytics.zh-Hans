---
title: 交易 ID 数据源
description: 了解使用交易 ID 数据源的一般工作流程。
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 54c88a275b48f2b401be450ce35767ab3ea9d40b
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 10%

---

# 交易 ID 数据源

交易ID数据源是概要数据源上的一个变体，允许您将在线和离线数据绑定在一起。 它需要在您的 Analytics 实施中使用 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 变量。

* 如果数据源文件中的某行包含与AppMeasurement已收集的交易ID相匹配的交易ID，则维度和量度将附加到在线点击中。
* 如果数据源文件中的某行包含不包含匹配项的交易ID，则该行的处理方式与概要数据源类似。

>[!NOTE]
>
>在使用交易ID数据源之前，必须先在 [一般帐户设置](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) 的双曲正切值。

当您发送包含 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 值时，Adobe会生成随后设置或保留的所有变量的“快照”。 如果找到通过数据源上传的匹配交易ID，则离线和在线数据会绑定在一起。

交易ID数据源具有以下属性：

* 必须先收集和处理在线数据。 如果在报表包处理与交易ID匹配的点击之前上传了交易ID数据源，则不会关联该数据。
* 通过AppMeasurement收集的交易ID在大约90天后过期。 如果贵组织需要较长的交易ID窗口，请联系Adobe客户关怀团队。
* 上载有过期交易ID的数据源的处理方式与上载没有交易ID的数据的处理方式类似。
* 如果在线点击和交易ID数据源中都包含相同的变量，则会使用交易ID数据源中的值。
* 如果某个变量包含在联机点击中，但未包含在匹配的交易ID数据源点击中，则会保留联机点击变量。
* 如果在多个在线点击中设置相同的交易ID，则仅使用来自匹配交易ID数据源的数据更改第一个事件。
* 如果对同一维度的多个数据源行设置相同的交易ID，则会使用最新的维度项目。

例如：

1. 您从AppMeasurement发送页面查看，其中：
   * `eVar1` 等于 `blue`
   * `eVar2` 等于 `water`
   * `events` 等于 `event1`
   * `transactionID` 等于 `1256`
2. 收集和处理点击后，您可以上传交易ID数据源，其中：
   * `eVar1` 等于 `yellow`
   * `eVar3` 等于 `bird`
   * `events` 等于 `event2`
   * `transactionID` 等于 `1256`
3. 处理数据源点击后，即可在工作区中查看报表。 数据将显示以下内容：
   * `eVar1` 等于 `yellow`
   * `eVar2` 等于 `water`
   * `eVar3` 等于 `bird`
   * `events` 等于 `event2`

eVar1值 `blue` 和 `event1` 量度在报表中不存在，因为交易ID点击覆盖了这些值。
