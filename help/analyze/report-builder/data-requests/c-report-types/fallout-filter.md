---
description: 描述如何将过滤器应用到流失报表的步骤。
title: 使用请求向导过滤流失报表
topic: Report builder
uuid: 269e900e-23bd-48d8-9bac-69e3167a9c18
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用请求向导过滤流失报表

描述如何将过滤器应用到流失报表的步骤。

此示例显示了页面流失报表。

1. 在 Adobe Report Builder 中，单击&#x200B;**[!UICONTROL 创建]**&#x200B;以打开“请求向导”。
1. 选择适当的报表包。
1. 在左侧的树视图中，选择&#x200B;**[!UICONTROL 路径]** > **[!UICONTROL 页面]** > **[!UICONTROL 页面流失]**。

   ![](assets/page_fallout.png)

1. 配置相应的[日期范围](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)。
1. 单击&#x200B;**[!UICONTROL 下一步]**。
1. 在向导的第 2 步中，在&#x200B;**[!UICONTROL 行标签]**&#x200B;下面单击&#x200B;**[!UICONTROL 定义检查点]**&#x200B;链接。（在流失报表中，您始终必须定义路径元素，这与预先应用了模式的路径报表不同。）

   ![](assets/define_checkpoints.png)

1. 选择&#x200B;**[!UICONTROL 过滤器]**&#x200B;选项。

1. 在&#x200B;**[!UICONTROL 定义网站区域流失检查点]**&#x200B;对话框中，从单元格范围或列表定义检查点。然后，单击&#x200B;**[!UICONTROL 确定]**。
1. 确定从单元格范围还是列表进行选择。
1. 如果从列表进行选择，请单击&#x200B;**[!UICONTROL 添加]**&#x200B;以选择要添加到流失路径的检查点。您可以定义 3 至 8 个检查点。（通过单击&#x200B;**[!UICONTROL 更多]**，可搜索可用的元素。）

   有关优化过滤器的更多信息，请参阅[过滤器维度](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md)。1. 通过选择&#x200B;**[!UICONTROL 可用元素]**&#x200B;中的元素并单击橙色箭头，将其从左栏移至右栏。
1. 单击&#x200B;**[!UICONTROL 确定]**&#x200B;三次，然后单击&#x200B;**[!UICONTROL 完成]**。

   现在应当刷新了报表。
