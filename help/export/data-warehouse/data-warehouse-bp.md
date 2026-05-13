---
description: 了解有助于缩短从Data Warehouse检索数据所用时间的准则。
keywords: 最佳实践；失败；超时；疑难解答
title: Data Warehouse最佳实践
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
TQID: https://experienceleague.adobe.com/fWshdRnbrh11kLLT3DiW0a-qMJ13o8v4EMH-t-ceWC8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 27%

---

# Data Warehouse 最佳实践

Data Warehouse 为运行自定义报表提供了灵活的界面。 请遵循以下准则以帮助减少检索数据所需的时间：

| 参考性能 | 描述 |
|--- |--- |
| 了解您请求的数据量 | 大型报表包的多年期报表可能包含数百亿数据行。 处理和评估此数据可能会花费几天乃至几周时间。 评估如何使用报表来确定某些多年期数据是否可用，或者您是否可以将报表拆分为多个请求。 |
| 将报表时段与粒度匹配 | 报表粒度需要额外的处理时间。 如果您报告的粒度为整年的每月粒度，则在提交每月报表请求时，报表处理速度会更快。 |
| 报告已完成的数据范围 | Data Warehouse 报表在请求的日期范围完成后生成。 例如，如果在星期三请求当周的报表，则到下周的星期日才会生成报表。 |
| 在Data Warehouse中生成路径报表 | 路径量度（登入次数、退出次数、跳出次数等） 在Data Warehouse中不可用。 |
| 虚拟报告包 | 虚拟报表包的Data Warehouse报表功能支持在虚拟报表包上配置的替代时区。 |

