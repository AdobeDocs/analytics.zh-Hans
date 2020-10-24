---
title: 退出维度
description: 列出退出维度及其用法。
keywords: exit page, exit site section, exit server, exit custom insight
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---


# 退出维度

*此帮助页介绍退出次数如何作为维度使用。有关退出次数如何作为量度使用的信息，请参阅[退出次数](../metrics/exits.md)量度。*

退出维度记录最后一个维度项目，并将其逆向应用于访问中的所有点击。退出维度可用于在“报表包”设置中的[流量变量](/help/admin/admin/c-traffic-variables/traffic-var.md)下启用路径的所有变量。

## 使用数据填充退出维度

给定的退出维度基于其关联的流量变量。如果非退出变量包含数据，则其关联的退出维度也包含数据。如果流量变量包含数据，则不需要对退出维度进行更改。

## 维度项目

由于退出变量通常基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。给定退出维度中的值与其关联的非退出维度中的维度项目相匹配。例如，“退出页面”维度中的维度项目包含“页面”维度中的类似维度项目。
