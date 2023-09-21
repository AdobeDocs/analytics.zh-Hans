---
title: 登入维度
description: 列出登入维度及其使用情况。
keywords: 登入页面，登入网站区域，登入服务器，登入自定义见解
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 89%

---

# 登入维度

*此帮助页介绍登入次数如何作为 [维度](overview.md). 有关登入次数如何作为量度使用的信息，请参阅[登入次数](../metrics/entries.md)量度。*

登入维度为 [基于访问](../metrics/visits.md). 它们记录第一个维度项目，并在该访问的整个过程中保留该值。登入维度可用于在“报表包”设置中的[流量变量](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)下启用路径的所有变量。

## 使用数据填充登入维度

给定条目 [维度](overview.md) 基于其关联的流量变量。 如果非登入变量包含数据，则其关联的登入维度也包含数据。如果流量变量包含数据，则不需要对登入维度进行更改。

## 维度项目

由于登入变量通常基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。给定登入维度中的值与其关联的非登入维度中的维度项目相匹配。例如，“登入页面”维度中的维度项目包含“页面”维度中的类似维度项目。

## 原始登入页面

“原始登入页面”维度的操作方式与其他登入维度不同。它不保留给定访问的登入页面，而是保留该访客 Cookie 的整个生命周期中的第一个登入页面。例如，如果您登陆 `https://example.com/page4` 首次访问该网站，一年后登陆 `https://example.com/store` 时，“原始登入页面”维度会将 `https://example.com/page4` 列为维度项目。
