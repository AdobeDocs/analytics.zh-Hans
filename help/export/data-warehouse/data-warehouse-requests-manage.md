---
description: 请求管理器允许您查看和复制请求，并重新安排请求的优先级。
title: 管理 Data Warehouse 请求
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: 8507ce3f7e4d09956ad88c2be5335b68c8e3b8a0
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 18%

---

# 管理 Data Warehouse 请求

{{release-limited-testing}}

>[!NOTE]
>
>如果您的组织尚不具有即将面向所有客户提供的新Data Warehouse体验，请使用以下位置的信息： [管理Data Warehouse请求（旧体验）](#manage-data-warehouse-requests-old-experience)


您可以管理已发出的Data Warehouse请求。 以下各节介绍了可在管理请求时执行的活动。 <!-- just those you have made? I think you can see other people's requests (you can filter by them). What can you do with other people's requests? Just view them?-->

## 查看请求

1. 在Adobe Analytics中，选择 [!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**].

   “Data Warehouse”页显示您已提出的所有请求。 <!-- just those you have made? -->数据显示在每列中。 您可以 [配置哪些列](#configure-columns) 可见。

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. （可选）单击请求名称可查看显示以下信息的对话框： <!-- Check this -->

   * 当请求开始处理时

   * 比率限制：您的组织有太多正在运行的Data Warehouse请求。 请求将暂停，直到其他数据请求完成。

## 编辑请求

编辑请求时，请考虑以下事项：

* 只能编辑配置为按计划运行的请求。

* 并非与请求关联的所有字段都可以编辑。 无法编辑的字段将灰显。

要编辑计划请求，请执行以下操作：

1. 在Adobe Analytics中，选择 [!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**].

1. 在“Data Warehouse”页面上，选择要编辑的请求。

   ![管理请求](assets/dw-manage-request.png)

1. 选择 [!UICONTROL **编辑**].

1. 根据需要编辑请求。 无法编辑灰显的配置选项。

   有关每个配置选项的信息，请参见 [创建Data Warehouse请求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 选择 [!UICONTROL **保存更改**].

## 查看请求的历史记录

您可以查看任何已运行的报表的历史记录。

1. 在Adobe Analytics中，选择 [!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**].

1. 在“Data Warehouse”页面上，选择要查看其历史记录的请求。

   ![管理请求](assets/dw-manage-request.png)

1. 选择 [!UICONTROL **查看历史记录**].

## 复制请求

复制请求时，将从原始请求复制所有配置选项。

1. 在Adobe Analytics中，选择 [!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**].

1. 在“Data Warehouse”页面上，选择要复制的请求。

   ![管理请求](assets/dw-manage-request.png)

1. 选择 [!UICONTROL **复制**].

   此时将显示复制Data Warehouse请求页面。 所有配置选项都复制自原始请求。

1. 更新与请求关联的任何配置选项。

   有关每个配置选项的信息，请参见 [创建Data Warehouse请求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 选择 [!UICONTROL **保存更改**].

## 取消请求

只能取消配置为按计划运行的请求。

要取消计划请求，请执行以下操作：

1. 在Adobe Analytics中，选择 [!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**].

1. 在“Data Warehouse”页面上，选择要编辑的请求。

   ![管理请求](assets/dw-manage-request.png)

1. 选择 [!UICONTROL **取消**].

   该请求将不再按计划时间运行。

## 配置列

您可以通过添加或删除列来配置为每个请求显示的信息。

1. 选择 **配置列** 图标(位于Data Warehouse页面的右上角)。

   ![配置列](assets/dw-configure-columns.png)

   以下列可供使用：

   | 可用列 | 描述 |
   |---------|----------|
   | 请求名称 | 创建请求的人员的姓名。 |
   | 报表包 | 与请求关联的报表包。 |
   | 请求者 | 创建请求的用户。 |
   | 请求日期 | 发出请求的日期。 |
   | 状态 | 可以使用以下状态：<ul><li><p>**已完成**：请求已成功运行。</p></li><li><p>**已取消**：用户已取消请求。</p></li><li><p>**已计划**：请求配置为按计划运行。</p></li><!-- Are there other statuses? Failed? --> |

   {style="table-layout:auto"}

1. 确保选定您要显示的任何列。 选定的列将显示在“Data Warehouse”页上，并显示相关信息。

## 过滤和排序请求

1. 选择 **筛选** 图标(位于Data Warehouse页面的左边栏中)。

   ![筛选请求](assets/dw-filter.png)

1. 展开 [!UICONTROL **报表包**]， [!UICONTROL **所有者**]，或 [!UICONTROL **状态**] 部分，然后选择您希望如何过滤请求。

## 搜索请求

1. 在“Data Warehouse”页顶部的“搜索”字段中，指定要查看的请求名称。

   请求会在您键入内容时进行过滤。

## 管理Data Warehouse请求（旧体验）

>[!NOTE]
>
>以下信息仅适用于贵组织尚不具有新Data Warehouse体验的情况，该体验很快将适用于所有Analytics客户。


请求管理器允许您查看和复制请求，并重新安排请求的优先级。

在 Data Warehouse 中，选择&#x200B;**[!UICONTROL 请求管理器]**&#x200B;选项卡。

使用此选项卡，您可以

* 按报表名称、应用的区段、请求者、请求日期和状态查看最近的报表请求。
* 复制请求。单击请求旁边的&#x200B;**[!UICONTROL 复制]**。

  >[!NOTE]
  >
  >此操作只会复制请求，而不会复制计划或提交详细信息。

* 按报表名称或请求者的登录名搜索报表。
* 通过将报表拖放到队列中的新位置，重新安排报表的优先级。
* 要查看请求开始处理的时间，请单击计划请求 ID，然后检查打开的弹出窗口。

单击某个作业可查看该作业的单个请求。

* 比率限制：您的组织有太多正在运行的Data Warehouse请求。 请求将暂停，直到其他数据请求完成。