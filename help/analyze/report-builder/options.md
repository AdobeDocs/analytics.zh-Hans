---
description: 在“选项”面板中，您可以指定日期设置、延迟设置（“当前数据”）和日志信息，还可以配置更新。
title: Report Builder 选项
topic: Report builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Report Builder 选项

在“选项”面板中，您可以指定日期设置、延迟设置（“当前数据”）和日志信息，还可以配置更新。

1. In the Add-Ins toolbar, click **[!UICONTROL Options]** ![](assets/options_icon.png):

| 元素 | 描述 |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| 设置为当前日期 | Lets you specify or reset the  [!UICONTROL As Of Date] so that report builder uses the current date or asks you which date to use upon refresh. |
| 提示我在刷新时设置 | 允许您在刷新请 [!UICONTROL As Of Date] 求时设置。 |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Lets you view data latency (also known as  [!UICONTROL Data Recency]) down to the minute in reporting, occasionally even before this data has been processed by  Adobe Analytics.<br>如果不使用此选项，则应用已完成模式（已处理），此模式通常具有更长的[延迟时间](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/current-data.html)。<br>此设置适用于工作簿中与“当前数据”兼容的所有请求。如果该请求不兼容，将应用已完成模式。<br>请注意以下情况以使用模 [!UICONTROL Include Current Data] 式：格式<br>**选项&#x200B;**:您可以指定在设置显示标题的格式[!UICONTROL Data Recency]时是否[显示此信息](/help/analyze/report-builder/layout/t-format-display-headers.md)。<br>**划分**：不支持。If the  [!UICONTROL Data Recency] mode is set to the Current Data, and one of the requests contains a break-down element, this request reverts to non-current data mode. 然而，其他请求仍将继续使用“当前数据”模式。<br>**请求管理器&#x200B;**：您可以在请求管理器中查看“当前数据”列，这样就可以看到该设置是否已应用于计划的请求。<br>**计划的工作簿**：在工作簿级别的计划过程中会存储此模式。If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**权限&#x200B;**：对于没有权限访问当前数据的用户，此选项是隐藏的。当启用此选项时，如果无法应用一个或多个请求，将发出警告。 |
| 禁用与“当前数据”不兼容的请求的警告 | Displays warnings if the  [!UICONTROL Include Current Data] mode is selected but the data mode cannot be applied to the edited request.  For example, if you set [!UICONTROL Include Current Data], and then edit a request that has a segment selected, a warning is issued. |
| 将 Report Builder 请求记录到本地文件（用于疑难解答） | 可让您将请求记录到本地文件。使用该日志文件进行疑难解答。 |
| 解析键入的值... | 请先将过滤器控件中键入的值解析为单元格位置，然后再将其视为过滤器表达式。<br>例如，如果您使用鞋过滤器创建一个“前 10 页”的请求，则该请求将显示一个包含类似于以下内容的单元格：过滤器：前 1-10 页，页面包含鞋 |
| 在有新版本时进行更新 | 让系统在有新版本可供安装时通知您。 |
