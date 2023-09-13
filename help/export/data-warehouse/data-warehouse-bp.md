---
description: Data Warehouse 为运行自定义报表提供了灵活的界面。遵循这些指导进行操作有助于缩短检索数据所用的时间。
keywords: 最佳实践；失败；超时；疑难解答
title: Data Warehouse 最佳实践
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
source-git-commit: 2ed0627efe50c000c9fe440fccafd12739b09554
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 89%

---

# Data Warehouse 最佳实践

Data Warehouse 为运行自定义报表提供了灵活的界面。请遵循以下准则以帮助减少检索数据所需的时间：

| 指导 | 描述 |
|--- |--- |
| 在 Reports &amp; Analytics 中运行“页面查看”、“访问”、“访客”和其他标准报表 | 在创建 Data Warehouse 报表前，请查看报表中是否已有您要查找的信息。如果有，则传送报表的速度会非常快，因为 Reports &amp; Analytics 对常用量度执行了预处理。 |
| 了解请求的数据量 | 大型报表包中的多年报表可能包含上百亿个数据行。处理和评估此数据可能会花费几天乃至几周时间。查看如何使用报表来确定是否有一些多年数据，或者是否可以将报表划分为多个请求。 |
| 将报表时段与粒度进行匹配 | 报告粒度需要额外的处理时间。在对全年报告每月粒度时，如果按月提交报表请求，则报表的处理速度会更快。 |
| 报告完成的数据范围 | Data Warehouse 报表在请求的日期范围完成后生成。例如，如果在星期三请求当周的报表，则到下周的星期日才会生成报表。 |
| 在 Data Warehouse 中生成路径报表 | 路径量度（登入次数、退出次数、跳出次数等）在Data Warehouse中不可用。 |
| 虚拟报表包 | 有关虚拟报表包的 Data Warehouse 报表支持在虚拟报表包中配置的替代时区。 |

