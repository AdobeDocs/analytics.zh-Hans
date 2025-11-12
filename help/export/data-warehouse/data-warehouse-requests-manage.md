---
description: 了解如何查看、复制和重新排定Data Warehouse请求的优先级。
title: 管理 Data Warehouse 请求
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 4%

---

# 管理 Data Warehouse 请求

您可以查看和管理已发出的Data Warehouse请求。 只有管理员才能查看和管理组织中其他用户发出的请求。

以下各节介绍了可在管理请求时执行的活动。

## 查看请求

默认情况下，您只能查看您创建的请求，除非用户已选择将其请求对组织中的其他人可见(如[Data Warehouse请求常规设置](/help/export/data-warehouse/create-request/dw-general-settings.md)中所述)。 系统管理员可以查看所有请求。

要查看Data Warehouse请求，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**]。

   Data Warehouse页面会显示您提出的所有请求。 数据显示在每列中。 您可以[配置哪些列](#configure-columns)可见。

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. （可选）单击请求名称可查看显示以下信息的对话框：<!-- Check this -->

   * 当请求开始处理时

   * 速率限制：您的组织运行过多的Data Warehouse请求。 请求将暂停，直到其他数据请求完成。

## 编辑请求

编辑请求时，请考虑以下事项：

* 只能编辑配置为按计划运行的请求。

* 并非与请求关联的所有字段都可以编辑。 无法编辑的字段将灰显。

* 编辑其他用户请求的管理员必须选择他们可以访问的新帐户和位置。

要编辑计划请求，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**]。

1. 在Data Warehouse页面上，选择要编辑的请求。

   ![管理请求](assets/dw-manage-request.png)

1. 选择&#x200B;[!UICONTROL **编辑**]。

1. 根据需要编辑请求。 无法编辑灰显的配置选项。

   有关每个配置选项的信息，请参阅[创建Data Warehouse请求](/help/export/data-warehouse/create-request/t-dw-create-request.md)。

1. 选择&#x200B;[!UICONTROL **保存更改**]。

## 查看请求的历史记录

您可以查看已发出的任何Data Warehouse请求的历史记录。

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**]。

1. 在Data Warehouse页面上，选择要查看其历史记录的请求。

   ![管理请求](assets/dw-manage-request.png)

1. 选择&#x200B;[!UICONTROL **查看历史记录**]。

   [!UICONTROL **查看Data Warehouse请求**]&#x200B;页面显示与该请求关联的各个报告投放的列表。

   选择&#x200B;**配置列**&#x200B;图标![配置列图标](assets/configure-column-icon.png)以隐藏默认不显示的列或显示列。

   ![请求历史记录页](assets/dw-request-history.png)

   以下列可供使用：

   | 列 | 描述 |
   |---------|----------|
   | [!UICONTROL **创建日期**] | 报告的创建日期和时间。<p>以发起请求的用户的时区显示。</p> |
   | [!UICONTROL **开始日期**] | 报表开始的日期和时间。<p>以发起请求的用户的时区显示。</p> |
   | [!UICONTROL **完成日期**] | 报表完成的日期和时间。<p>以发起请求的用户的时区显示。</p> |
   | [!UICONTROL **日期已更新**] | 上次更新报告的日期和时间。<p>以发起请求的用户的时区显示。</p> |
   | [!UICONTROL **状态**] | 报告投放的状态。 可能的状态是：<ul><li>[!UICONTROL **已创建**]：报告已创建，但尚未处理。</li><li>[!UICONTROL **挂起**]：报表正在等待处理。</li><li>[!UICONTROL **正在处理**]：报表当前正在处理。</li><li>[!UICONTROL **已完成**]：报告已完成，现在可用。</li><li>[!UICONTROL **已计划**]：报告已计划，但尚未启动。</li><li>[!UICONTROL **已取消**]：用户已取消报告。</li><li>[!UICONTROL **错误 — 正在处理**：]报告遇到错误，无法处理。</li><li>[!UICONTROL **错误 — 无法发送**]：报告生成成功，但无法传送。 检查目标[的](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)配置，然后重新发送报告。</li></ul>。 |
   | [!UICONTROL **来自**] | 报表中包含的整体时间范围的开始日期。<p>它以报表包的时区显示。</p> |
   | [!UICONTROL **至**] | 报告中包含的整体时间范围的结束日期。 <p>它以报表包的时区显示。</p> |
   | [!UICONTROL **旧请求ID**] | 用于在旧版Data Warehouse界面中标识报表的ID。 联系Adobe客户关怀团队时可能需要此ID。 |
   | [!UICONTROL **报告ID**] | 用于在当前Data Warehouse界面中标识报表的ID。 联系Adobe客户关怀团队时可能需要此ID。 |


1. 选择一个报表交付，然后选择以下任一选项：

   | 选项 | 功能 |
   |---------|----------|
   | [!UICONTROL **目标详细信息**] | 显示与请求关联的帐户和位置详细信息。 这是之前配置的帐户和位置，如[为Data Warehouse请求配置报表目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)中所述。 |
   | [!UICONTROL **取消报告**] | 取消报告。 您无法取消状态为&#x200B;[!UICONTROL **已完成**]&#x200B;或&#x200B;[!UICONTROL **已取消**]&#x200B;的报告。 |
   | [!UICONTROL **重新运行报告**] | 再次运行报表，其中包含与最初发送时相同的数据。 您可以重新运行具有以下任意状态的报表： [!UICONTROL **已取消**]、[!UICONTROL **已完成**]、[!UICONTROL **错误 — 正在处理**]&#x200B;或&#x200B;[!UICONTROL **错误 — 无法发送**]。 |
   | [!UICONTROL **重新发送报告**] | 重新发送之前生成的报告文件。 您可以重新发送具有以下任意状态的报表： [!UICONTROL **已完成**]&#x200B;或&#x200B;[!UICONTROL **错误 — 无法发送**]。 |

## 复制请求

复制请求时，将从原始请求复制所有配置选项。

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**]。

1. 在Data Warehouse页面上，选择要复制的请求。

   ![管理请求](assets/dw-manage-request.png)

1. 选择&#x200B;[!UICONTROL **复制**]。

   此时会显示复制Data Warehouse请求页面。 所有配置选项都复制自原始请求。

1. 更新与请求关联的任何配置选项。

   有关每个配置选项的信息，请参阅[创建Data Warehouse请求](/help/export/data-warehouse/create-request/t-dw-create-request.md)。

1. 选择&#x200B;[!UICONTROL **保存更改**]。

## 取消请求

只能取消配置为按计划运行的请求。

要取消计划请求，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**]。

1. 在Data Warehouse页面上，选择要编辑的请求。

   ![管理请求](assets/dw-manage-request.png)

1. 选择&#x200B;[!UICONTROL **取消**]。

   该请求将不再按计划时间运行。

## 配置各列

您可以通过添加或删除列来配置为每个请求显示的信息。

1. 选择Data Warehouse页面右上角的&#x200B;**配置列**&#x200B;图标。

   ![配置列](assets/dw-configure-columns.png)

   以下列可供使用：

   | 可用列 | 描述 |
   |---------|----------|
   | 请求名称 | 创建请求的人员的姓名。 |
   | 报告包 | 与请求关联的报表包。 |
   | 请求者 | 创建请求的用户。 |
   | 请求日期 | 发出请求的日期。 |
   | 状态 | 可以使用以下状态：<ul><li><p>**已完成**：请求已成功运行。</p></li><li><p>**已取消**：用户已取消请求。</p></li><li><p>**已计划**：请求已配置为按计划运行。</p></li><li><p>**失败**：请求未能完成。 如果请求仍然失败，请联系客户支持。</p></li></ul> |

   {style="table-layout:auto"}

1. 确保选定您要显示的任何列。 选定的列会显示在Data Warehouse页面上，并显示相关信息。

## 过滤和排序请求

1. 选择Data Warehouse页面左边栏中的&#x200B;**筛选器**&#x200B;图标。

   ![筛选请求](assets/dw-filter.png)

1. 展开&#x200B;[!UICONTROL **报表包**]、[!UICONTROL **所有者**]&#x200B;或&#x200B;[!UICONTROL **状态**]&#x200B;部分，然后选择要如何筛选请求。

## 搜索请求

1. 在Data Warehouse页面顶部的搜索字段中，指定要查看的请求名称。

   请求会在您键入内容时进行过滤。