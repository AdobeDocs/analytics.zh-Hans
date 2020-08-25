---
title: Report Builder常见问题解答
description: Report Builder的常见问题解答。
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---


# Report Builder常见问题解答

关于Report Builder的常见问题解答。

## 是否可以在工 `TODAY()` 作簿 `DATERANGE()` 中使用或函数？

Excel [`TODAY()` 中的函](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) 数返回当天。 函数 [`DATEVALUE()` 将日期](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) 字符串转换为序列值。 虽然Adobe对Excel中的许多功能很有帮助，但强烈建议不要将这些功能用作Report Builder计划请求的一部分。 Adobe客户关怀部门不支持使用以下任一功能进行故障诊断请求。

计划报告在可能不与报表包共享时区的服务器上处理。 用 `TODAY()` 户期望和处理服 `TODAY()` 务器使用的通常可能不同。 此外，使用日期基于处理开始时。 如果同时运行多个报告，则日期可在请求时间和由于延迟而开始处理时间之间发生变化。 如果预定时间接近午夜，则出现此问题。

在可能不共享日期语法的服务器上也会处理计划报告。 例如，根 `7/1/YYYY` 据您所在的国家／地区，可以参考7月1日或1月7日。 根据执 `DATEVALUE()` 行此日期的计算机，使用该函数将产生不同的序列值。

作为使用这些Excel函数的替代方法，Adobe强烈建议在Report Builder请求中使用日期范围。 在请求向导的第一页，在下拉框中选 **[!UICONTROL 择预设日期]** ，然后在常用日期下选择 **[!UICONTROL 今天]** 或其他所需的日期范围。 此设置需要报告包在运行时的时间，而不是服务器处理请求的时间。

## 我可以制作多大和复杂的工作簿？

Report Builder支持以下限制的工作簿：

* **1000个请求**:一个工作簿在一个工作簿中最多可包含1000个数据请求。 如果您有需要1000个以上请求的报表或项目，Adobe建议将它们分为多个工作簿。
* **每小时20K请求公司**:Report Builder使用Analytics报告API检索数据。 每个请求在创建或刷新时都使用API调用。 如果您的组织在给定的小时内累积超过20,000个API调用，您必须等到下一小时再检索数据。
* **4小时处理时间**:处理过去4小时后，计划报告超时。 如果您的工作簿包含许多使用大数据集的复杂请求，则计划报告可能会失败。
