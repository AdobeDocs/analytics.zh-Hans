---
description: Data Warehouse 为运行自定义报表提供了灵活的界面。遵循这些指导进行操作有助于缩短检索数据所用的时间。
keywords: best practices;failure;timeout;troubleshooting
solution: Analytics
title: Data Warehouse 最佳实践
topic: Data warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Data Warehouse 最佳实践

数据仓库提供了一个灵活的界面来运行自定义报表。 遵循这些指导进行操作有助于缩短检索数据所用的时间。



| 指导 | 描述 |
|--- |--- |
| 在“报告与分析”中运行页面查看、访问、访客和其他标准报告 | 在创建数据仓库报表之前，请查看您要查找的信息是否已在报表中可用。 如果是，由于Reports &amp; Analytics对常见指标执行了预处理，因此报告的交付速度将大大提高。 |
| 了解请求的数据量 | 大型报表包中的多年报表可能包含上百亿个数据行。处理和评估此数据可能会花费几天乃至几周时间。查看如何使用报表来确定是否有一些多年数据，或者是否可以将报表划分为多个请求。 |
| 将报表时段与粒度进行匹配 | 报告粒度需要额外的处理时间。在对全年报告每月粒度时，如果按月提交报表请求，则报表的处理速度会更快。 |
| 报告完成的数据范围 | 数据仓库报表在请求的日期范围完成时生成。 例如，如果在星期三请求当周的报表，则到下周的星期日才会生成报表。 |
| 在 Data Warehouse 中生成路径报表 | 路径量度（登录次数、退出次数、跳出次数等）在 Data Warehouse 中不可用。 |
| 虚拟报表包 | 有关虚拟报表包的 Data Warehouse 报表支持在虚拟报表包中配置的替代时区。 |
