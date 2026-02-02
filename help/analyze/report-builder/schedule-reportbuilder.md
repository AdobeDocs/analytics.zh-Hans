---
title: 使用Report Builder计划工作簿
description: 了解如何使用Report Builder中的计划功能。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 40e1feb0-64bc-40e6-83cb-4a1ea7e2d0cc
source-git-commit: 8b6d8a4efec59b693a69984880d8f374ae0cfabc
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 26%

---

# 通过电子邮件共享计划工作簿

>[!NOTE]
>
>除了计划通过电子邮件共享的工作簿外（如本节所述），您还可以计划要导出到云目标的工作簿（如[计划导出到云目标的工作簿](/help/analyze/report-builder/report-builder-export.md)中所述）。

保存工作簿并完成分析后，您可以使用计划功能轻松地与团队中的其他人共享您的工作簿。计划功能允许您创建计划，自动刷新工作簿中的数据，并在特定日期和时间将 Excel 工作簿。xlsx 文件作为附件通过电子邮件发送给指定的受众。设置时间表可为收件人自动提供定期更新。您还可以使用计划功能将工作簿发送一次，而无需计划自动更新。

您可以为单个工作簿创建多个计划。例如，您可以每天向您的团队发送一份工作簿，也可以通过创建两个不同的时间表每周一次将工作簿发送给您的经理。

计划功能还允许您为工作簿设置密码保护并编辑以前计划的工作簿。


>[!BEGINSHADEBOX]

请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [计划工作簿](https://video.tv.adobe.com/v/3417502?captions=chi_hans&quality=12&learn=on){target="_blank"}以观看演示视频。

>[!ENDSHADEBOX]


## 计划工作簿

要计划工作簿，请执行以下操作：

1. 选择Report Builder中心中的&#x200B;**[!UICONTROL 计划]**&#x200B;以创建计划，以便您将工作簿Excel文件(.xlsx)自动分发给个人或组。

   ![选择“计划”按钮以创建计划。](./assets/schedule.png){zoomable="yes"}

1. 选择&#x200B;**[!UICONTROL 计划工作簿]**&#x200B;或![添加](/help/assets/icons/Add.svg)以创建新的计划工作簿。

   ![计划工作簿窗口。](./assets/schedule-workbook.png){zoomable="yes"}

   计划窗格显示有关工作簿的一些预定义信息，例如工作簿名称和修改工作簿的最后日期。

### 文件

在&#x200B;**[!UICONTROL 文件]**&#x200B;部分中，您提供了文件类型、名称和密码的详细信息以保护文件。

![计划窗格。](./assets/schedule-pane.png){zoomable="yes"}

1. 使用![TableSelect](/help/assets/icons/TableSelect.svg)选择当前工作簿（如果尚未选择）。

1. （可选）输入&#x200B;**[!UICONTROL 文件名]**。

   工作簿文件名默认为工作簿的名称，但您可以根据需要更改文件名。

1. 选择&#x200B;**[!UICONTROL 文件类型]**。

   * **[!UICONTROL Excel]**
   * **[!UICONTROL PDF]**
   * **[!UICONTROL CSV]**

   选择&#x200B;**[!UICONTROL CSV]**&#x200B;时，请注意，计划工作簿是作为zip附件发送的。 某些公司电子邮件管理部门可能会阻止包含zip附件的电子邮件。 您会看到相应的警告。

1. （可选）选择&#x200B;**[!UICONTROL 将时间戳附加到文件名]**。

   您可以将时间戳附加到文件名以标识工作簿的更新日期。时间戳有助于查看在特定日期发送的工作簿版本。 选中后，您可以选择以下选项：

   * **[!UICONTROL ISO日期格式]**，这会导致`YYYY-MM-DD`被附加到文件名中。
   * **[!UICONTROL ISO日期格式+时间戳]**，这会导致`YYYY-MM-DD_HH-MM-SS`被附加到文件名中。

<!-- Does no longer seem to be an option? 
1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){zoomable="yes"}{width="55%"}
-->

1. 在&#x200B;**[!UICONTROL 密码保护工作簿]**&#x200B;中输入密码。 有效密码至少需要8个字符、一个数字和一个特殊字符。 选择![VisibilityOff](/help/assets/icons/VisibilityOff.svg)以显示密码，选择![Visibility](/help/assets/icons/Visibility.svg)隐藏密码（默认）。


### 电子邮件

在&#x200B;**[!UICONTROL 电子邮件]**&#x200B;部分中，提供电子邮件的收件人、主题和描述。

![计划电子邮件设置](assets/schedule-email.png){zoomable="yes"}

1. **输入收件人**。您可以输入组织中可识别的人员的姓名。 或者，您可以输入组织外部人员的电子邮件地址。

1. 输入电子邮件的&#x200B;**主题**&#x200B;和对收件人的描述。主题默认为工作簿文件名，但您可以根据需要修改主题。您可以在描述部分添加详细信息。

1. 您可以选择在&#x200B;**[!UICONTROL 描述]**&#x200B;文本区域中输入描述。


### 计划

在&#x200B;**[!UICONTROL 计划]**&#x200B;部分中，您可以定义将带有工作簿的电子邮件发送给收件人的计划。

![计划定义](assets/schedule-enable.png){zoomable="yes"}

1. 选择&#x200B;**[!UICONTROL 显示计划选项]**&#x200B;以定义计划。

1. 输入从&#x200B;**[!UICONTROL 开始的]**&#x200B;开始日期。 或者，选择![日历](/help/assets/icons/Calendar.svg)以从日历中选择开始日期。

1. 在&#x200B;**[!UICONTROL 结束日期]**&#x200B;中输入结束日期。 或者，选择![日历](/help/assets/icons/Calendar.svg)以从日历中选择结束日期。

1. 选择&#x200B;**[!UICONTROL 频率]**。 根据所选的频率，您还有其他选项。 请参阅下表。

   | 频率 | 选项 |
   |---|---|
   | **[!UICONTROL 每小时发送]** | 为&#x200B;**[!UICONTROL 发送间隔小时数]**&#x200B;输入一个值。 |
   | **[!UICONTROL 每日发送]** | 选择&#x200B;**[!UICONTROL 每日频率]**：**[!UICONTROL 每天发送]**、**[!UICONTROL 每个工作日发送]**&#x200B;或&#x200B;**[!UICONTROL 自定义频率]**。<br/>如果您选择&#x200B;**[!UICONTROL 自定义频率]**，请为&#x200B;**[!UICONTROL 发送间隔天数]**&#x200B;输入一个值。 |
   | **[!UICONTROL 每周发送]** | 为&#x200B;**[!UICONTROL 发送间隔周数]**&#x200B;输入一个值。 并选择一周中的&#x200B;**[!UICONTROL 天]**。 |
   | **[!UICONTROL 按星期几发送月报表]** | 选择&#x200B;**[!UICONTROL 周中某天]**&#x200B;和&#x200B;**[!UICONTROL 月中某周]**。 |
   | **[!UICONTROL 每月按月发送]** | 从&#x200B;**[!UICONTROL 发送日期]**&#x200B;中选择一个值。 |
   | **[!UICONTROL 按月份中的日期每年发送]** | 选择&#x200B;**[!UICONTROL 周中日]**，选择&#x200B;**[!UICONTROL 月中周]**，然后选择&#x200B;**[!UICONTROL 月中月]**。 |
   | **[!UICONTROL 按特定日期每年发送]** | 选择&#x200B;**[!UICONTROL 月份]**&#x200B;并从&#x200B;**[!UICONTROL 发送日期]**&#x200B;中选择一个值。 |

### 发送

要发送工作簿，请执行以下操作：

* 如果您尚未使用&#x200B;**[!UICONTROL 显示计划选项]**&#x200B;定义计划，请选择&#x200B;**[!UICONTROL 立即发送]**&#x200B;以立即通过电子邮件发送工作簿。
* 如果您使用&#x200B;**[!UICONTROL 显示计划选项]**&#x200B;定义了计划，请选择&#x200B;**[!UICONTROL 按计划发送]**，以使用您定义的计划通过电子邮件发送工作簿。

在这两种情况下，您都会在Report Builder中心底部看到一个确认吐司。

若要取消发送工作簿，请选择&#x200B;**[!UICONTROL 取消]**。

## 管理已安排的工作簿

有关管理已计划工作簿的信息，请参阅[管理计划的工作簿](/help/analyze/report-builder/manage-reportbuilder.md)。




<!--

## Schedule a workbook

Use the Schedule button in the Report Builder hub to quickly create a schedule so that you can automatically distribute a workbook Excel file (.xlsx) to an individual or a group.

1. Click the Schedule button in the Report Builder hub.

    ![Click the Schedule button to create a schedule.](./assets/schedule-button.png){width="55%"}

1. Click Schedule Workbook or the plus button in the upper-left to create a new scheduled workbook.

    ![The Schedule workbooks window.](./assets/schedule-workbook.png){width="55%"}

    The scheduling pane displays some pre-defined information about the workbook such as the workbook name and the last date that the workbook was modified.

    ![The scheduling pane.](./assets/schedule-pane.png){width="55%"}

1. (Optional) Enter a file name.

    The workbook file name defaults to the name of the workbook but you can change this if you want. If you\'re sending the same workbook to multiple audiences and you want to name it something a little bit more friendly for a certain audience, you can change the name.

1. (Optional) Select **Append time-stamp to file name**.

    You can append a timestamp to the file name to identify the date the workbook was updated. This is helpful to quickly see which version of a workbook was sent on a specific date. The **Filename preview** shows how the workbook file name will appear in the email when the workbook is distributed. The time-stamp format is YYYY-MM-DD.

1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){width="55%"}

1. Enter **Recipients**. You can enter the name of a person that is recognized in your organization, or you can enter an email address of a person inside or outside of your organization.

1. Enter the **Subject** of the email and a description for your recipients. The subject defaults to the workbook file name but you can modify the subject if needed. You can add details in the description section.

    ![Enter a subject in the Subject field.](./assets/recipients-subject.png){width="55%"}

1. Set up the scheduling options to set the date and time that you want the workbook emailed to your recipients.

    Choose the start and end date and time frames. This can be today's date or a date in the future.

    Choose the **Frequency** from the drop-down menu. You can set the frequency to be hourly, daily, weekly, monthly, or yearly on a specific day. For example, you can set up a schedule to send the workbook on the first Sunday night of the month so that your recipients will have the email in their inbox first thing on Monday morning.

    ![Select the frequency to schedule your report.](./assets/frequency.png){width="55%"}

1. After you set the schedule, click **Send on schedule**.

    ![Click Send on schedule.](./assets/send-on-schedule.png){width="55%"}

    You see a confirmation toast at the bottom of the Report Builder hub and the scheduled workbook is listed under the Workbooks tab.

    ![Confirmation toast](./assets/confirmation-toast.png){width="55%"}

## Schedule a converted workbook {#converted}

1. Schedule a [converted](/help/analyze/report-builder/convert-workbooks.md) legacy workbook.

   A pop up appears, asking if you want to use the scheduling metada from the legacy workbook to create a new scheduled task. 

1. If you select **[!UICONTROL Use]**, Report Builder automatically fills in the legacy scheduling information. 

1. Ensure that this information is correct and schedule. 

1. If you want to send the workbook on a different schedule, schedule a completely fresh scheduled task. 


## Send the workbook one-time only

You can also send out the workbook only once.

1. Un-check **Show scheduling options** 

    ![Click Un-check Show scheduling options to send out a workbook one time.](./assets/send-now.png){width="40%"}

1. Click **Send Now**.

## Manage scheduled workbooks

For information about managing workbooks that are already scheduled, see [Manage scheduled workbooks](/help/analyze/report-builder/manage-schedules-reportbuilder.md).

-->