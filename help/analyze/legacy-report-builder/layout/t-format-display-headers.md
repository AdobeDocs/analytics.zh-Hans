---
description: 了解如何命名报告并配置如何显示行和列标题。
title: 如何格式化显示标题
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 71%

---

# 设置显示标题的格式

{{legacy-arb}}

您可以为报表命名并配置行和列标题的显示方式。“格式选项”链接对“引导布局”和“自定义布局”类型可用。

1. 在“[!UICONTROL 请求向导: 第 1 步]”中创建请求。
1. 单击&#x200B;**[!UICONTROL 下一步]**。
1. 在“[!UICONTROL 请求向导: 第 2 步]”窗体中，根据需要向请求添加维度和量度数据。
1. 单击&#x200B;**[!UICONTROL 格式选项]**。
1. 配置“[!UICONTROL 显示]”选项：

   | 元素 | 描述 |
   |--- |--- |
   | 报表名称 | 显示从“请求向导：第 1 步”的树中选择的报表类型的名称（例如，[!DNL Traffic Report]），或者显示您在 [!DNL Name this Request] 字段中键入的名称。 |
   | 过滤器参数 | 显示维度过滤器，如搜索过滤器。 |
   | 区段 | 显示区段参数。 |
   | “数据新近度” | 显示数据新近度参数。例如：    数据新近度：页面查看次数（1.5小时前）、退出次数（30分钟前）。有关当前数据处理的信息，请参阅[选项](/help/analyze/legacy-report-builder/options.md)。 |

   关于显示顺序，如果“[!UICONTROL 行标签]”网格（在第 2 步中）包含项目，则首先在请求中显示该项目。如果未包含，则系统使用“[!UICONTROL 列标签]”网格中的第一项。如果没有行或列项目，则显示“[!UICONTROL 量度]”网格中的第一项。

   **显示行与列标题：**&#x200B;添加行和列以显示这些项目。

   在版本 3.11 中，可以分别显示各个项目的标题。版本 4 要么显示所有这些项目，要么一个都不显示。如果您在版本3.11中创建了请求，然后在版本4.x中打开该请求，则Report Builder会在步骤2中提示您为缺少标题的项目使用一个单元格来更新范围。

   **将标题更改为 Excel 自动过滤器：**&#x200B;仅在显示行和列标题时可用。此设置会创建Excel自动过滤器，并将其附加到为此请求返回的数据Report Builder。

   >[!NOTE]
   >
   >对于每个工作表，Excel 仅支持一个自动过滤器。如果在已具有自动过滤器的工作表中创建新的自动过滤器，那么 Excel 不提供警告即替换现有的自动过滤器。

   **执行自动分级显示：**&#x200B;将Report Builder返回的数据从列表视图转换为树视图。

   **为此请求命名：**&#x200B;允许您为请求键入用户定义的名称，或者使用在第 1 步中选择的默认名称。此名称在[!UICONTROL 请求管理器]中显示为[!UICONTROL 报表]名称。查看[为请求命名](/help/analyze/legacy-report-builder/layout/name-a-request.md)。

1. 单击&#x200B;**[!UICONTROL 确定]**。
