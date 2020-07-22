---
title: 退出尺寸
description: 列表退出尺寸及其使用。
keywords: exit page, exit site section, exit server, exit custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---


# 退出尺寸

*此帮助页面描述退出如何以维的形式工作。 有关退出如何作为度量的信息，请参阅退出[度量](../metrics/exits.md)。*

退出维记录最后一个维项，并逆向将其应用于访问中的所有点击。 退出维度适用于在“报表包”设置中的“流量变量”下启 [用寻路](/help/admin/admin/c-traffic-variables/traffic-var.md) 的所有变量。

## 用数据填充退出维

给定的退出维度基于其关联的流量变量。 如果非退出变量包含数据，则其关联的退出维也包含数据。 如果流量变量包含数据，则退出维度不需要实施更改。

## 维项

由于退出变量通常基于实施中的自定义字符串，因此您的组织将决定维项是什么。 给定退出维中的值与其关联的非退出维中的维项匹配。 例如，“退出页面”维中的维项目包含“页面”维中的类似维项目。
