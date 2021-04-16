---
description: 网络日志数据源允许您导入标准的网站服务器日志文件。
subtopic: Data sources
title: 网络日志
topic-fix: Developer and implementation
uuid: a0efed57-6d1b-43d8-97ce-dc31009805e0
exl-id: 11c4f21a-de07-436e-a05e-ab6769cb3e21
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 100%

---

# 网络日志

网络日志数据源允许您导入标准的网站服务器日志文件。

支持以下常用网站服务器日志类型：

| 列名称 | 描述 |
|--- |--- |
| NCSA 普通日志 | Apache 默认 |
| NCSA 扩展（组合） | Apache |
| W3C 扩展日志 | 用于 IIS 4.0 及更高版本 |
| Microsoft IIS 日志 | 用于 IIS 3.0 及更早版本 |

数据源处理的主要日志文件字段包含 IP 地址、请求的日期/时间和 URL。在少数情况下（如 NCSA 扩展格式），数据源还处理“反向链接”和“用户代理”字段。

您可以使用标准市场营销报表查看有关页面查看、访问量和访客的网络日志数据。由于报表量度主要基于 Cookie，且网站服务器日志基于 IP 地址，因此 Adobe 建议专为上述目的将网站服务器日志导入单独的报表包。

有关网站服务器日志文件的详细信息，请查阅您的网站服务器文档。
