---
description: 此集成将 Qualtrics Research Suite 的客户研究功能与您在 Adobe Analytics 中收集的丰富数据整合在一起，为贵组织提供强大的分析和优化契机。
subtopic: Qualtrics
title: 适用于 Adobe Analytics 的 Qualtrics Data Connector
feature: Data Connectors
uuid: f1fa90b6-1b80-4da4-a39b-efb8bac1692a
exl-id: 5c1234b1-bca8-4e7a-981e-1379e88821b8
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 96%

---

# 适用于 Adobe Analytics 的 Qualtrics Data Connector{#qualtrics-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>我们将于2021年8月1日终止Adobe Data Connector技术。 [了解详情...](/help/import/data-connectors/data-connectors-eol.md)

此集成将 Qualtrics Research Suite 的客户研究功能与您在 Adobe Analytics 中收集的丰富数据整合在一起，为贵组织提供强大的分析和优化契机。

这种双向集成先将 Qualtrics 调查响应数据与访客点击流数据相关联。然后，再将相关的行为操作和属性从 Adobe Analytics 注入回 Qualtrics 调查报表。

## 主要优势和功能{#key-benefits-and-features}

* 根据用户对特定调查问题的响应构建用户区段。
* 根据调查级别、问题级别和响应级别的详细信息，提供流量和转化报表。
* 仅使用 1 个 ListVar、1 个 eVar 和 1 个事件来集成不限数量的 Qualtrics 调查。
* 使用 Adobe Analytics 跟踪的最多 5 个自定义转化维度、5 个自定义流量维度、5 个自定义成功事件以及 20 多个其他标准量度和维度增强 Qualtrics 报表。
* 在提交调查时，Adobe Analytics 中的集成调查数据会以“实时”方式流动。每天均会导出到 Qualtrics。

## 在激活此连接器之前{#before-you-activate-this-connector}

### Adobe 先决条件 {#section-fd37a66150c34cd6b494d13f75e5fb0d}

* 必须是 Adobe Analytics 的当前客户。
* 必须是管理员用户。
* 您的报表包中必须具有 1 个已启用的可用列表变量。
* 您的报表包中必须具有 1 个已启用的可用 eVar（或 prop）变量。
* 您的报表包中必须具有 1 个可用的自定义事件。

### Qualtrics 先决条件 {#section-dbb780af47c145d7b6ae12acde3ca94c}

* 必须是 Qualtrics Research Suite 的当前客户。
* 必须是有权启用 Adobe Analytics 集成的用户。
* 必须能够在 Research Suite 的 **[!UICONTROL Qualtrics ID]** 区域内生成 Adobe Analytics 令牌。
