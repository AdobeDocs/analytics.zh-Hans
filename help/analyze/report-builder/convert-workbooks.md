---
title: 转换旧版Report Builder工作簿
description: 了解如何将旧版Report Builder工作簿迁移并转换为新的Report Builder。 按照本迁移指南中的分步说明，了解如何无缝转换基于Adobe Analytics的工作簿。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 9743d7ac2a6c7e63d7a6701e60d05683c5680d36
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 0%

---

# 转换旧版Report Builder工作簿

旧版Report Builder将于2026年6月终止生命周期。 您应该将工作簿从旧版Report Builder迁移到新Report Builder。 新的Report Builder提供了一种便捷的方式来快速迁移使用旧版Report Builder创建的工作簿。

>[!IMPORTANT]
>
>在转换旧版工作簿之前，请复制每个工作簿并重命名一个版本。 确保在需要时始终保留原始旧工作簿的副本。


>[!BEGINSHADEBOX]

请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [转换工作簿](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/exporting/report-builder/upgrade-and-reschedule-workbooks){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]


>[!NOTE]
>
>若要转换旧版工作簿，您必须先设置[新的Report Builder](/help/analyze/report-builder/report-builder-setup.md)。


## 打开旧工作簿

要打开旧工作簿，您可以：

* 从&#x200B;**[!UICONTROL Report Builder中心]**&#x200B;的[计划](report-builder-hub.md)选项卡中打开计划的旧工作簿。 此操作是计划旧版工作簿的首选方法。 您可以选择在[计划转换的旧工作簿后，立即使用与旧工作簿关联的计划](#schedule-a-converted-legacy-workbook)。

   1. 打开[!DNL Excel]并从![功能区栏中选择](/help/assets/icons/AdobeLogoRedOnWhite.svg)AdobeLogoRedonWhite **** Report Builder[!DNL Excel]。

   1. 选择&#x200B;**[!UICONTROL 登录]**&#x200B;并登录到Report Builder。

   1. 在&#x200B;**[!UICONTROL Report Builder中心]**&#x200B;中选择[计划](report-builder-hub.md)。
   1. 选择&#x200B;**[!UICONTROL 旧版]**&#x200B;选项卡。 选项卡列出了您创建的基于Report Builder的旧版计划工作簿。

      ![旧版工作台](assets/upgrade-legacy-schedule.png)

   1. 从列表中选择![SelectBox](/help/assets/icons/SelectBox.svg)要转换的计划工作簿，然后选择![下载](/help/assets/icons/Download.svg)。 在[!DNL Excel]中下载工作簿并在新窗口中打开。 您现在可以[转换旧版Report Builder工作簿](#convert-a--workbook)。


* 直接从本地计算机或网络打开旧工作簿。 使用此方法时，不提供使用可能与旧版工作簿关联的计划。 <br/>在[!DNL Excel]中打开旧工作簿时：

   1. 从![功能区栏中选择](/help/assets/icons/AdobeLogoRedOnWhite.svg)AdobeLogoRedOnWhite **** Report Builder[!DNL Excel]。
   1. 选择&#x200B;**[!UICONTROL 登录]**&#x200B;并登录到Report Builder。
   1. 然后[转换旧工作簿](#convert-a-workbook)。


## 转换旧工作簿

要转换旧工作簿，请执行以下操作：

1. 打开旧工作簿后，新的Report Builder将检测此工作簿是否包含[旧版Report Builder](/help/analyze/legacy-report-builder/home.md)请求。

   ![显示迁移升级的[!DNL Excel] Report Builder升级报告屏幕截图](assets/upgrade-workbook.png){zoomable="yes"}

1. 如果找到一个或多个旧请求，请单击&#x200B;**[!UICONTROL 升级工作簿]**&#x200B;对话框中的&#x200B;**[!UICONTROL 升级]**&#x200B;以升级工作簿。

   >[!NOTE]
   >
   >您必须单独升级每个请求。 不支持批量升级。


1. 升级时出现&#x200B;**[!UICONTROL 警告]**&#x200B;对话框，提醒您对工作簿的更改。 它还敦促您在继续之前创建旧工作簿的备份。

   ![显示迁移警告的[!DNL Excel] Report Builder升级报告屏幕截图](assets/upgrade-warning.png){zoomable="yes"}

1. 单击&#x200B;**[!UICONTROL 继续]**&#x200B;以继续升级。

   如果升级成功，则显示&#x200B;**[!UICONTROL 工作簿升级现已完成]**&#x200B;通知。

   ![显示迁移已完成的[!DNL Excel] Report Builder升级报告的屏幕截图](assets/upgrade-complete.png)

   * 选择&#x200B;**[!UICONTROL 关闭]**&#x200B;以关闭通知，并继续使用包含新Report Builder更新请求的工作簿。

   * 选择&#x200B;**[!UICONTROL 下载升级报告]**&#x200B;以下载并打开显示升级结果的新[!DNL Excel]工作簿。 有关示例，请参见下文。

     ![显示迁移报告的[!DNL Excel] Report Builder升级报告屏幕截图](assets/upgrade-report.png)

您现在可以[管理工作簿中的数据块](/help/analyze/report-builder/manage-reportbuilder.md)。 这些数据块是升级的结果，它们将替换您的旧版Report Builder请求。


## 计划转换的旧工作簿

您可以选择使用从Report Builder中心的&#x200B;**[!UICONTROL 计划]**&#x200B;选项卡下载和打开的旧版工作簿的计划详细信息。 此选项不适用于具有从本地计算机或网络打开的计划详细信息的旧版工作簿。

1. 要计划使用旧版计划转换的旧版工作簿，请执行以下操作：

   * 从Report Builder中心选择&#x200B;**[!UICONTROL 发送工作簿]**，或者
   * 从Report Builder的&#x200B;**[!UICONTROL 计划]**&#x200B;选项卡中提供的&#x200B;**[!UICONTROL 工作簿]**&#x200B;选项卡中选择&#x200B;**[!UICONTROL 计划工作簿]**。

1. 允许您使用旧工作簿中的计划详细信息作为默认计划设置。

   ![Report Builder旧版计划设置选项[!DNL Excel]的屏幕截图](assets/upgrade-legacy-schedule-convert.png)

   * 选择&#x200B;**[!UICONTROL 使用]**&#x200B;以使用旧版计划详细信息。 已在[发送工作簿](schedule-reportbuilder.md#schedule-a-workbook)界面中预填充计划详细信息。
   * 选择&#x200B;**[!UICONTROL 不要使用]**&#x200B;以不使用旧版计划详细信息。
   * 选择&#x200B;**[!UICONTROL 取消]**&#x200B;即可取消。

   选择&#x200B;**[!UICONTROL 从将来使用中删除旧元数据]**，以便将来不使用此工作簿的旧计划详细信息。


## 从旧版Report Builder迁移

旧版Report Builder的某些功能在Report Builder中不受支持、部分支持或实施方式不同：

* **实时请求**。 实时请求不受支持，将从已转换的旧工作簿中删除。

* **路径/流失报表**。 不支持流失请求，将从已转换的旧版工作簿中删除该请求。

* 计划报告的&#x200B;**[!DNL FTP]选项**。 计划报表发送至[!DNL FTP]位置的选项不再可用。

* **将工作簿发布到计划报告的[!DNL Power BI]选项**。 计划报表发送至[!DNL Power BI]的选项不再可用。

* **访客指标**。 在转换后的旧工作簿中，以下量度已转换为&#x200B;*独特访客*，即使报表结果可能不完全匹配： `visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly`和`visitorsyearly`。 此转换还适用于`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly`和`mobilevisitorsyearly`。

* **自动重新身份验证**。 打开新的[!DNL Excel]文件时，您需要明确重新进行身份验证。 此重新身份验证是[!DNL Office Add-ins]功能的安全功能。

* **复制具有一组数据块的工作表**。 要支持包含多个数据块的工作表的副本，请执行以下操作：

   1. 在[!DNL Excel]工作簿中选择要复制的工作表选项卡。
   1. 从选项卡的上下文菜单中，选择&#x200B;**[!UICONTROL 移动或复制……]**
   1. 在&#x200B;**[!UICONTROL 移动或复制]**&#x200B;对话框中：
      1. 选择要将复制的工作表复制到何处。
      1. 确保启用&#x200B;**[!UICONTROL 创建副本]**。
      1. 选择&#x200B;**[!UICONTROL 确定]**。
   1. 从源工作表中：
      1. 选择包含所有数据块的单元格范围。
      1. 从![Report Builder中心](/help/assets/icons/Copy.svg)中选择&#x200B;**[!UICONTROL 复制]** [复制数据块](/help/analyze/report-builder/report-builder-hub.md)。
   1. 在目标工作表中：
      1. 选择要将复制的单元格范围粘贴到的单元格。
      1. 从![Report Builder中心](/help/assets/icons/Paste.svg)中选择&#x200B;**[!UICONTROL 粘贴]** [粘贴数据块](/help/analyze/report-builder/report-builder-hub.md)。

* **日期范围**。 Report Builder不迁移应用于旧版Report Builder中日期范围的行标签的日期范围格式选项&#x200B;**[!UICONTROL 将开始和结束期间显示为]**。

* **平均**。 Report Builder未迁移应用于旧版Report Builder中量度的所选格式选项&#x200B;**[!UICONTROL 平均选项]** （**[!UICONTROL 每日平均值]**，一直到&#x200B;**[!UICONTROL 每年平均值]**）。 使用计算量度替换所选选项。

* **在文本前置/后置**。 Report Builder不会迁移应用于旧版Report Builder中指标的&#x200B;**[!UICONTROL 前置/后置文本]**。

* **小计**。 Report Builder未迁移应用于旧版Report Builder中某个量度的格式选项&#x200B;**[!UICONTROL SubTotal（此请求）]**。 当您在旧工作簿请求中使用了&#x200B;**[!UICONTROL SubTotal（此请求）]**&#x200B;时，该功能已转换为&#x200B;**[!UICONTROL Total]**。 例如：在具有前5个页面名称的旧数据块中，您已使用&#x200B;**[!UICONTROL SubTotal（页面查看次数）]**&#x200B;返回前5个页面名称的页面查看次数总和。 迁移后，排名前5的页面名称的相同数据块返回&#x200B;*所有*&#x200B;页面名称的页面查看总和。 使用计算量度功能替代旧版&#x200B;**[!UICONTROL SubTotal]**&#x200B;功能。
