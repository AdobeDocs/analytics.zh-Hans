---
description: 描述如何将过滤器应用到路径报表的步骤。
title: 使用请求向导过滤路径报表
topic: Report builder
uuid: 9b22d5b5-7ae8-49a2-90ae-0c1075562bbe
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用请求向导过滤路径报表

描述如何将过滤器应用到路径报表的步骤。

此示例使用“网站区域路径”。

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. 选择适当的报表包。
1. 在左侧的树视图中，选择 **[!UICONTROL Paths]** > **[!UICONTROL Site Sections]** > **[!UICONTROL Site Section Paths]**。

   ![](assets/site_section_path_1.png)

1. 指定适当的日期。
1. 单击 **[!UICONTROL Next]**.
1. 在向导的步骤2中，在下 **[!UICONTROL Row Labels]**&#x200B;面单击链 **[!UICONTROL Top 1-10 (pattern applied)]** 接。 默认情况下，路径报表中已应用模式。

   ![](assets/site_section_path_2.png)

1. 选择 **[!UICONTROL Filter]** 选项。

   ![](assets/filter_option.png)

1. 在对话 **[!UICONTROL Define 'Site Section Paths' Path Pattern]** 框中，可以指定
   1. 第一个报表的起始排名。
   1. 要在此报表中显示的条目数。
1. Click **[!UICONTROL Edit]** to define a path pattern.
1. If you want a custom pattern, drag and drop any **[!UICONTROL Pattern Objects]** from the list on the left into the **[!UICONTROL Pattern Build Canvas]** on the right.

   ![](assets/custom_pattern.png)

1. You can also select a predefined pattern from the **[!UICONTROL Select a Pattern]** drop-down list and modify it. 下面显示了可用的模式：

   ![](assets/select_a_pattern.png)

   其中，某些模式是特定于 Report Builder 的：登入路径的下一项目模式、退出路径的上一项目模式、下一项目模式。
1. 要编辑预定义模式，请执行以下操作：
   1. 选择模式。例如，选择 **[!UICONTROL Exited Site Pattern]**: ![](assets/exited_site_pattern.png)

   1. 现在，您应当定义用户在退出前所遵循的网站区域路径。单击 **[!UICONTROL Specific Item(s): 0 selected]**. 您可以通过从单元格范围（如果您在编辑现有请求）或区域列表进行选择来定义此路径。
   1. To select from a range of cells from a previous request, select **[!UICONTROL From range of cells]** and click the cell selector icon. 然后，从报表中选取单元格。![](assets/choose_site_section_paths.png)

   1. To select from a list of site sections, select **[!UICONTROL From list]** and click **[!UICONTROL Add]**.
   1. Move elements from the **[!UICONTROL Available Elements]** column to the **[!UICONTROL Selected Elements]** column by selecting them and clicking the orange arrow. 单击 **[!UICONTROL OK]**。 ![](assets/move_site_section_elements.png)

   1. To save the pattern you just established, click **[!UICONTROL Save]**.
   1. 单击 **[!UICONTROL OK]** 三次，然后单击 **[!UICONTROL Finish]**。 此时会生成过滤的路径请求。
