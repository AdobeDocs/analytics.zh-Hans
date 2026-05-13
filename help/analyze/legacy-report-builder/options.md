---
description: 了解Report Builder选项。
title: 关于Report Builder选项
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: User, Admin
exl-id: d3388990-7919-461d-a96e-4c996b8bdb8b
TQID: https://experienceleague.adobe.com/56Wyy-f9kDXxFSanTNILr4rNQ0OB3YtbIFPcRT082sc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 39%

---

# Report Builder 选项

{{legacy-arb}}

在“选项”面板中，您可以指定日期设置、延迟设置（“当前数据”）和日志信息，还可以配置更新。

1. 在“加载项”工具栏中，单击&#x200B;**[!UICONTROL 选项]** ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)：

| 元素 | 描述 |
|--- |--- |
| [!UICONTROL 截止日期] |  |
| 设置为当前日期 | 可让您指定或重置[!UICONTROL 截止日期]，以便Report Builder使用当前日期或者在刷新时询问您要使用的日期。 |
| 提示我在刷新时设置 | 可让您在刷新请求时设置[!UICONTROL 截止日期]。 |
| [!UICONTROL 数据新近度] |  |
| [!UICONTROL 包括当前数据] | 可让您在报表中查看精确到分钟的数据延迟（也称为[!UICONTROL 数据新近度]），有时甚至在Adobe Analytics处理此数据之前。<br>如果不使用此选项，则使用已完成模式（已处理），此模式通常具有更长的延迟时间。<br>此设置适用于工作簿中与“当前数据”兼容的所有请求。 如果该请求不兼容，将应用已完成模式。<br>请注意以下使用[!UICONTROL 包括当前数据]模式的情况：<br>**格式选项**：您可以指定在[设置显示标题的格式](/help/analyze/legacy-report-builder/layout/t-format-display-headers.md)时，是否显示此信息（[!UICONTROL 数据新近度]）。<br>**划分**：不支持。 如果“[!UICONTROL 数据新近度]”模式设置为“当前数据”，并且其中一个请求包含了划分元素，该请求将还原为非当前数据模式。 但是，其他请求仍继续使用“当前数据”模式。<br>**请求管理器**：您可以在请求管理器中查看“当前数据”列，以便查看设置是否已应用于计划请求。<br>**计划工作簿**：在计划流程期间在工作簿级别存储此模式。 如果您打开一个使用已完成数据的计划工作簿，并应用了[!UICONTROL 包括当前数据]，则以后将使用当前模式。<br>**权限**：对于无权访问当前数据的用户，此选项是隐藏的。  启用此选项时，如果无法应用一个或多个请求，则会发出警告。 |
| 禁用当前数据不兼容的请求警告 | 如果选择“[!UICONTROL 包括当前数据]”模式，但无法将该数据模式应用于已编辑的请求，就会显示警告。  例如，如果您设置“[!UICONTROL 包括当前数据]”，然后编辑一个含有选中区段的请求，将发出警告。 |
| 将Report Builder请求记录到本地文件（用于疑难解答） | 允许您将请求记录到本地文件。 使用此日志文件进行故障排除。 |
| 解释键入的值…… | 将筛选器控件中的键入值解释为单元格位置，然后再将其视为筛选器表达式。<br>例如，如果您使用鞋过滤器创建一个“前 10 页”的请求，则该请求将显示一个包含类似于以下内容的单元格：过滤器：前 1-10 页，页面包含鞋 |
| 在有新版本时更新 | 通知系统是否有新版本可供安装。 |
