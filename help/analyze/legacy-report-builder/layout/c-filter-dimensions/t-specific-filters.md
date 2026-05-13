---
description: 应用特定维度词的过滤器。
title: 特定过滤条件
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: User, Admin
exl-id: e5f2d67c-3add-4d51-8a76-ee3b2a6eef94
TQID: https://experienceleague.adobe.com/yNIeTJwwWtjXkbi47lX1Ve-Rbz6lF1PazD4YxxXa0Ac
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 336
ht-degree: 46%

---

# 特定过滤条件

{{legacy-arb}}

应用特定维度词的过滤器。

您可以通过创建与精确条件匹配的过滤器来搜索特定维度项。 例如，您可以创建以下类型的过滤器：[!DNL homepage.htm]、[!DNL contact_us.html]、[!DNL corporate_info.html] 中的页面。

**创建特定过滤器**

1. 创建或编辑请求，然后进入“[!UICONTROL 请求向导: 第 2 步]”。

   ![屏幕截图显示按下列选项进行筛选：“应用程序”、“用户”和“项目”。](/help/admin/tools/assets/filter.png)

1. 在“[!UICONTROL 请求向导: 第 2 步]”中，单击网格中维度旁边的链接，然后选择&#x200B;**[!UICONTROL 过滤器]**。

1. 启用&#x200B;**[!UICONTROL 特定]**。

   ![选择“特定”选项的“选择页面”对话框屏幕截图。](assets/choose_page_specific01.png)

1. 启用以下特定选项之一：

   * **从单元格范围：**&#x200B;允许您从单元格中选择数据。 您可以选择︰
      * **范围**&#x200B;中的所有单元格允许您映射该范围的每个单元格。 描述性文本说明必须选择多少组单元格。 要映射多个单元格组，请在进行连续选择时按Ctrl键。 如果必须映射的范围只包含一个单元格，则这是唯一可用的选项
      * **范围的第一个单元格：**&#x200B;您只需选择范围左上角的单元格，然后为数据选择方向。 此外，如果请求具有多个期间，您可以选择期间的方向，并选择是否要在期间之间跳过设置的单元格数。
   * **从列表：**&#x200B;允许您从可向其添加数据的列表中选择数据。
1. 如果启用&#x200B;**[!UICONTROL 来自列表]**，请选择列出的任意可用项目，或者单击&#x200B;**[!UICONTROL 添加]**。

   单击&#x200B;**[!UICONTROL 添加]**&#x200B;时，[!UICONTROL 从列表中选择]窗体会显示当前请求日期范围的可用维度项列表（仅限前 10,000 项）。 您可以在这些项中搜索，或者单击&#x200B;**[!UICONTROL 更多...]**，这样会显示[!UICONTROL 搜索窗体]，以便您可以创建更详细的维度搜索条件。
1. 在“[!UICONTROL 从列表中选择]”中，单击&#x200B;**[!UICONTROL 确定]**。
1. 在“[!UICONTROL 选择页面]”窗体中，保存您的特定过滤器（如果需要），然后单击&#x200B;**[!UICONTROL 确定]**。
