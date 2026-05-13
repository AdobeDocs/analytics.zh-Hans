---
description: 在“请求向导：第 1 步”中，您可以对数据请求应用某一级别的粒度。 粒度指定报表中包含的基于时间的详细信息级别。
title: 粒度
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
TQID: https://experienceleague.adobe.com/26j4Fernl4bfuYeyuVVzw1K5hZvNSD6pDUVOfEc0J8s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 14%

---

# 粒度

{{legacy-arb}}

在“请求向导：第1步”中，您可以对数据请求应用某一级别的粒度。 粒度指定报表中包含的基于时间的详细信息级别。

有效值包括小时、日、周、月、季度、年和汇总。

## Report Builder 如何处理粒度

假设您选择的日期范围为粒度为[!UICONTROL 月]的月份。 请求仅根据一个月的数据显示指标的总数。 如果请求的日期范围跨越一季度，则报表会显示三张图表：每张图表显示一张图表，或部分图表。 如果今天是3月18日，则选择最后一个季度会返回一个1月1日至1月31日的数字，另一个2月1日至2月28日的数字，以及3月1日至3月17日的最终数字。
