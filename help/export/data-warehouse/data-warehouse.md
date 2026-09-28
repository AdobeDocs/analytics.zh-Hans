---
description: 了解 Data Warehouse 以及如何筛选数据，使您能创建和运行自定义报告。
title: Data Warehouse 概述
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
TQID: 'https://experienceleague.adobe.com/Vkn9mWvBzaiIBf1KYIEUK8cRwTuzw41MT-v-thMBg38'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: e3e906cf-5493-4e0a-9a33-bf0ac37393d6
    internal-label: Custom reports
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f47edbe0-f963-46ff-a667-71011396f5f3
    internal-label: Data Warehouse
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 86%
---
# Data Warehouse 概述

Data Warehouse 可让您复制 Adobe Analytics 数据以用于存储和创建自定义报表，可以通过筛选数据来运行这些报表。

## 报表概述

Data Warehouse 报表可以根据独特的问题显示高级数据与原始数据的关系。 它们可以在单个请求中包含无限数量的行（针对单个报表、计划报表和已下载报表）。

>[!NOTE]
>
>Data Warehouse 会显示在报告时段遇到的第一个值。

>[!IMPORTANT]
>
>在对分类的值进行分段时，Analysis Workspace 和 Data Warehouse 处理“未指定”值的方式有所不同。 工作区中的“未指定”是指未分类的值，而 Data Warehouse 中的“未指定”是指您分类为“未指定”的值。

## 投放概述

Data Warehouse 报告会通过电子邮件发送或发送到云存储提供商，处理时间最长可达 72 小时。 处理时间取决于查询的复杂程度和请求的数据量。

Data Warehouse 会自动将任何大小超过 1 MB 的文件压缩为 zip 包。 电子邮件附件的最大大小为 10 MB。

## 访问

对于特定的报表包，Adobe 仅为管理员级别的用户启用 Data Warehouse。 （它可以为全局报表包和子报表包启用，但不能为汇总报表包启用。） 管理员可以创建有权访问Data Warehouse的组，然后将非管理员级别的用户与该组相关联。

请参阅[管理 Data Warehouse 权限](/help/export/data-warehouse/t-dw-group.md)。

## 创建 Data Warehouse 请求

有关如何创建 Data Warehouse 请求的信息，请参阅[创建 Data Warehouse 请求](/help/export/data-warehouse/create-request/t-dw-create-request.md)。

## 管理 Data Warehouse 请求

有关如何管理 Data Warehouse 请求的信息，请参阅[管理 Data Warehouse 请求](/help/export/data-warehouse/data-warehouse-requests-manage.md)。

