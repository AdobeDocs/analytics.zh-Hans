---
title: 退出维度
description: 列出退出维度及其用法。
keywords: 退出页面，退出站点部分，退出服务器，退出客户洞察
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 94%

---

# 退出维度

*此帮助页介绍退出次数如何作为[维度](overview.md)使用。 有关退出次数如何作为指标使用的信息，请参阅[退出次数](../metrics/exits.md)指标。*

退出维度记录最后一个维度项目，并将其逆向应用于访问中的所有点击。退出维度可用于在“报表包”设置中的[流量变量](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)下启用路径的所有变量。

## 使用数据填充退出维度

给定的退出维度基于其关联的流量变量。如果非退出变量包含数据，则其关联的退出维度也包含数据。如果流量变量包含数据，则不需要对退出维度进行更改。

## 维度项目

由于退出变量通常基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。给定退出维度中的值与其关联的非退出维度中的维度项目相匹配。例如，“退出页面”维度中的维度项目包含“页面”维度中的类似维度项目。
