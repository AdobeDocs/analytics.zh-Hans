---
title: 如何将旧版Report Builder工作簿转换为数据块
description: 介绍如何将旧版请求转换为数据块
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 22%

---

# 将旧版Report Builder工作簿转换为数据块

作为迁移到新Report Builder技术的一部分，您可以快速将当前旧版工作簿转换为基于Javascript的工作簿。

>[!IMPORTANT]
>
>复制每个工作簿并重命名一个版本，然后再转换它。 这样，如果需要原始工作簿的副本，您仍然可以使用该副本。


>[!BEGINSHADEBOX]

请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [转换工作簿](https://video.tv.adobe.com/v/3446192?quality=12&learn=on&captions=chi_hans){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]



1. 按[中的说明操作](/help/analyze/report-builder/report-builder-setup.md)设置新的Report Builder。

1. 打开Excel，然后单击右上方的Adobe Report Builder图标。

1. 单击&#x200B;**[!UICONTROL 登录]**&#x200B;并登录到Report Builder。

1. Report Builder加载项检测到此工作簿是否包含[旧版Report Builder](/help/analyze/legacy-report-builder/home.md)请求。

   ![升级工作簿提示](assets/upgrade_workbook.png)

1. 如果找到一个或多个旧版请求，请单击&#x200B;**[!UICONTROL 升级]**&#x200B;以升级工作簿。

   >[!NOTE]
   >
   >您必须单独升级每个请求。 不支持批量升级。


1. 如果升级，会出现警告，提醒您对工作簿的更改。 它还敦促您在继续之前创建旧工作簿的备份。

   ![升级警告](assets/upgrade_warning.png)

1. 单击&#x200B;**[!UICONTROL 继续]**&#x200B;以继续升级。

   如果升级成功，将显示以下完成通知：

   ![升级完成](assets/upgrade_complete.png)

1. （可选）单击&#x200B;**[!UICONTROL 下载升级报告]**。 此报表包含每个已升级数据块的状态。

您现在可以[管理数据块](/help/analyze/report-builder/manage-reportbuilder.md)。


## 新版 Report Builder 不支持旧版 Report Builder 的功能 {#unsupported}

如果将旧版 Report Builder 的功能与新版 Report Builder 插件进行比较，某些旧版功能不再可用：

- 实时请求

- 路径/流失报告

- 用于计划报告的 FTP 选项

- 访客量度。以下量度都将转换为“唯一访客”，即使报告结果可能不完全匹配：`visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly` 和 `visitorsyearly`。这也适用于`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly` 和 `mobilevisitorsyearly`。

## 计划转换的工作簿 {#schedule}

请参阅计划文章中的[计划转换的工作簿](/help/analyze/report-builder/schedule-reportbuilder.md)。