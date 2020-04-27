---
description: 在“请求向导：第 1 步”中，您可以对数据请求应用某一级别的粒度。粒度指定报表中包含的基于时间的详细信息级别。
title: 粒度
topic: Report builder
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 粒度

在“请求向导: 第 1 步”上，您可以对数据请求应用某一级别的粒度。粒度指定报表中包含的基于时间的详细信息级别。

有效值包括“小时”、“日”、“周”、“月”、“季度”、“年”和“汇总”。

## Report Builder 如何处理粒度

Suppose you choose a date range for a month with [!UICONTROL Month] granularity. 则请求基于这一个月的数据显示量度的总计。如果请求的日期范围跨一个季度，则报表显示 3 个数字：以月为单位每月一个，或者所占的比例。如果今天是 3 月 18 日，并且选择的是上一季度，那么将返回 3 个数字，分别对应 1 月 1 日 - 1 月 31 日、2 月 1 日 - 2 月 28 日和 3 月 1 日 - 3 月 17 日。
