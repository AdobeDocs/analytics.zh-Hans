---
title: 配置Report Builder的设置
description: 了解如何配置Report Builder的设置。
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 28%

---

# Report Builder 设置


使用&#x200B;**设置**&#x200B;窗格可以配置应用程序级别的设置，例如 UI 显示的语言或者是否在离线模式下工作。这些设置会立即应用，并设定用于所有未来的会话，直至发生更改。

更改 Report Builder 设置

1. 选择&#x200B;**设置**&#x200B;图标。

1. 更改[启用离线模式](#off-line-mode)、[选择语言](#language)或[启用故障排除](#troubleshooting)。

1. 选择&#x200B;**[!UICONTROL 应用]**。

   显示“取消并应用”按钮的![Report Builder日期范围窗格。](./assets/report-builder-settings.png){zoomable="yes"}

## 离线模式

在离线模式下创建和编辑数据块时，不会检索数据。 相反，会使用模拟数据，以便您可以快速工作，而无需等待请求运行。 当您重新联机时，请选择![刷新](/help/assets/icons/Refresh.svg) **[!UICONTROL 刷新数据块]**&#x200B;或![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL 刷新所有数据块]**&#x200B;以使用实际数据刷新数据块。

启用离线模式

1. 选择![设置](/help/assets/icons/Setting.svg)。

1. 打开&#x200B;**[!UICONTROL 启用离线模式]**。

1. 在&#x200B;**[!UICONTROL 将量度数据]**&#x200B;显示为字段中输入正整数。

1. 选择&#x200B;**[!UICONTROL 应用]**。


## 语言

您可以为Report Builder界面选择语言。 所有受支持的Customer Journey Analytics语言均可用。

要选择Report Builder界面中使用的语言，请执行以下操作：

1. 从&#x200B;**[!UICONTROL 语言]**&#x200B;下拉菜单中选择一种语言。

1. 选择&#x200B;**应用。**

## 故障排除

**[!UICONTROL 疑难解答日志]**&#x200B;设置将所有客户端/服务器数据记录到本地文件。 使用此选项帮助解决支持服务单。

要启用故障排除日志，请选中&#x200B;**[!UICONTROL 将Report Builder请求记录到本地文件]**。

<!--
Use the **Settings** pane to configure application-level settings such as the language displayed by the UI or whether or not to work in off-line mode. The settings are applied immediately and they are set for all future sessions until they're changed.

To change Report Builder settings

1. Click the **Settings** icon.

1. Make changes to Enable off-line mode, select a Language, or enable Troubleshooting log settings.

1. Click **Apply**.

    ![Report Builder settings.](./assets/image38.png)

## Off-line mode

When creating and editing a data block in off-line mode, data is not retrieved. Instead, simulation data is used so that you can quickly create and edit a data block without waiting for the request to run. When you are back online, the *Refresh data block* command or *Refresh all data blocks* command refreshes the data blocks that you created with actual data.

To enable off-line mode

1. Click the **[!UICONTROL Settings]** icon.

1. Select **[!UICONTROL Enable off-line mod]e**.

1. Enter a positive integer in the **[!UICONTROL Display metric data as]** field.

1. Click **[!UICONTROL Apply]**.

## Language

You can choose the language for the Report Builder UI. All supported Adobe Analytics languages are available.

To select the language used in the Report Builder UI

 1. Click Settings.

 1. Select a language from the **[!UICONTROL Language]** drop down menu.

     ![Report Builder date range pane showing the Language list with English selected.](./assets/image39.png)

 1. Click **[!UICONTROL Apply].**

## Troubleshooting

Use the Troubleshooting setting to log all client/server data to a local file. Use this option to help resolve support tickets.

To enable the Troubleshooting option, select **[!UICONTROL Log report builder data block to web console]**.
-->