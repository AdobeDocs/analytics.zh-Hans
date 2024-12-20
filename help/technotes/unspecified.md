---
description: Adobe Analytics 中的各种报表可以显示“未指定”、“无”、“其他”或“未知”，具体视查看的特定报表而定。通常，该行项目意味着变量未定义，或是不可用。
title: 报表中的“未指定”、“无”、“其他”和“未知”
feature: Analytics Basics
exl-id: 35451239-91f3-400a-981e-8c3fbc0e4185
source-git-commit: 0f5890679ea73c1bbea9f5d2939e89c6775c85da
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 96%

---

# 报表中的“未指定”、“无”、“其他”和“未知”

Adobe Analytics 中的各种报表可显示“未指定”、“其他”或“未知”，具体视查看的特定报表而定。通常，该行项目意味着变量未定义，或是不可用。下面详尽地列出了每个报表可以如何包含这些行项目之一。

## 报表中的“未指定”（或“无”） {#reporting}

“未指定”是报表中相当常见的行项目。它也经常被称为“无”。

* **在没有转化变量的情况下触发事件：**&#x200B;例如，用户来到您的网站并购买商品，但没有任何 eVar1 值。如果您使用 eVar1 维度查看订单，则没有此订单的归因值。因此，该订单会被自动归因于“未指定”。
* **分类报表中存在未分类的数据：**&#x200B;在查看分类数据时，任何没有数据与该特定分类相关联的值都会返回“未指定”。要解决此问题，请确保每个父维度项目都有一个关联的分类值。
* **仅触发一个变量的划分报表：**&#x200B;将划分应用于变量时，必须考虑该变量的每个实例。如果没有看到第二个变量，或者该变量在上一个点击后持续保留，则维度项目为“未指定”。
* **移动设备报表中的非移动设备点击：**&#x200B;移动设备报表中的任何非移动设备点击都会列为“未指定”（Reports and Analytics 中为“非移动”）。

## 报表中的“其他” {#other}

尽管“其他”在报表中稍微少见，但在几种情况下，还是会出现。

* **页面在内部 URL 过滤器之外触发：**&#x200B;该值旨在帮助防止数据欺诈，例如，如果其他组织窃取您的源代码并在其自己的网站进行实施。要更正此问题，请确保您实施代码的所有 URL 与您在报表包中设置的内部 URL 过滤器相匹配。
* **访客使用不常用的浏览器：**&#x200B;如果访客使用的浏览器类型不常用，则在浏览器类型报表中将显示“其他”作为划分。有很多组织都在开发浏览器。大型组织未创建的所有浏览器都会存储到“其他”中，以防止报表混乱。

## 报表中的“未知” {#unknown}

在几种情况下会出现“未知”：

* **查看技术报表时的非浏览器点击：**&#x200B;如果 AppMeasurement 库无法确定是否支持某个功能，则报表中将显示“未知”。
* **使用其中组件无法访问的区段：**&#x200B;确保已启用区段中使用的变量，并且允许用户进行访问。如果用户无权访问区段组件，或者禁用了变量，则显示“未知”。

## 在报表中过滤这些值 {#filter}

在大多数情况下，可以忽略这些行项目，这不会出现问题。如果需要，可以使用搜索过滤器删除这些行项目。

尽管未在界面中显示，但有些后端数据变量会在报表中使用值 `::unspecified::`。如果搜索过滤器无法排除数据，请尝试使用此值（包括冒号）。
