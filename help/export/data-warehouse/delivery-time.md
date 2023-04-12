---
title: Data Warehouse 请求提交时间故障诊断
description: 确定 Data Warehouse 请求存在的可能会延长提交时间的潜在问题。
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 97%

---

# Data Warehouse 请求提交时间故障诊断

给定 Data Warehouse 请求可能需要不到一小时，或者几天甚至更长时间才能处理。由于以下因素，很难估计处理请求所需的确切时间：

* 请求的日期范围
* 在请求的时间段内，您的报表包收到的流量
* 区段内的规则数量，以及区段内使用的变量
* 区段内包含的数据量
* 使用的细分数量，以及每个细分中的唯一值数量
* 使用的量度数量
* 正在处理的并发请求数量
* VISTA 规则（如果已配置为应用于 Data Warehouse 请求）

如果您发现 Data Warehouse 请求持续处理较长时间，请考虑更改请求以适应以下情况：

* **使用包含较小数据样本的区段**：请求处理的数据越少，返回报表的速度就越快。
* **以 14 天或更短的时间增量运行请求**：处理较小的请求比处理较大的请求速度更快。
* **使用较少的细分**：Data Warehouse 请求中的许多细分会急剧增加处理时间。

>[!IMPORTANT]
>
> *无法加快 Data Warehouse 请求的提交速度。*

如果您需要更及时地获取这些类型的报表，请考虑以下替代方案：

* **Analysis Workspace**：虽然不能使用无限数量的维度项目，但它包含 Data Warehouse 提供的几乎所有其他用例。
* **数据馈送**：每天获取报表包中的所有原始数据，并将其发送到 FTP 站点。然后，您可以将此数据导入自己的数据库，并运行查询以获取要查找的数据。
* **自定义工程服务解决方案**：Adobe 工程服务团队可以为贵组织提供自定义解决方案，但需支付额外费用。请联系您的Adobe客户团队以了解更多详细信息。
