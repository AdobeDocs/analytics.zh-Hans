---
title: 转换旧版Report Builder工作簿
description: 了解如何将基于Report Builder的旧工作簿转换为使用新的Report Builder。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: d7832dc56eb680f57a6875cf32e29fd5a8858098
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 1%

---

# 转换旧版Report Builder工作簿

作为迁移到新Report Builder功能的一部分，您可以快速转换当前基于Report Builder的旧工作簿（旧工作簿）以使用新的Report Builder [数据块](create-a-data-block.md)功能。

>[!IMPORTANT]
>
>在转换旧版工作簿之前，请复制每个工作簿并重命名一个版本。 确保在需要时始终保留原始旧工作簿的副本。


>[!BEGINSHADEBOX]

请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [转换工作簿](https://video.tv.adobe.com/v/3446192?captions=chi_hans&quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]


>[!NOTE]
>
>若要转换旧版工作簿，您必须先设置[新的Report Builder](/help/analyze/report-builder/report-builder-setup.md)。


## 打开旧工作簿

要打开旧工作簿，您可以：

* 直接从本地计算机或网络打开旧工作簿。 在Excel中打开旧版工作簿时：

   1. 从Excel功能区栏中选择![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]**。
   1. 选择&#x200B;**[!UICONTROL 登录]**&#x200B;并登录到Report Builder。
   1. 然后[转换旧工作簿](#convert-a-workbook)。

* 从&#x200B;**[!UICONTROL Report Builder中心]**&#x200B;的[计划](report-builder-hub.md)选项卡中打开计划的旧工作簿。 操作方法：

   1. 打开Excel，然后从Excel功能区栏中选择![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]**。

   1. 选择&#x200B;**[!UICONTROL 登录]**&#x200B;并登录到Report Builder。

   1. 在&#x200B;**[!UICONTROL Report Builder中心]**&#x200B;中选择[计划](report-builder-hub.md)。
   1. 选择&#x200B;**[!UICONTROL 旧版]**&#x200B;选项卡。 选项卡列出了旧版基于Report Builder的计划工作簿。

      ![旧版工作台](assets/upgrade-legacy-schedule.png)

   1. 从列表中选择![SelectBox](/help/assets/icons/SelectBox.svg)要转换的计划工作簿，然后选择![下载](/help/assets/icons/Download.svg)。 在Excel中下载工作簿并在新窗口中打开。 您现在可以[转换旧版Report Builder工作簿](#convert-a--workbook)。


## 转换旧工作簿

要转换旧工作簿，请执行以下操作：

1. 打开旧工作簿后，新的Report Builder将检测此工作簿是否包含[旧版Report Builder](/help/analyze/legacy-report-builder/home.md)请求。

   ![升级工作簿提示](assets/upgrade-workbook.png){zoomable="yes"}

1. 如果找到一个或多个旧请求，请单击&#x200B;**[!UICONTROL 升级工作簿]**&#x200B;对话框中的&#x200B;**[!UICONTROL 升级]**&#x200B;以升级工作簿。

   >[!NOTE]
   >
   >您必须单独升级每个请求。 不支持批量升级。


1. 升级时出现&#x200B;**[!UICONTROL 警告]**&#x200B;对话框，提醒您对工作簿的更改。 它还敦促您在继续之前创建旧工作簿的备份。

   ![升级警告](assets/upgrade-warning.png){zoomable="yes"}

1. 单击&#x200B;**[!UICONTROL 继续]**&#x200B;以继续升级。

   如果升级成功，则显示&#x200B;**[!UICONTROL 工作簿升级现已完成]**&#x200B;通知。

   ![升级完成](assets/upgrade-complete.png)

   * 选择&#x200B;**[!UICONTROL 关闭]**&#x200B;以关闭通知，并继续使用包含新Report Builder更新请求的工作簿。

   * 选择&#x200B;**[!UICONTROL 下载升级报告]**&#x200B;以下载并打开一个显示升级结果的新Excel工作簿。 有关示例，请参见下文。

     ![Excel Report Builder升级报告工作簿](assets/upgrade-report.png)

您现在可以[管理数据块](/help/analyze/report-builder/manage-reportbuilder.md)。


## 计划转换的旧工作簿

您可以选择使用从Report Builder中心的&#x200B;**[!UICONTROL 计划]**&#x200B;选项卡下载和打开的旧版工作簿的计划详细信息。 此选项不适用于具有从本地计算机或网络打开的计划详细信息的旧版工作簿。

1. 计划工作簿。 要计划使用旧版计划转换的旧版工作簿，请执行以下操作：

   * 从Report Builder中心选择&#x200B;**[!UICONTROL 发送工作簿]**，或者
   * 从Report Builder的&#x200B;**[!UICONTROL 计划]**&#x200B;选项卡中提供的&#x200B;**[!UICONTROL 工作簿]**&#x200B;选项卡中选择&#x200B;**[!UICONTROL 计划工作簿]**。

1. 允许您使用旧工作簿中的计划详细信息作为默认计划设置。

   ![迁移旧工作簿计划](assets/upgrade-legacy-schedule-convert.png)

   * 选择&#x200B;**[!UICONTROL 使用]**&#x200B;以使用旧版计划详细信息。 已在[发送工作簿](schedule-reportbuilder.md#schedule-a-workbook)界面中预填充计划详细信息。
   * 选择&#x200B;**[!UICONTROL 不要使用]**&#x200B;以不使用旧版计划详细信息。
   * 选择&#x200B;**[!UICONTROL 取消]**&#x200B;即可取消。

   选择&#x200B;**[!UICONTROL 从将来使用中删除旧元数据]**，以便将来不使用此工作簿的旧计划详细信息。


## 不支持旧版Report Builder功能 {#unsupported}

新的Report Builder中不再提供某些旧版Report Builder功能

* 实时请求。

* 路径/流失报表。

* 计划报表的FTP选项。

* 访客量度。以下量度已转换为&#x200B;*独特访客*，即使报表结果可能不完全匹配： `visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly`和`visitorsyearly`。 此转换还适用于`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly`和`mobilevisitorsyearly`。
