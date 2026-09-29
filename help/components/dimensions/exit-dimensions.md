---
title: 退出维度
description: 列出退出维度及其用法。
keywords: 退出页面，退出站点部分，退出服务器，退出客户洞察
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
TQID: 'https://experienceleague.adobe.com/YRjvhW8OzBlip9ok0-1D4rYSljkccpIAlDkqCQv7nyo'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 74%
---
# 退出维度

>[!BEGINSHADEBOX]

*此帮助页介绍退出次数如何作为[维度](overview.md)使用。 有关退出次数如何作为指标使用的信息，请参阅[退出次数](../metrics/exits.md)指标。*

>[!ENDSHADEBOX]

退出维度记录最后一个维度项，并将其追溯应用于访问中的所有点击。 退出维度可用于在“报表包”设置中的[流量变量](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)下启用路径的所有变量。

## 使用数据填充退出维度

给定的退出维度基于其关联的流量变量。 Adobe从访问期间为该变量显示的最后一个值派生每个退出维度；没有要设置的专用变量。 如果非退出变量包含数据，则其关联的退出维度也包含数据。 如果流量变量包含数据，则不需要对退出维度进行更改。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（派生自访客的上次点击） |
| **Web SDK / XDM字段** | 无（派生自访客的上次点击） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 访问 |

## 维度项目

由于退出变量通常基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。 给定退出维度中的值与其关联的非退出维度中的维度项目相匹配。 例如，“退出页面”维度中的维度项与“页面”维度中的类似维度项相对应。
