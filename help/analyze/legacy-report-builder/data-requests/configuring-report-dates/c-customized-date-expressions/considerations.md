---
description: 使用自定义表达式设置日期范围时的两个重要注意事项
title: 自定义日期注意事项
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
feature: Report Builder
role: User, Admin
exl-id: 66b817b3-7e9e-4030-92f3-797e730f9661
TQID: https://experienceleague.adobe.com/7PLNffmZnNnQ2X0HgnqYa8R3zWQvFPMSM8sbWocmxH4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 415
ht-degree: 7%

---

# 自定义日期注意事项

{{legacy-arb}}

使用自定义表达式设置日期范围时的两个重要注意事项：

* 运行报表（截止日期）（或刷新请求）的日期决定了哪些数据可用。
* 报表开始日期和结束日期的滚动时间范围会影响报表涵盖的日期范围。

由于数据的可用性对报表的时间范围和您刷新报表中的请求的日期都敏感，因此请确保在适当的日期运行报表以提取所需信息。 以下示例演示了这两种考虑事项。

假设您使用聚合粒度对[!UICONTROL 页面查看次数]发出请求。 在北美，一周从周日开始。 要获取星期日到星期六（例如，2008年11月23日至11月29日）期间的更新报表，请在星期日（11月30日）运行上一周（11/23至11/29）的报表（刷新请求）。

使用此自定义表达式：

*从：* cw-1w *到：* cw-1d

当请求的[!UICONTROL 结束日期]为11/30 （含）时，自定义表达式的分析：

*从：* cw-1w

当前周中从11月30日星期日开始的日期减去七天=过去一周中从11月23日星期日开始的日期

*收件人：* cw-1d

本周的某天，从11月30日星期日开始，减一天= 11月29日星期六

将自定义表达式映射到电子表格后，使用2008年11月30日星期日作为浮动请求的包含[!UICONTROL 结束日期]刷新请求。 该数据将反映为期一周的数据。

如果您刷新表达式并将11月29日星期六指定为浮动请求的[!UICONTROL 结束日期]，则数据将反映11/16到11/22这一周。 这是因为请求刷新的参考日期提前了一天。

当请求的[!UICONTROL 结束日期]为11/29（含）时，差异如下：

*从：* cw-1w

当前周中从11月23日星期日开始的日期减去七天=过去一周中从11月16日星期日开始的日期

*收件人：* cw-1d

本周的某天，从11月23日星期日开始，减一天= 11月22日星期六

在欧洲和其他一些国家，一周从周一开始，而不是周日。 在这种情况下，您可以自定义日历以更改开始日期。 （请参阅[自定义日历](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)。）
