---
description: 您可以为报表命名并配置行和列标题的显示方式。“格式选项”链接对“引导布局”和“自定义布局”类型可用。
seo-description: 您可以为报表命名并配置行和列标题的显示方式。“格式选项”链接对“引导布局”和“自定义布局”类型可用。
seo-title: 设置显示标题的格式
solution: Analytics
title: 设置显示标题的格式
topic: Report Builder
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 设置显示标题的格式

您可以为报表命名并配置行和列标题的显示方式。“格式选项”链接对“引导布局”和“自定义布局”类型可用。

1. 在“[!UICONTROL 请求向导: 第 1 步]”中创建请求。
1. Click **[!UICONTROL Next]**.
1. 在“[!UICONTROL 请求向导: 第 2 步]”窗体中，根据需要向请求添加维度和量度数据。
1. Click **[!UICONTROL Format Options]**.
1. 配置“[!UICONTROL 显示]”选项：

   | 元素 | 描述 |
   |--- |--- |
   | 报表名称 | Displays either the name of the report type you selected from the tree in the  Request Wizard: Step 1 (for example, [!DNL Traffic Report]), or the name you type in the [!DNL Name this Request] field. |
   | 过滤器参数 | 显示维度过滤器，如搜索过滤器。 |
   | 区段 | 显示区段参数。 |
   | “数据新近度” | 显示数据新近度参数。例如：    Data Recency: Page Views (1.5 hr ago), Exits (30 mins ago)  See [Options](../../../analyze/report-builder/options.md) for information about current data processing. |

   关于显示顺序，如果“[!UICONTROL 行标签]”网格（在第 2 步中）包含项目，则首先在请求中显示该项目。如果未包含，则系统使用“[!UICONTROL 列标签]”网格中的第一项。如果没有行或列项目，则显示“[!UICONTROL 量度]”网格中的第一项。

   **显示行与列标题：**&#x200B;添加行和列以显示这些项目。

   在版本 3.11 中，可以分别显示各个项目的标题。版本 4 要么显示所有这些项目，要么一个都不显示。如果在版本 3.11 中创建请求但在版本 4.x 中打开，那么对于缺少标题的项目，Report Builder 会在第 2 步中提示您通过添加一个单元格来更新范围。

   **将标题更改为 Excel 自动过滤器：**&#x200B;仅在显示行和列标题时可用。此设置会创建 Excel 自动过滤器，并将其附加到 Report Builder 为此请求而返回的数据中。

   >[!NOTE]
   >
   >Excel仅支持每个工作表一个自动过滤器。如果在已具有自动过滤器的工作表中创建新的自动过滤器，那么 Excel 不提供警告即替换现有的自动过滤器。

   **执行自动分级显示：**&#x200B;将 Report Builder 返回的数据从列表视图转换为树视图。

   **为此请求命名：**&#x200B;允许您为请求键入用户定义的名称，或者使用在第 1 步中选择的默认名称。此名称在[!UICONTROL 请求管理器]中显示为[!UICONTROL 报表]名称。请参阅[为请求命名](../../../analyze/report-builder/layout/name-a-request.md#concept_37277AFB63EA4541B6FD93A5B713D82D)。

1. Click **[!UICONTROL OK]**.
