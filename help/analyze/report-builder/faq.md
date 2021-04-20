---
title: Report Builder 常见问题解答
description: 有关Report Builder的常见问题解答。
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 1%

---


# Report Builder 常见问题解答

有关Report Builder的常见问题解答。

## 是否可以在工作簿中使用`TODAY()`或`DATERANGE()`函数？

Excel中的[`TODAY()`函数](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9)返回当天。 [`DATEVALUE()`函数](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252)将日期字符串转换为串行值。 尽管Adobe对Excel中的许多功能很有帮助，但强烈建议不要将这些功能用作Report Builder计划请求的一部分。 Adobe客户服务部门不支持使用上述任一功能进行故障排除。

计划报表在可能不会与报表包共享时区的服务器上处理。 用户期望的`TODAY()`和处理服务器使用的`TODAY()`通常可能不同。 此外，使用日期基于处理开始时。 如果同时运行多个报表，则请求日期与由于延迟而开始处理日期之间可能会发生变化。 如果预定时间接近午夜，则会出现此问题。

计划报表也会在可能不共享日期语法的服务器上处理。 例如，`7/1/YYYY`可以参考7月1日或1月7日，具体取决于您所在的国家或地区。 在此日期使用`DATEVALUE()`函数将导致不同的序列值，具体取决于执行该函数的计算机。

作为使用这些Excel函数的替代方法，Adobe强烈建议在Report Builder请求中使用日期范围。 在请求向导的第一页，在下拉菜单中选择&#x200B;**[!UICONTROL 预设日期]**，然后在“常用日期”下选择&#x200B;**[!UICONTROL 今天]**&#x200B;或其他所需日期范围。 此设置占用运行报表包的时间，而不是服务器处理请求的时间。

## 我可以做多大和复杂的工作簿？

Report Builder支持以下限制的工作簿：

* **1000项请求**:一个工作簿在一个工作簿中最多可包含1000个数据请求。如果您有需要超过1000个请求的报表或项目，Adobe建议将其分为多个工作簿。
* **每小时2万个请求**:Report Builder使用Analytics报告API检索数据。每个请求在创建或刷新时都使用API调用。 如果您的组织在给定的小时内累积了超过20,000个API调用，您必须等到下一小时再检索数据。
* **4小时处理时间**:处理过去4小时后，计划报表超时。如果您的工作簿包含使用大数据集的许多复杂请求，则计划报表可能会失败。
