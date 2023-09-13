---
description: 描述如何创建 Data Warehouse 请求的步骤。
title: 为Data Warehouse请求配置报表选项
feature: Data Warehouse
source-git-commit: 0abf0c76f38b481c0b72d113fe49e0da03ddd8cd
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 18%

---

# 为Data Warehouse请求配置报表选项

>[!AVAILABILITY]
>
>本文中介绍的一些Data Warehouse功能(以及此部分中的其他Data Warehouse文章)仅在版本的有限测试阶段提供，并且在您的环境中可能尚未提供。
>
>有关尚未向所有客户提供的功能的信息，以及有关这些功能发布时间线的信息，请参阅 [发行说明](/help/release-notes/latest.md).
>
>当该功能正式发布时，将删除此说明。有关 Analytics 发布流程的信息，请参阅 [Adobe Analytics 功能发布](/help/release-notes/releases.md)。

创建Data Warehouse请求时，有多种可用的配置选项。 以下信息介绍了如何为请求配置报表选项。

有关如何开始创建请求以及指向其他重要配置选项的链接的信息，请参阅 [创建Data Warehouse请求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

要为Data Warehouse请求配置报表选项，请执行以下操作：

1. 通过在Adobe Analytics中选择 **[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **添加**].

   有关其他详细信息，请参阅 [创建Data Warehouse请求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 在“新建Data Warehouse请求”页面上，选择 [!UICONTROL **报表选项**] 选项卡。

   ![“报表目标”选项卡](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. 请完成以下字段：

   | 选项 | 函数 |
   |---------|----------|
   | 文件名 | 标识报表。 |
   | 将报表日期范围附加到文件名 | 将日期范围添加到报表文件名。 <p>例如，如果您请求获得从2024年5月1日到2024年5月7日的数据，则文件名将包含日期范围20240501 - 20240507。</p> |
   | CSV | 以CSV文件格式发送报表，用于查看电子表格中的数据。 |
   | 表格(TDE) | 以Tableau数据提取(TDE)文件格式发送报告，该文件格式可用于在Tableau中可视化附加数据的数据和层。 |
   | 以压缩文件(ZIP)形式发送报表 | 以压缩(ZIP)文件格式发送报表。 我们建议在使用电子邮件作为时启用此选项 [报表目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | 表格中的行数 | 可包含在报告中的行数。 使用0包括所有行（这是默认选项）。 <!-- when would you want to limit the rows? To improve performance? Do we have recommendations? --> |
   | 评论 | 添加任何要包含在报告中的注释。 评论显示在报告开头。 |
   | 按量度排序 | 在 Data Warehouse 中提供排名的划分报表（按量度值从大到小排序）。按量度排序可以让您更易于解释 Data Warehouse 报表，同时，也可以更轻松地将这些报表与其他 Analytics 划分报表查看次数进行比较。<p>有关更多信息，请参阅 [按指标排序](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | 发送清单文件 | 包含有关报表中包含的文件的元数据。<!-- What kind of metadata is included in the manifest file? --> |
   | 发送数字签名文件 | 允许报表接收者验证文件是否来自Adobe以及是否未被更改。 |
   | 当报告中没有数据时，发送空文件 | 发送报告，即使报告不包含任何数据。 |

   {style="table-layout:auto"}

1. 继续在上配置您的Data Warehouse请求 [!UICONTROL **计划选项**] 选项卡。 有关更多信息，请参阅 [为Data Warehouse请求配置计划选项](/help/export/data-warehouse/create-request/dw-request-scheduling.md).