---
description: 了解Report Builder选项。
title: 关于Report Builder选项
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: User, Admin
exl-id: d3388990-7919-461d-a96e-4c996b8bdb8b
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 88%

---

# Report Builder 选项

{{legacy-arb}}

在“选项”面板中，您可以指定日期设置、延迟设置（“当前数据”）和日志信息，还可以配置更新。

1. 在“加载项”工具栏中，单击&#x200B;**[!UICONTROL 选项]** ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)：

| 元素 | 描述 |
|--- |--- |
| [!UICONTROL 截止日期] |  |
| 设置为当前日期 | 可让您指定或重置[!UICONTROL 截止日期]，以便Report Builder使用当前日期或在刷新时询问您要使用的日期。 |
| 提示我在刷新时设置 | 可让您在刷新请求时设置[!UICONTROL 截止日期]。 |
| [!UICONTROL 数据新近度] |  |
| [!UICONTROL 包括当前数据] | 可让您在报表中查看精确到分钟的数据延迟（也称为“[!UICONTROL 数据新近度]”），有时甚至在 Adobe Analytics 处理此数据之前。<br>如果不使用此选项，则应用已完成模式（已处理），此模式通常具有更长的[延迟时间](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=zh-Hans)。<br>此设置适用于工作簿中与“当前数据”兼容的所有请求。如果该请求不兼容，将应用已完成模式。<br>请注意以下使用[!UICONTROL 包括当前数据]模式的情况：<br>**格式选项**：您可以在[设置显示标题的格式](/help/analyze/legacy-report-builder/layout/t-format-display-headers.md)时，指定是否显示此信息（[!UICONTROL 数据新近度]）。<br>**划分**：不支持。如果“[!UICONTROL 数据新近度]”模式设置为“当前数据”，并且其中一个请求包含了划分元素，该请求将还原为非当前数据模式。然而，其他请求仍将继续使用“当前数据”模式。<br>**请求管理器**：您可以在请求管理器中查看“当前数据”列，这样就可以看到该设置是否已应用于计划的请求。<br>**计划的工作簿**：在工作簿级别的计划过程中会存储此模式。如果您打开一个使用已完成数据的计划工作簿，并应用[!UICONTROL 包括当前数据]，则以后将使用当前模式。<br>**权限**：对于没有权限访问当前数据的用户，此选项是隐藏的。当启用此选项时，如果无法应用一个或多个请求，将发出警告。 |
| 禁用与“当前数据”不兼容的请求的警告 | 如果选择“[!UICONTROL 包括当前数据]”模式，但无法将该数据模式应用于已编辑的请求，就会显示警告。例如，如果您设置“[!UICONTROL 包括当前数据]”，然后编辑一个含有选中区段的请求，将发出警告。 |
| 将Report Builder请求记录到本地文件（用于疑难解答） | 可让您将请求记录到本地文件。使用该日志文件进行疑难解答。 |
| 解析键入的值... | 请先将过滤器控件中键入的值解析为单元格位置，然后再将其视为过滤器表达式。<br>例如，如果您使用鞋过滤器创建一个“前 10 页”的请求，则该请求将显示一个包含类似于以下内容的单元格：过滤器：前 1-10 页，页面包含鞋 |
| 在有新版本时进行更新 | 让系统在有新版本可供安装时通知您。 |
