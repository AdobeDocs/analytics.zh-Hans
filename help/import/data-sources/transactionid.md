---
title: 交易 ID 数据源
description: 使用在线点击中存储的值扩充共享交易ID的离线点击。
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 8%

---

# 交易 ID 数据源

交易ID数据源是汇总数据源的变体，允许您将从在线点击中保存的值应用于共享同一交易ID的离线行。 当您在线捕获事务但稍后从另一个系统接收详细信息时，此方法非常有用。 主要示例包括产品退货、预订取消或呼叫中心交互的结果。

>[!NOTE]
>
>在使用交易ID数据源之前，必须先在所需报表包的[常规帐户设置](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)中启用它。

## 工作原理

交易ID的概念需要两个部分：

* **在线点击**：任何发送到报表包(AppMeasurement、Web SDK、API等)的完整Analytics点击。 在此点击中，您设置了[`transactionID`](/help/implement/vars/page-vars/transactionid.md)实施变量。
* **离线点击**：通过数据源上传的行。 在文件中，包含其值与在线点击匹配的`transactionID`列。

当您发送包含`transactionID`实现变量的在线点击时，Adobe会为当时设置或保留的以下维度生成“快照”：

* [类别](/help/components/dimensions/category.md)
* [首次购买间隔天数](/help/components/dimensions/days-before-first-purchase.md)
* [上次购买间隔天数](/help/components/dimensions/days-since-last-purchase.md)
* [eVar 1-250](/help/components/dimensions/evar.md)
* 在[报表包设置](/help/admin/tools/manage-rs/report-suites-admin.md)中启用的特定功能维度，其行为与eVar类似。 行为与prop相似的特定于特征的维度不包括在内。
* [列表变量](/help/implement/vars/page-vars/list.md)
* [营销渠道](/help/components/dimensions/marketing-channel.md)
* [营销渠道详细信息](/help/components/dimensions/marketing-detail.md)
* [移动设备维度](/help/components/dimensions/mobile-dimensions.md)
* [原始反向链接域](/help/components/dimensions/original-referring-domain.md)
* [产品](/help/components/dimensions/product.md)
* [反向链接域](/help/components/dimensions/referring-domain.md)
* [搜索引擎](/help/components/dimensions/search-engine.md)
* [搜索关键词](/help/components/dimensions/search-keyword.md)
* [跟踪代码](/help/components/dimensions/tracking-code.md)
* [访问量](/help/components/dimensions/visit-number.md)

>[!NOTE]
>
>量度（如[订单](/help/components/metrics/orders.md)或[自定义事件](/help/components/metrics/custom-events.md)）未包含在“快照”中。

当您通过包含匹配交易ID的数据源上载离线点击时，“快照”中的任何可用维度都会自动附加到数据源行。 如果给定的维度同时存在于在线和离线点击中，则会使用离线点击值。

>[!IMPORTANT]
>
>交易ID数据源的概念仅有助于填充数据源行（离线点击）。 它们不会影响或更改在线点击。

## 交易ID数据源注意事项

交易ID数据源具有以下属性：

* 首先要收集和处理在线数据。 如果在报表包处理与该交易ID匹配的点击之前上载了交易ID数据源，则数据将被视为摘要数据源。
* 从在线点击中收集的交易ID将在25个月后过期。
* 使用过期的交易ID上传的数据源的处理方式与没有交易ID上传的数据的处理方式类似。
* 如果在多个在线点击中设置相同的交易ID，则仅使用第一次点击的“快照”。 后续的重复交易ID在线点击会得到处理，就像它们没有交易ID一样。
* 填充给定`transactionID`值后，在该交易ID过期之前，关联的“快照”被视为不可变。
* 如果您在多个数据源行中设置相同的交易ID，则来自在线点击的任何可用维度都会附加到每个离线点击中。 同一交易ID的离线点击彼此之间不了解任何内容；数据不会在离线点击之间传递。
