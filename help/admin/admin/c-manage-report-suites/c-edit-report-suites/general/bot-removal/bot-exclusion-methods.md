---
title: 比较不同的机器人排除法
description: 比较用于排除机器人的不同方法
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
role: Admin
feature: Bot Removal
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 94%

---

# 比较不同的机器人排除法

下表显示了用于排除机器人的不同方法以及它们之间的对比情况。

| 方法 | 机器人规则 | 按 IP 地址排除 | 客户属性 | 区段 | 第三方评分 + 区段 | 在运行时禁止对机器人的服务器调用 | 自定义 DB VISTA 规则 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **用于排除数据的方法的描述** | 基于用户代理、IP 地址或 IP 地址范围排除 | IP 地址 | 客户属性中的标志，用于将 ECID 标识为机器人 | Analytics 区段中的标准，用于根据机器人行为标识已知机器人 | 第三方（例如 [Perimeter X](https://www.perimeterx.com) 或 [Akamai Bot Manager](https://www.akamai.com/us/en/products/security/bot-manager.jsp)）为每个页面视图分配一个分数，用于指示它是机器人的可能性。分数将被发送到 Analytics 中，并且区段可用于根据分数筛选数据。 | 客户端逻辑停止为机器人执行 Analytics 服务器调用。 | VISTA 规则会将流量从符合特定标准的机器人转移到单独的报表包。 |
| **&#x200B;机器人名称是否能用于报告？** | 是 | 否 | 否 | 否 | 否 | 否 | 是 |
| **&#x200B;是否能看到机器人正在访问哪些页面？** | 是 | 否 | 否 | 否 | 是 | 否 | 是 |
| &#x200B;**是否会产生机器人服务器调用成本？** | 是 | 是 | 是 | 是 | 是 | 否 | 是 |
| **机器人数据是否在数据馈送中可用？** | 否 | 否 | 是 | 是 | 是 | 否 | 是 |
| **是否能报告机器人流量，就好像它们是实际的服务器调用一样？** | 否 | 否 | 是 | 是 | 是 | 否 | 否 |
| **是否能从数据集中追溯性地删除数据？** | 否 | 否 | 是，在实现声明的 ID 之后 | 是 | 是，在实现分数之后 | 否 | 否 |
| **是否受标准中的唯一限制的约束？** | 否 | 否 | 否 | 是 | 否 | 否 | 否 |
| **是否会产生额外成本？** | 否 | 否 | 可能会，具体取决于 Analytics SKU | 否 | 是 | 否 | 是 - 执行和维护 VISTA 规则所产生的成本 |
