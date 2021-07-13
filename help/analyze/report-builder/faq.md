---
title: Report Builder 常见问题解答
description: 有关Report Builder的常见问题解答。
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 1%

---

# Report Builder 常见问题解答

有关Report Builder的常见问题解答。

## 我能否在工作簿中使用`TODAY()`或`DATERANGE()`函数？

Excel中的[`TODAY()`函数](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9)返回当天。 [`DATEVALUE()`函数](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252)将日期字符串转换为序列值。 虽然Adobe在Excel中具有许多功能，但强烈建议不要将这些函数用作Report Builder计划请求的一部分。 Adobe客户关怀团队不支持使用其中任一功能对请求进行故障诊断。

计划报表在可能与报表包不共享时区的服务器上进行处理。 用户期望的`TODAY()`和处理服务器使用的`TODAY()`通常可能不同。 此外，使用日期还基于处理开始时间。 如果同时运行多个报表，则请求日期与由于延迟而开始处理日期之间的日期可能会发生更改。 如果计划时间接近午夜，则会出现此问题。

计划报表也会在可能不共享日期语法的服务器上进行处理。 例如，`7/1/YYYY`可以指7月1日或1月7日，具体取决于您所在的国家/地区。 在此日期使用`DATEVALUE()`函数会根据执行该函数的计算机而产生不同的序列值。

作为使用这些Excel函数的替代方法，Adobe强烈建议在Report Builder请求中使用日期范围。 在请求向导的第一页，在下拉菜单中选择&#x200B;**[!UICONTROL 预设日期]**，然后在常用日期下，选择&#x200B;**[!UICONTROL 今天]**&#x200B;或其他所需的日期范围。 此设置占用报表包运行时的时间，而不是服务器处理请求的时间。

## 我可以创建多大和复杂的工作簿？

Report Builder支持的工作簿最多可达以下限制：

* **1000个请求**:一个工作簿在单个工作簿中最多可包含1000个数据请求。如果您的报表或项目需要1000个以上的请求，则Adobe建议将它们分隔为多个工作簿。
* **每公司每小时2万个请求**:Report Builder使用Analytics报表API来检索数据。每个请求在创建或刷新时都使用API调用。 如果贵组织在给定小时内累积了超过20,000个API调用，则必须等到下一小时才能再次检索数据。
* **4小时处理时间**:计划报表在处理过去4小时后超时。如果您的工作簿包含许多使用大数据集的复杂请求，则计划报表可能会失败。
