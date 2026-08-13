---
description: 使用 AND/OR 搜索表达式通过布尔逻辑配置的排名和条件过滤器。
title: 最受欢迎的过滤设置
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
feature: Report Builder
role: User, Admin
exl-id: 31587740-6caa-40cb-bb24-d7a15181f642
TQID: https://experienceleague.adobe.com/TLo2RytIM7ZQlpFMqXsTdoz7vFAXnwqoTJGHDG7gWLg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 633
ht-degree: 33%

---

# 最受欢迎的过滤设置

{{legacy-arb}}

使用 AND/OR 搜索表达式通过布尔逻辑配置的排名和条件过滤器。

最受欢迎的过滤器是使用 AND/OR 条件通过布尔逻辑配置的表达式过滤器，如使用[!UICONTROL 包括全部]、[!UICONTROL 包括任何]或[!UICONTROL 排除所有]等条件或条件组的[!UICONTROL 页面不包含&#x200B;]*`<product name>`*。 您可以[保存](/help/analyze/legacy-report-builder/layout/c-filter-dimensions/saved-filters.md)这些表达式，供此工作簿或其他工作簿中的其他请求使用。

**创建最受欢迎的过滤器**

1. 创建或编辑请求，然后进入“[!UICONTROL 请求向导: 第 2 步]”。

1. 在“[!UICONTROL 请求向导: 第 2 步]”中，单击网格中维度旁边的链接，然后选择&#x200B;**[!UICONTROL 过滤器]**。

   ![屏幕截图显示“定义筛选器”对话框，其中包含按应用程序、用户和项目筛选的选项。](/help/admin/tools/assets/filter.png)

1. 在“[!UICONTROL 选择页面]”窗体中，启用&#x200B;**[!UICONTROL 最受欢迎]**，然后配置下列选项：

   **起始排名：**&#x200B;维度的起始排名。 默认排名1表示报告的数据列表中的排名最前的项目。 例如，对于维度[!UICONTROL Page]，起始标记为1表示您网站中请求次数最多的单个页面。 您可以指定10或其他值作为起始排名单元格，这将生成以10开头为最高值的报表。 量度按降序排列，以便具有最大活动的行项目首先在列表中报告。 如果您在一个请求中需要超过50,000个页面名称，但具有数千个要报告的页面，则可以复制请求并更改起始排名，以按50,000的块检索适当数据。

   **条目数：**（仅[!UICONTROL 引导布局]）定义针对特定量度在某日期范围内报告的项目数。 某些量度可能会列出数百个量度条目，而其他量度可能只显示几个。 例如，对于维度[!UICONTROL 网站区域]，如果条目数为25，则表明报表显示了25个访问次数最多的页面。

   箭头允许您更改工作表中第一个数据点的[!UICONTROL 起始排名]和[!UICONTROL 条目数]。 默认情况下，[!UICONTROL 起始排名]设置为1，[!UICONTROL 条目数]设置为10。 对于某些量度，这些值可从最小值1到最大值50,000进行调整。 每个量度在[!UICONTROL 条目数]上都有各自的上限。 这些字段中不允许负值或零。 如果您选择[!UICONTROL 起始排名]为15，[!UICONTROL 条目数]为10，则该量度的数据请求将返回访问次数最多的10个页面，其中访问次数最多的第一个页面是特定日期范围列表中的第15个页面。 请求次数最多的所有页面排名第15到25位，按降序排列。

   >[!NOTE]
   >
   >对现有请求应用过滤器会导致提供的数据发生变化。 假设您将前10个[!UICONTROL 页面]映射到单元格$A$1到$A$10，其中1表示[!UICONTROL 起始排名]，10表示[!UICONTROL 条目数]。 如果您将这些值更改为[!UICONTROL 起始排名]显示1，而[!UICONTROL 条目数]仅显示3，则以前填充单元格$A$4到$A$10的数据将不再显示。

1. 要创建搜索表达式，请单击&#x200B;**[!UICONTROL 添加]**。

1. 在“[!UICONTROL 定义过滤器]”窗体中，根据您的需要配置条件。


   ![显示“定义筛选器”对话框的屏幕截图。](assets/expressions_define_filter.png)

   使用选择单元格图标，可查找在单元格值中定义的条件。 ![选择单元格图标。](assets/select_cell_icon.png)

   **添加条件**&#x200B;链接允许您向表达式添加条件。 可添加的条件数没有限制。

1. 单击&#x200B;**[!UICONTROL 确定]**。

   ![右下角显示“定义过滤器”对话框“确定”按钮的屏幕截图。](assets/choose_page_02.png)

1. 在“[!UICONTROL 选择页面]”窗体上，单击&#x200B;**[!UICONTROL 保存]**&#x200B;以保存表达式。
1. 单击&#x200B;**[!UICONTROL 确定]**。
