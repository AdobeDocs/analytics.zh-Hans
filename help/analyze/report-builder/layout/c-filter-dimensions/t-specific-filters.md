---
description: 应用特定维度词的过滤器。
title: 特定过滤器
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: User, Admin
exl-id: e5f2d67c-3add-4d51-8a76-ee3b2a6eef94
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 91%

---

# 特定过滤器

应用特定维度词的过滤器。

通过创建符合严密条件的过滤器，您可以搜索特定维度项目。例如，您可以创建以下类型的过滤器：[!DNL homepage.htm]、[!DNL contact_us.html]、[!DNL corporate_info.html] 中的页面。

**创建特定过滤器**

1. 创建或编辑请求，然后进入“[!UICONTROL 请求向导: 第 2 步]”。

   ![屏幕截图显示按下列选项进行筛选：“应用程序”、“用户”和“项目”。](/help/admin/admin/assets/filter.png)

1. 在“[!UICONTROL 请求向导: 第 2 步]”中，单击网格中维度旁边的链接，然后选择&#x200B;**[!UICONTROL 过滤器]**。

1. 启用&#x200B;**[!UICONTROL 特定]**。

   ![选择“特定”选项的“选择页面”对话框屏幕截图。](assets/choose_page_specific01.png)

1. 启用以下特定选项之一：

   * **来自单元格范围：**&#x200B;允许您从单元格中选择数据。您可以选择︰
      * **范围中的所有单元格：**&#x200B;允许您映射范围中的每个单元格。描述性文本解释您必须选择多少组单元格。要映射多组单元格，请在按住 Ctrl 键的同时进行连续选择。如果必须映射的范围仅包含一个单元格，那么只能使用此选项。
      * **范围的第 1 个单元格：**&#x200B;只需选择范围中左上角的单元格，然后选择数据方向即可。此外，如果请求包含多个时段，则需要选择时段的方向并选择是否要在两个时段之间跳过一定的单元格数。
   * **来自列表：**&#x200B;允许您从列表中选择数据，您可以向列表中添加数据。
1. 如果启用&#x200B;**[!UICONTROL 来自列表]**，请选择列出的任意可用项目，或者单击&#x200B;**[!UICONTROL 添加]**。

   单击&#x200B;**[!UICONTROL 添加]**&#x200B;时，[!UICONTROL 从列表中选择]窗体会显示当前请求日期范围的可用维度项列表（仅限前 10,000 项）。 您可以在这些项中搜索，或者单击&#x200B;**[!UICONTROL 更多...]**，这样会显示[!UICONTROL 搜索窗体]，以便您可以创建更详细的维度搜索条件。
1. 在“[!UICONTROL 从列表中选择]”中，单击&#x200B;**[!UICONTROL 确定]**。
1. 在“[!UICONTROL 选择页面]”窗体中，保存您的特定过滤器（如果需要），然后单击&#x200B;**[!UICONTROL 确定]**。
