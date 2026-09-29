---
title: 数据保留策略
description: 数据保留策略确定 Adobe 将您的数据存储多长时间。
exl-id: f3bb02d2-380d-4eb7-8449-e0318fc8c0a6
feature: Data Governance
TQID: 'https://experienceleague.adobe.com/ymM-0bethfijutq5sprEuEfOFgw3Xn4gTsLNNgKTEio'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f7fb4c71-5c39-4655-ba2d-b3b189287ab7
    internal-label: Data governance
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 92%
---
# 数据保留策略

由 Adobe Analytics 收集的数据将保留特定的一段时间。 Adobe 保留此数据的时间因合同而异，在组织的数据保留策略中进行了概述。 此策略适用于数据本身，这意味着该策略会影响所有 Analytics 报表功能（Analysis Workspace、报告 API 等）。

**Adobe Analytics的默认数据保留策略为25个月。** 贵组织的保留策略可能因合同而异。

保留的数据基于当前日期和历史数据的日期/时间。 点击时记录的日期/时间可能与 Adobe 收到点击的日期/时间不同。

## 调整默认数据保留期限

如果您希望缩短或延长默认数据保留期限，请联系您的 Adobe 帐户团队。

* 缩短默认数据保留期限不收取任何费用。
* 如果延长数据保留期限超出 25 个月的默认保留期限，则需要购买延长时间，每次购买可延长一年。 最多可购买 8 次延长，共 10 年 1 个月（默认保留期为 2 年 1 个月，另购买 8 年）。

## 数据保留和数据隐私

Adobe 作为您的数据处理者，必须采取适当措施协助其客户实现个人访问、删除和其他请求。 运用适当、安全和及时的删除策略是履行此项职责的重要部分。 GDPR 适用于以欧盟公民为营销对象或处理欧盟公民相关信息的所有客户。 CCPA 适用于以加利福尼亚公民为营销对象或处理加利福尼亚公民相关信息的所有客户。 因此，数据隐私是一个全球范围的法规变动。

## 数据删除

一旦数据超出您的数据保留策略，Adobe 保留删除这些数据的权利，且不提供恢复选项。 您必须确保要保留的所有数据都涵盖在贵组织的数据保留策略中。

## 查看/管理当前数据保留策略

[!UICONTROL Admin] 工具中的“数据治理”对话框概述了为数据治理配置了哪些报表包。 它还指示它们是否已映射到CX Enterprise组织，以及是否为此报表包制定了数据保留策略。

## 常见问题解答

+++ 如何确定我的组织的数据保留期限？

作为数据控制者，您的公司可以确定贵组织内负责制定数据保留相关决策的利益干系人，如营销、分析和隐私团队。 贵组织最适合判断 Adobe Analytics 保留数据的适当期限。

+++

+++ 如何计算数据保留窗口？

数据保留策略定义了一个滚动的数据保留窗口，在此窗口内可以查看和报告完整数据。 数据保留开始日期由当前日期减去数据保留期确定。 数据保留结束日期由当前日期确定。 如果数据的时间戳介于开始日期和结束日期之间，则该数据包含在数据保留窗口内。

+++

+++ 我可以在删除之前请求一份数据副本吗？

是的。 Adobe 可以提供点击级别原始数据的历史数据转储。 有关更多信息，请参阅导出用户指南中的[数据馈送](/help/export/analytics-data-feed/data-feed-overview.md)。 如果您的数据导出要求超出 UI 可提供的范围，请联系 Adobe 帐户团队。 可以做出特殊调整；成本可能会有所不同。

+++

+++ Adobe 何时删除数据？

有关计划删除数据的具体时间，请与您的 Adobe 帐户团队联系。 通常会每月滚动删除数据。

+++

