---
description: 了解Data Warehouse以及如何过滤数据，让您创建和运行自定义报表。
title: Data Warehouse概述
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 79%

---

# Data Warehouse 概述

Data Warehouse 可让您复制 Adobe Analytics 数据以用于存储和创建自定义报表，可以通过筛选数据来运行这些报表。

## 报表概述

Data Warehouse 报表可以根据独特的问题显示高级数据与原始数据的关系。它们可以在单个请求中包含无限数量的行（针对单个报表、计划报表和已下载报表）。

>[!NOTE]
>
>Data Warehouse 会报告在报表时段遇到的第一个值。

>[!IMPORTANT]
>
>在对分类的值进行分段时，Analysis Workspace 和 Data Warehouse 处理“未指定”值的方式有所不同。工作区中的“未指定”是指未分类的值，而 Data Warehouse 中的“未指定”是指您分类为“未指定”的值。

## 投放概述

Data Warehouse 报表通过电子邮件发送或发送给云存储提供商，过程可能长达 72 小时。处理时间取决于查询的复杂程度和请求的数据量。

Data Warehouse 会自动将任何大小超过 1 MB 的文件压缩为 zip 包。电子邮件附件的最大大小为 10 MB。

## 访问

对于特定的报表包，Adobe 仅为管理员级别的用户启用 Data Warehouse。（它可以为全局报表包和子报表包启用，但不能为汇总报表包启用。） 管理员可以创建有权访问Data Warehouse的组，然后将非管理员级别的用户与该组相关联。

请参阅[管理 Data Warehouse 权限](/help/export/data-warehouse/t-dw-group.md)。

## 创建 Data Warehouse 请求

有关如何创建 Data Warehouse 请求的信息，请参阅[创建 Data Warehouse 请求](/help/export/data-warehouse/create-request/t-dw-create-request.md)。

## 管理 Data Warehouse 请求

有关如何管理 Data Warehouse 请求的信息，请参阅[管理 Data Warehouse 请求](/help/export/data-warehouse/data-warehouse-requests-manage.md)。

