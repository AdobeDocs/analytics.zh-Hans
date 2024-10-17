---
description: 了解 Report Builder 常见问题解答。
title: Report Builder 常见问题解答
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 100%

---

# Report Builder 常见问题解答

{{legacy-arb}}

与 Report Builder 有关的常见问题解答。

## 我可以在工作簿中使用 `TODAY()` 或 `DATERANGE()` 函数吗？ {#today}

Excel 中的 [`TODAY()` 函数](https://support.microsoft.com/zh-cn/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9)会返回当前日期。[`DATEVALUE()` 函数](https://support.microsoft.com/zh-cn/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252)会将日期字符串转换为序列值。虽然这些函数对 Excel 中的许多功能很有帮助，但 Adobe 强烈建议不要将这些函数用作 Report Builder 计划请求的一部分。Adobe 客户关怀不支持使用其中任一函数对请求进行疑难解答。

计划报表在可能不与报表包具有相同时区的服务器上进行处理。用户预期的 `TODAY()` 与处理服务器使用的 `TODAY()` 往往不同。另外，使用的日期基于处理开始日期。如果同时运行许多报告，则日期可能会因请求时间和由于延迟而开始处理的时间而异。如果计划时间接近午夜，则会出现此问题。

计划报表还在可能不采用相同日期语法的服务器上进行处理。例如，`7/1/YYYY` 可能指 7 月 1 日或 1 月 7 日，具体取决于您所在国家或地区。使用此日期的 `DATEVALUE()` 函数将会导致序列值有所不同，具体取决于执行此函数的计算机。

作为使用这些 Excel 函数的替代方法，Adobe 强烈建议在 Report Builder 请求中使用日期范围。在请求向导的第一页上，在下拉菜单中选择&#x200B;**[!UICONTROL 预设日期]**，然后在“常用日期”下选择&#x200B;**[!UICONTROL 今天]**&#x200B;或另一想要的日期范围。此设置会采用报表包运行时的时间，而不是服务器处理请求的时间。

## 我的工作簿的大小和复杂程度如何？ {#complexity}

Report Builder 支持具有以下限制的工作簿：

* **1000 个请求**：单个工作簿最多可以包含 1000 个数据请求。如果您有需要超过 1000 个请求的报告或项目，Adobe 建议将它们分成多个工作簿。
* **每个公司每小时 2 万个请求**：Report Builder 使用 Analytics 报表 API 检索数据。每个请求每当在创建或刷新完毕后即使用 API 调用。如果贵组织在给定小时内累积超过 20,000 次 API 调用，您必须等到下一小时才能再次检索数据。
* **4 小时处理时间**：计划报表在处理过去 4 小时后将超时。如果您的工作簿包含许多使用大型数据集的复杂请求，则计划报表可能会失败。

## 我如何知道我是否有权访问 Report Builder？ {#access}

您需要获得 Adobe Analytics 管理员授予的 Report Builder 访问权限。管理员在 [Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/home)中设置产品配置文件。请求您的管理员授予您访问权限。
