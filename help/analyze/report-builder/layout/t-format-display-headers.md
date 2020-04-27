---
description: 您可以为报表命名并配置行和列标题的显示方式。“格式选项”链接对“引导布局”和“自定义布局”类型可用。
title: 设置显示标题的格式
topic: Report builder
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 设置显示标题的格式

您可以为报表命名并配置行和列标题的显示方式。“格式选项”链接对“引导布局”和“自定义布局”类型可用。

1. 在上创建请求 [!UICONTROL Request Wizard: Step 1]。
1. 单击 **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2] form, add dimensions and metrics data to the request, as desired.
1. 单击 **[!UICONTROL Format Options]**.
1. Configure the [!UICONTROL Display] options:

   | 元素 | 描述 |
   |--- |--- |
   | 报表名称 | 显示从“请求向导：第 1 步”的树中选择的报表类型的名称（例如，[!DNL Traffic Report]），或者显示您在 [!DNL Name this Request] 字段中键入的名称。 |
   | 过滤器参数 | 显示维度过滤器，如搜索过滤器。 |
   | 区段 | 显示区段参数。 |
   | “数据新近度” | 显示数据新近度参数。例如：数据新近度：页面查看次数（1.5 小时前）、退出次数（30 分钟前）。有关当前数据处理的信息，请参阅[选项](/help/analyze/report-builder/options.md)。 |

   Regarding display order, if the [!UICONTROL Row Label] grid (on Step 2) contains an item, it is displayed first in the request. If not, the system uses the first item present in the [!UICONTROL Column Label] grid. If no row or column items exist, the first item in the [!UICONTROL Metrics] grid is displayed.

   **显示行与列标题：**&#x200B;添加行和列以显示这些项目。

   在版本 3.11 中，可以分别显示各个项目的标题。版本 4 要么显示所有这些项目，要么一个都不显示。如果在版本 3.11 中创建请求但在版本 4.x 中打开，那么对于缺少标题的项目，Report Builder 会在第 2 步中提示您通过添加一个单元格来更新范围。

   **将标题更改为 Excel 自动过滤器：**&#x200B;仅在显示行和列标题时可用。此设置会创建 Excel 自动过滤器，并将其附加到 Report Builder 为此请求而返回的数据中。

   >[!NOTE]
   >
   >对于每个工作表，Excel 仅支持一个自动过滤器。如果在已具有自动过滤器的工作表中创建新的自动过滤器，那么 Excel 不提供警告即替换现有的自动过滤器。

   **执行自动分级显示：**&#x200B;将 Report Builder 返回的数据从列表视图转换为树视图。

   **为此请求命名：**&#x200B;允许您为请求键入用户定义的名称，或者使用在第 1 步中选择的默认名称。此名称在中 [!UICONTROL Report] 显示为名称 [!UICONTROL Request Manager]。 See [Name a Request](/help/analyze/report-builder/layout/name-a-request.md).

1. 单击 **[!UICONTROL OK]**.
